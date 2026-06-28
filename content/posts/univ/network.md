

# Overview

-   まずVPNに接続する
    -   <https://drive.google.com/file/d/1_htS6AvJraEf3Lxut-G-20HjvyrMms2X/view?usp=drive_link>

-   VPNに接続できたらターミナルでkomainu（セグメントB）を踏み台にしてセグメントAの計算機サーバーに入る．
-   hakugei
    
        ssh -J nakano@133.46.233.35 nakano@133.46.232.31
-   gpu0
    
        ssh -J nakano@133.46.233.35 nakano@133.46.232.40
-   gpu1
    
        ssh -J nakano@133.46.233.35 nakano@133.46.232.41


# 学内で行う初期設定

図の左側のSDS内ネットワークにいるので，vpn接続する必要はなく，
通常通りターミナルからセグメントAに接続できる．

    ssh -v nakano@133.46.233.35

komainuは，図のセグメントBです．つまり，後から外部からセグメントBのkomainu→セグメントAの計算機サーバーに接続するために，いまは内部からセグメントBのkomainuに入り，さらにそこでセグメントAに繋ぐための設定をしている．
まずこれがうまくいけば，

-   [X] 自分のアカウントでkomainuにsshで接続できることが確認できた

つぎに，

-   [ ] komainuを経由して（踏み台にして）hakugeiやその他の計算機サーバーにssh接続できる

を確認する．komainuから出て，（つまりローカルに戻って）以下を叩く．

    ssh -J nakano@133.46.233.35 nakano@133.46.232.31

これが通れば，komainu（セグメントB）からhakugei（セグメントA）にsshで入れることが確認できている．

追加で，gpu0,gpu1にも接続可能かどうかを確かめる．

    # gpu0
    ssh -v -J nakano@133.46.233.35 nakano@133.46.232.40

    # gpu1
    ssh -v -J nakano@133.46.233.35 nakano@133.46.232.41

全て通れば，あとはvpnに接続できさえすればOK.これは次のセクションを参照．


# VPNに接続する

-   学内アカウントでこちらを確認すればOK
    -   <https://mail.google.com/mail/u/0/?tab=rm&ogbl#inbox/FMfcgzQgLXlCvGfBfhdQPVlPlmVzBpDx>
    -   学外からVPN接続するための方法
        -   <https://drive.google.com/file/d/1_htS6AvJraEf3Lxut-G-20HjvyrMms2X/view?usp=drive_link>

-   memo
    -   <https://docs.google.com/document/d/1gk0mpZsCFMgnvXvkRBtFLb7pLfM2gmXAFRVroXY1EEQ/edit?usp=sharing>
    
    -   <https://claude.ai/chat/f176d73b-4b0b-489e-8533-066ad127e244>


# reference


## 現在の構成は以下の通り

![img](../../../static/images/posts/univ/20260422_134542.png)


## 一覧

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">


<colgroup>
<col  class="org-left" />

<col  class="org-right" />

<col  class="org-left" />

<col  class="org-left" />
</colgroup>
<thead>
<tr>
<th scope="col" class="org-left">名前</th>
<th scope="col" class="org-right">IP (住所)</th>
<th scope="col" class="org-left">セグメント</th>
<th scope="col" class="org-left">役割</th>
</tr>
</thead>

<tbody>
<tr>
<td class="org-left">vpn01</td>
<td class="org-right">133.46.233.13</td>
<td class="org-left">B</td>
<td class="org-left">VPN 認証用 (2FA 登録のために一度だけ SSH した)</td>
</tr>


<tr>
<td class="org-left">komainu</td>
<td class="org-right">133.46.233.35</td>
<td class="org-left">B</td>
<td class="org-left">踏み台 (ゲートウェイ)。外から唯一入れる入口</td>
</tr>


<tr>
<td class="org-left">hakugei</td>
<td class="org-right">133.46.232.31</td>
<td class="org-left">A</td>
<td class="org-left">CPU サーバ。研究室のメイン作業機</td>
</tr>


<tr>
<td class="org-left">s23</td>
<td class="org-right">133.46.232.41</td>
<td class="org-left">A</td>
<td class="org-left">GPU サーバ (RTX A6000 x8)</td>
</tr>


<tr>
<td class="org-left">s29</td>
<td class="org-right">133.46.232.40</td>
<td class="org-left">A</td>
<td class="org-left">GPU サーバ (A100 x4)</td>
</tr>


<tr>
<td class="org-left">(H100 機)</td>
<td class="org-right">-</td>
<td class="org-left">A</td>
<td class="org-left">GPU サーバ (H100 x1)</td>
</tr>


<tr>
<td class="org-left">hg001-3</td>
<td class="org-right">192.168.20.1-3</td>
<td class="org-left">ローカル LAN</td>
<td class="org-left">hakugei 配下の計算ノード</td>
</tr>


<tr>
<td class="org-left">ファイルサーバ</td>
<td class="org-right">192.168.20.101</td>
<td class="org-left">ローカル LAN</td>
<td class="org-left">146TB ストレージ</td>
</tr>
</tbody>
</table>

