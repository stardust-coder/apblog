---
title: "幾何数理"
date: 2021-01-12
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "math"
tags:
  - "topology"
  
# post type
type: "post"
---

幾何数理の期末勉強をはじめなきゃ汗

#### 連結閉曲面の分類定理

連結な閉曲面は
* 穴がkこの浮き輪
* 射影平面をk'こくっつけたもの
のどちらかと同相である！！！

同相・・・位相同型。全単射で逆写像も連続である同相写像が存在。
射影平面・・・P^2
位相空間が連結・・・開かつ閉な集合が自明なもの(空集合と全体)しか存在しない。

#### 弧状連結ならば連結。逆は一般には成り立たない。$\mathbb{R}^n$上の開集合Aについては同値。
証明は、任意の点$x \in A$からパスをひいて行ける点全体を$O$として、$O$の範囲を開球をつかってちまちま広げていく感じ。弧状連結を示したいってことは、$A=O"$を言う、つまりどの点にもパスで行けるよーということが言いたい.

＜使ったこと＞
* 開球は凸集合なので中身はパスで結べる.
* PastingLenmaで、xと開球をパスで結べる. 
* 開球を用いた開と閉の定義.
* Oが開集合かつ閉集合かつ非空 $\Rightarrow$ O=A（全体）



#### ホモトピー

やりたいこと：空間の間のホモトピー同値を、群の間の同型に対応させる。


#### ホモロジー群

##### $H_1(G)$ の意味・・・生成元となるサイクルの個数

以下の３つの操作を導入する.
* 辺の反転
* 辺の細分
* 点の縮約

これらの操作を施してもホモロジー群は不変.

###### ブーケ(bouquet)
* $S^1 \wedge S^1 \cdots \wedge S^1$
 
<details><summary>連結グラフとブーケはホモトピー同値（ホモロジー群も一緒）</summary>
すべての頂点と接続してサイクルを含まない枝数 n − 1 の枝集合のことを，グラフの全域木という. これは可縮な部分複体になる.全域木を1点に縮約すると，全域木に含まれない m − n + 1 本の枝はループになる
</details>

* ブーケのホモロジー群は、$H_0(G) = \mathbb{Z}, H_1(G) = \mathbb{Z}^m$, $m$は花弁の枚数

##### $H_0(G)$の意味・・・連結成分の個数

1次元複体$K$上に離散的ダイバージェンス、ベクトル場、ポテンシャルの存在 $\Leftrightarrow H_0(K) \simeq \mathbb{Z} \Leftrightarrow Kは連結グラフ$


##### ホモロジーの計算の仕方
* 愚直に計算する
* スミス標準形を用いる
* 完全系列を用いる

###### 完全系列とは
すべてのホモロジー群が0であるチェイン複体（アーベル群の列ろ準同型写像たちの組）
* $0 \xrightarrow{f} A \rightarrow B$ のとき, $f$は単射
* $A \rightarrow B \xrightarrow{f} 0$ のとき, $f$は全射
* $0 \rightarrow A \xrightarrow{f} B \rightarrow 0$ のとき, $f$は全単射（つまり同型写像）

##### 代表的な図形のホモロジー群を計算してみる

<details><summary>n次元球体（中身あり）・・・$H_0(\mathbb{B}^n) \simeq \mathbb{Z}, 他は0$</summary>１点に変形レトラクトできるので（可縮）</details>

<details><summary>n次元球面（中身なし）・・・$H_0(\mathbb{S}^n) = H_n(\mathbb{S}^n) \simeq \mathbb{Z}$, 他は$0$</summary>$\mathbb{S}^n$を上半球と下半球に分解し, MV完全列を用いる. 詳細は割愛.</details>

<details><summary>トーラス体$V$・・・$H_k(\mathbb{S}^1)$と同型</summary>うまく写像を定めてやると$V \simeq \mathbb{B^2}\times \mathbb{S}^1 \simeq \mathbb{S}^1$となるらしい...</details>

<details><summary>トーラス面$\mathbb{T}^2$・・・$H_1(\mathbb{T}^2) \simeq \mathbb{Z} + \mathbb{Z}, H_0(\mathbb{T}^2) \simeq H_2(\mathbb{T}^2) \simeq \mathbb{Z}, 他は0.$</summary>うまく写像を定めてやると$V \simeq \mathbb{B^2}\times \mathbb{S}^1 \simeq \mathbb{S}^1$となるらしい...</details>

<details><summary>ブーケ・・・$H_0(G) = \mathbb{Z}, H_1(G) = \mathbb{Z}^m$</summary>それは...そう...</details>

<details><summary>射影平面$\mathbb{P}^2$・・・$H_0(\mathbb{P}^2) = \mathbb{Z}, H_1(G) = \frac{\mathbb{Z}}{2\mathbb{Z}}, 他は0$</summary>
メビウスの帯と円盤の分解に対し, MV完全列を用いる. 詳細は割愛.
</details>



#### 自由群
##### 定義
集合Xから生成された自由群F(X)は,
* $X \in F(X)$
* 与えられた群$G$と$f:X \to G$に対して, $f$が準同型$\hat{f} \to G$ に一意に拡張される
をみたす群である.