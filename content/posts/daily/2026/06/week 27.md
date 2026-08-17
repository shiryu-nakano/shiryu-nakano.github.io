---
title: week 27
url: /posts/daily/2026/06/week27/
---

## Overview

- **Week 27** | [week 27](/posts/daily/2026/06/week27/)
- [2026-06-29 Mon](/posts/daily/2026/06/29/) | emacs org で書いた（復活）
- [2026-06-30 Tue](/posts/daily/2026/06/30/) | seminar, bayes submition
	- [X] ~~*bayes*~~ [2026-07-01 11:50]
- [2026-07-01 Wed](/posts/daily/2026/07/01/)
	- [x] 公的統計提出
	- [X] ~~*AI for Science*~~ [2026-07-02 12:19]
- [2026-07-02 Thu](/posts/daily/2026/07/02/)
	- [X] ~~*AI for Science 提出*~~ [2026-07-02 12:19]
	- [x] Deep提出
	- [x] Physical AI提出
    - [ ] 初期設定など→なんの？
- [2026-07-03 Fri](/posts/daily/2026/07/03/) | Bayes MTG 
- [2026-07-04 Sat](/posts/daily/2026/07/04/)
- [2026-07-05 Sun](/posts/daily/2026/07/05/)

## Week 27 TASK

### LLC
- [ ] DSBのデータの作成
- [ ] ひとまずDSB on CIFER10で

###  PJ_H (40%)
- [X] ~~*覚醒かつ安静時の時の値のみを取ってきて解析する 5h*~~ [2026-06-21 19:16]
- [ ] 機械学習モデルを動かしてみる 20h
- [ ] 目的をはっきりさせる 2h
- [ ] https://notebooklm.google.com/notebook/b71ee6d5-5324-4d89-98e4-275795f5c533
	- [ ] 休息時間
### Bayes
- [X] ~~*RLCTの実装*~~ [2026-06-21 19:17]
	- [X] ~~*論文の再実装→計画的にやる*~~ [2026-06-20 13:44]
		- [X] ~~*https://www.jstage.jst.go.jp/article/ipsjtrans/7/0/7_20/_pdf*~~ [2026-06-20 13:44]
- [ ] 再現：この前のMTGで決まった自分の担当はなんだったっけ？？
	- [ ] exp2
		- [X] ~~*fig4*~~ [2026-06-20 13:44]
		- [X] ~~*fig5*~~ [2026-06-20 13:44]
		- [ ] fig6→**来週**

### submit
- [x] Deep Learning 
	- [x] https://edu.omnicamp.us/courses/129/assignments/801/
- [x] Bayes 課題
- [ ] ELSI
	- [ ] research introduction

## 喫緊の論文リスト
- [ ] DSB
	- [ ] 研究紹介
- [ ]  Geometry of Forgetting
	- https://openreview.net/pdf?id=qKh7Aip3JC
- [ ] https://www.p.u-tokyo.ac.jp/~zbyszek/zrs/Papers/Entries/2007/9/28_Universal_Scaling_Law_in_Human_Behavioral_Organization_files/PhysRevLett.99.138103.pdf
	- これは実装までやる
	- https://claude.ai/chat/5b1435a5-db53-4a36-91dc-24fd4f59ce3a
- 

- https://arxiv.org/pdf/2606.16399
	- むずそうなのでこのリストの中だと優先度低め．時間のあるときに
## WIP
作業復旧用のメモ
- 固有値の理解
	- https://www.math.s.chiba-u.ac.jp/~yasuda/Chiba/Lec/senkei/tl2009-6.pdf
	- tutorialにもtexがある．書きかけのノートもある
	- https://qiita.com/ymsk_CM/items/cca0b8571cdef7f54a62
- tensor flowのtutorial→特にこれはデータ提示の理解のために重要
	- tutorial

- LLCの実験
	- https://claude.ai/chat/097bf219-3460-405f-8f30-8894847a96bf

- 深層学習
	- https://blog.fltech.dev/entry/2021/04/09/aistats-hayase
	- 手法提案以外の場合は，面白いテーマを自分で探さないと
		- block interleave
		- エッジオブカオスの話と結びつける
			- https://blog.fltech.dev/entry/2021/04/09/aistats-hayase
	- https://www.jst.go.jp/kisoken/act-x/evaluation/s-houkoku/r04/JST_111F001_19206005_2022_Karakida_PER.pdf
- RBFの理解
	- miniexperimentsのrbfがある
- [ ] review of 2025がまだ残っている・・・


- [ ] ELSI②；研究紹介
	- [ ] あえて違うので紹介してみる？PINNsとか
		- [ ] んなことしたらやばいか．死ぬかも
- [ ] ML勉強会資料
- [ ] SLT勉強会資料
	- [ ] latex
- [ ] 統計学術の論文紹介のスライドも
- [X] ~~*公的統計課題*~~ [2026-06-21 19:17]



**留意点**
- 6月→論文紹介と研究紹介が7月にあることを念頭に
	- [ ] 両方のスライドを半分くらいの完成度で作り上げておくこと
- [ ] ELSIの発表資料
	- [ ] 2回目→研究進捗報告



## 一旦後で
- [X] ~~*2025　revew*~~ [2026-07-09 01:17]
- [ ] macbook prom1 のorg fileから撮ってくる
**AI Safety関連**
- [ ] [[2311.17035] Scalable Extraction of Training Data from (Production) Language Models](https://arxiv.org/abs/2311.17035)
- [ ] [[2406.17216] Machine Unlearning Fails to Remove Data Poisoning Attacks](https://arxiv.org/abs/2406.17216)



他のタスク

UNVEILING THE BASIN-LIKE LOSS LANDSCAPE IN　LARGE LANGUAGE MODELSこれ読みたい
![](../../../../../static/images/misc/Pasted%20image%2020260617063118.png)
![](../../../../../static/images/misc/Pasted%20image%2020260617063132.png)


## Review

**seminar**とその後の議論
- LLC+DSB
	- →継続する
- PINNs
	- LLCの論文を紹介した→その論文自体問題設定がはっきりしない
		- LLC→学習過程全体
		- RLCT→学習後
		- パラメータごとの不定性に近い値を持っているかもしれない→その部分の理論を整理できるかもしれない
			- LLCとRLCTの議論を整理しておく方がよさそう
				- 大関さんが論文出してた
- h
	- 論文紹介が優先→出てきたパターンに対しての考察が知りたいらしい
	- ヒストグラム
	- べき分布→後でOK
- [ ] AI  for Science
	- [ ] すぐに出す

