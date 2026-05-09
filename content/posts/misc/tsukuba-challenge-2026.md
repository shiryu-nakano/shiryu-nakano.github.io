---
title: "つくばチャレンジ2026参加メモ"
bookCollapseSection: true
url: /posts/misc/tsukuchal2026/ 
---

# Overview
現在進行中です。

### 今年度追加する機能（私の担当部分）
- EMCLとGNSSの２つの自己位置推定方法のNodeをLifecycleとして実装し、これらをロボットの状態に応じて切り替えるNodeによって柔軟に切り替える機能を追加する。
- カメラを用いた物体検知機能を追加する
- 物体検知結果による行動計画を行う（DWA）


### 作業記録

- Graphを用いたロボットの状態表現と状態遷移を実現するNode (Experimental repository)
  - [リポジトリ](https://github.com/shiryu-nakano/transition_recipe_test)
    - [作業ログ](https://github.com/shiryu-nakano/transition_recipe_test/blob/develop/arcanain_apply/docs/memo.md)

  