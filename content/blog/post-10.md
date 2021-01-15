---
title: "完全単模"
date: 2021-01-12
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "math"
  - "class"
tags:
  - "optimization"
  
# post type
type: "post"
---

最適化はおもしろそう。。。

### 完全単模性とは
任意の小行列式が0か-1か1の行列のこと.  
別に正方行列じゃなくてもいい.   
成分は, 0か1か-1となる.   
例) 単位行列, 

$A$が完全単模なら, 転置とか, $A$と単位行列を並べてできる行列も完全単模！


### 定理

<details><summary>$A$が完全単模行列のとき, 任意の整数ベクトル$\boldsymbol{b}$に対して$\{\boldsymbol{x}:A\boldsymbol{x} \leq \boldsymbol{b}\}$が整数多面体となる.</summary>

</details>
$\min \boldsymbol{c}^\mathrm{T}\boldsymbol{x}, s.t. A \boldsymbol{x} \leq b$ とかは, $\boldsymbol{b}$がintegralなら最適解もintegral.

整数の縛りを外して考えてやっても, 結局凸多面体の面（単体法で解くなら端点）に最適解が来るので, あれ？整数になってね？というノリかと

### 完全双対整数性(TDI)
$\max \{\boldsymbol{c}^\mathrm{T} \boldsymbol{x}:A\boldsymbol{x}\leq b\} = \min \{\boldsymbol{b}^\mathrm{T} \boldsymbol{y}: A^\mathrm{T} \boldsymbol{y} = \boldsymbol{c}, \boldsymbol{y} \geq 0\}$  
という双対問題において,   
$\boldsymbol{c}$がintegral $\Rightarrow$ $\boldsymbol{y}$もintegral.

あれ, これは完全単模関係ない...?

### 二部グラフとの関係
<details><summary>グラフ$G = (V,E)$ の接続行列を$A$とする. $A$が完全単模$\Leftrightarrow$ $G$が二部グラフ</summary>
</details>
$G = (V,E)$の最大マッチングを求める（婚活パーティ的な）問題は, 以下のように定式化できるらしい.
$$maxmize \ \boldsymbol{1}^\mathrm{T} \boldsymbol{x}$$

$$s.t. A\boldsymbol{x} \leq \boldsymbol{1}, \ \boldsymbol{x}の成分は0か1$$

式の意味は後で書く.

これを解く代わりに, 線形緩和問題（最後の線形束縛をなくしちゃう！）を解いても, $G$の最大マッチングが求められるということだった. すなわち...

"主問題の整数最適解"-> $G$の最大マッチング  
  = （このイコールが完全単模の性質）  
"主問題（緩和）の最適解"    
  = （このイコールは双対問題の性質）  
"(緩和）の双対問題の整数最適解"-> 最小頂点被覆

という関係から有名なKonigの定理が導かれる！！！

<details><summary>【Konigの定理】二部グラフの最大マッチングと最小頂点被覆の大きさが一致する！</summary>
</details>
基礎数理でやりましたね、そういえば.




単模, 変換で出てこなくてじれったい...