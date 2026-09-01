---
title: Neurips 2026 workshop submission
url: /posts/research/2026/neurips-workshop-submission/
---
## Overview

Neurips 2026 Workshopに提出するにあたっての計画と備忘録をまとめます．

基本情報
- [NeurIPS 2026 Workshop | OpenReview](https://openreview.net/group?id=NeurIPS.cc/2026/Workshop)



## 提出先の選定

今回の研究とスコープが一致していると思われるworkshopを探した．
- [NeurIPS 2026 Workshop | OpenReview](https://openreview.net/group?id=NeurIPS.cc/2026/Workshop)
掲載されている一覧から，いくつかリストアップした．
- [NeurIPS 2026 Workshop GDDL | OpenReview](https://openreview.net/group?id=NeurIPS.cc/2026/Workshop/GDDL#tab-recent-activity)
- [NeurIPS 2026 Workshop DevAI | OpenReview](https://openreview.net/group?id=NeurIPS.cc/2026/Workshop/DevAI#tab-recent-activity)
- [NeurIPS 2026 Workshop NeurReps Extended Abstracts | OpenReview](https://openreview.net/group?id=NeurIPS.cc/2026/Workshop/NeurReps_Extended_Abstracts#tab-recent-activity)

### GDDL

![](../../../../../static/images/misc/Pasted%20image%2020260817012306.png)

このワークショップでは深層学習の「表現の幾何学」に注目している．
複雑なデータの構造を幾何学的な構造や確率分布として表現することを，彼らはGeometric Deep Learning と呼んでいて，グラフ構造や多様体などの非ユークリッド空間上における対称性や不変性，同変性．相対情報を表現する手法が提案されている．

データや表現を確率分布としてみなすことで，最適輸送的な視点でのデータ変換が可能になり，これを組み込んだ深層学習技術が発展している．

このワークショップでは「**Geometric Distributional Deep Learning**」に注目する．
特に注目しているものは以下：
	データ、特徴、表現の幾何学的性質と分布的性質を統合的にモデル化する学習システム。私たちの目標は、幾何学的深層学習、計算最適輸送、生成モデリング、グラフと多様体学習、深層学習理論の研究者を共通の問いのもとに結集させることです

今回の私の研究は，上記の視点からは**外れるもの**と考えられる．自分の研究は簡単に言うと以下の通り：
- 本研究は，深層学習の学習中に起こっていると言われている，simplicity biasとそれをデータの統計的性質から解析したDistributional Simplicity Biasに注目する．
- 上記の二つの現象は，段階的に発展してきたものの，この二つの現象を結びつける実験的結果は今まで提供されてこなかった．
- 本研究は，これらの現象を，特異学習理論に基づく局所学習係数によって結びつけられることを主張する．
	- この発見と結果がどんな意味を持つのかを考察する必要があるがまだ終わってない．

この研究は深層学習モデルの学習過程においてみられる複数の現象を，新たな視点によって定量化し，独立して観察されていたものを統合する．本研究が扱う局所学習係数は，モデルの複雑性を図る指標として提案されており，その意味では深層モデルが学習によって獲得する関数の複雑性を定量化・比較している．一方で，モデルの表現について細かくその性質を調べることはしておらず，応用方向への展望も現段階では薄い．
以上を勘案すると，以下に示されているようなワークショップの目的からは外れると結論づけられる．
![](../../../../../static/images/misc/Pasted%20image%2020260817014335.png)


### DevAI

![](../../../../../static/images/misc/Pasted%20image%2020260817020046.png)



![](../../../../../static/images/misc/Pasted%20image%2020260817020142.png)

このワークショップでは発達的観点から知能の創発について議論する．
「to explore what human development can teach us about building more robust, efficient, and human-like artificial intelligence.」


![](../../../../../static/images/misc/Pasted%20image%2020260817020858.png)

学習を発達的視点から理解しようとする視点は，私の研究とも一致する点ではある．さらに今回のSimplicity Biasは，Core Knowledge and Inducive Biasとも深く関連する概念であるから，このワークショップはスコープとしてはかなり近いと考えることもできる．

一方，私の研究はあくまでSimplicity Bias/ Distributional Simplicity BiasをLLCによって定量化して，統合することであるから，神経科学的な視点はほとんど入ってこない．臨界期などの現象と紐づけてストーリーを作った場合うまく見せれば通るかもしれないが，おそらく追加で実験を行う必要がありそう．

たとえばもっと小さいモデルで，bio plausibleな接続行列とそうでないものを用意して違いを見るなどの設定にできたらいいかもしれない．ただしこれは今回は厳しそう．
来年のためにイメージを膨らませておくくらいにしておく．
来年このワークショップに通した上で，他の本会議に向けてそこで議論できるといい．

この議論と，ちょっとしたアイデアのメモはいかに残しておく．
- https://claude.ai/share/0a5adb19-d1ba-4c77-b2fe-b6803ba9e368
	- [HOW CONNECTIVITY STRUCTURE SHAPES RICH AND LAZY LEARNING IN NEURAL CIRCUITS](https://arxiv.org/pdf/2310.08513)
	- [From lazy to rich to exclusive task representations in neural networks and neural codes - ScienceDirect](https://www.sciencedirect.com/science/article/pii/S0959438823001058)
	- [Evaluating biological plausibility of learning algorithms the lazy way](https://openreview.net/pdf?id=HJgPEXtIUS)
	- [How Initial Connectivity Shapes Biologically Plausible Learning in Recurrent Neural Networks](https://arxiv.org/html/2410.11164v1#abstract1)
	- [Training biologically plausible recurrent neural networks on cognitive tasks with long-term dependencies | OpenReview](https://openreview.net/forum?id=O453PHSthc)
	- [[2410.11164] The Influence of Initial Connectivity on Biologically Plausible Learning](https://arxiv.org/abs/2410.11164)
	- [[2410.11164] The Influence of Initial Connectivity on Biologically Plausible Learning](https://arxiv.org/abs/2410.11164)


### NeurReps

![](../../../../../static/images/misc/Pasted%20image%2020260817023258.png)







![](../../../../../static/images/misc/Pasted%20image%2020260824135221.png)





> **応用数学・深層学習・計算論的神経科学の交差領域で、特に「対称性（symmetry）」や「幾何学（geometry）」をニューラルネットワークや神経表現の理解に利用する研究**

を募集しています

#### 特に関連性が高いテーマ

画像に挙げられているテーマは以下です。

1. **不変表現・同変表現の学習理論と手法**
    
    - invariant representations
        
    - equivariant representations
        
    - 例：回転・並進・群作用に対して構造を保つ表現学習
        
2. **トポロジー・幾何・対称性の文脈における統計的学習理論**
    
    - Statistical Learning Theory
        
    - 幾何学的・対称性を持つモデルの汎化や学習理論
        
3. **ニューラルデータにおける表現幾何**
    
    - Representational geometry in neural data
        
    - 生物学的な神経活動だけでなく、人工ニューラルネットワークの内部表現も対象
        
4. **データ中の群構造の学習・利用**
    
    - group structure
        
    - Lie群、群表現などを利用した学習
        
5. **ロボティクスのための同変 World Model**
    
    - equivariant world models
        
    - ロボット制御・環境モデルへの対称性の導入
        
6. **ニューラル表現のダイナミクス**
    
    - Dynamics of neural representations
        
    - 学習中に内部表現がどう形成・変化するか
        
7. **トポロジカル深層学習・トポロジカルデータ解析**
    
    - Topological Deep Learning
        
    - TDA
        
8. **言語における幾何構造**
    
    - Geometric structure in language
        
    - TransformerやLLM内部の表現空間の幾何など
        
9. **生成モデルの幾何学的・トポロジカル解析**
    
    - diffusion model、VAEなどの表現空間・生成分布の構造解析
        
10. **対称性・力学系・学習**
    

- Symmetries, dynamical systems, and learning
    
- ニューラルネットワークを力学系として解析する研究など
    

#### 対象とする研究の種類

理論研究だけに限定されていません。

**理論的な研究と応用的・実験的な研究の両方を歓迎する**と明記されています。

応用領域としては、
- Vision
- Motor control
- Navigation
- Language
    
などが挙げられています。
また、使用する数学的対象として、
- 商空間（quotient spaces）
- ファイバー束（fiber bundles）
- Lie群
- Riemann多様体
- グラフ
- トポロジカル空間
- 群表現

なども歓迎されています。さらに、
- ベンチマークデータセット
- ソフトウェア
の投稿も歓迎されています。

## 執筆
投稿先はまずNeuReps．形式はExtended Abstract.
### 基本情報
- [NeurIPS 2026 Workshop NeurReps Extended Abstracts | OpenReview](https://openreview.net/group?id=NeurIPS.cc/2026/Workshop/NeurReps_Extended_Abstracts#tab-recent-activity)


![](../../../../../static/images/misc/Pasted%20image%2020260824134750.png)
日本時間8/25 21:00


提出について，今回はExtended Abstractとする．
- [NeurIPS 2026 Workshop NeurReps Extended Abstracts | OpenReview](https://openreview.net/group?id=NeurIPS.cc/2026/Workshop/NeurReps_Extended_Abstracts#tab-recent-activity)
![](../../../../../static/images/misc/Pasted%20image%2020260824135600.png)

形式は，Extended Abstract.

![](../../../../../static/images/misc/Pasted%20image%2020260824142435.png)