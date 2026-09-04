---
title: VPN接続時のスマホのOTP簡略化
url: /posts/engineering/memo/shortcut-otp/
---
# やること

PCからVPNでGPU/CPUサーバに接続するときに毎回スマホのAuthenticatorを使うのがめんどくさい．

PC1台で接続できるようにしたい

---
# 手順

oathtoolをインストールしておく．

```jsx
brew install oath-toolkit
```

つぎに，すでにVPN接続できる状態であればしておく．そうでなければ大学に言って学内インターネットに接続する．

接続したら

```jsx
dm260013@vpn01:~$ cat ~/.google_authenticator
```

この初めの一行目の文字列をコピーしておく．

oath-toolがインストールできたら，さっきコピーした文字列（シークレットキー）を使って以下を実行．

シークレットキーは””で囲んでおく．

```jsx
oathtool --totp -b "シークレットキー"

```

これを実行すると6桁のワンタイムパスワードが出力される．これが，すでにスマホで使っているAuthenticatorの出力している文字と同じかどうかを確認して，一致していればOK.

さらに，ワンタイムパスワードは30秒ごとに更新されるため，残り秒数がわかったほうが便利である．

```jsx
brew install watch
```

これをインストールしておけば，以下を実行することで更新されるまでの秒数を表示しながら，最新のワンタイムパスワードを表示することができる．

```jsx
watch -n 1 'echo "OTP: $(oathtool --totp -b "シークレットキー")" && echo "残り秒数: $((30 - $(date +%s) % 30))秒"'
```

# 関数化

毎回面倒なので，ターミナル内部で関数にしておく．

```jsx
open -e ~/.zshrc
```

以下の関数を追記

```bash
vpn_otp_watch() {
  local secret="ここに実際のシークレットキーを入れる"
  local start=$(date +%s)
  local timeout=120  # 2分で自動終了

  while true; do
    local now=$(date +%s)
    local elapsed=$((now - start))
    if (( elapsed >= timeout )); then
      printf "\n2分経過したため自動終了しました\n"
      break
    fi

    local remaining=$((30 - now % 30))
    local code=$(oathtool --totp -b "$secret")
    echo "$code" | pbcopy
    printf "\rOTP: %s (自動コピー済) | 残り: %2d秒 | 終了まで: %3d秒 " "$code" "$remaining" "$((timeout - elapsed))"

    sleep 1
  done
}
alias vpnotp='vpn_otp_watch'
```

権限付与

```bash
chmod 600 ~/.zshrc
```

設定読み込み

```bash
source ~/.zshrc
```

実行

```bash
vpnotp
```

# 参考

- [https://drive.google.com/file/d/1_htS6AvJraEf3Lxut-G-20HjvyrMms2X/view?usp=sharing](https://drive.google.com/file/d/1_htS6AvJraEf3Lxut-G-20HjvyrMms2X/view?usp=sharing)
- [https://claude.ai/share/14e479d0-8896-4873-b5c2-1e18e7ae854d](https://claude.ai/share/14e479d0-8896-4873-b5c2-1e18e7ae854d)



