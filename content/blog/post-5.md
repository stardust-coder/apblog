---
title: "算法数理メモ"
date: 2021-01-06
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "lectures"
  - "computer science"
tags:
  - "algorithm"
  
# post type
type: "post"
---

### TSP
サンタさん。

Thm. 枝のコストがmetricだと、多項式時間1/2-近似アルゴリズムが存在。
どんなアルゴリズム？
* Gの最小全域木Tの枝を二重にしたグラフG'を作る
* G'のオイラー閉路Xを作る.
* TSPの解は、Xでの順番でGの全点を訪れるツアー
1/2-近似？
* OPT >= OPTから枝を１本取り除いた全域木のコスト >= c(T)
* c(X) = 2c(T)
* c(C) <= c(X) (metric)
* c(C) <= 2OPT = 1/(1-1/2) OPT qed.

Thm. 枝のコストがmetricだと、多項式時間1/3-近似アルゴリズムが存在。
【最近！】


#### TSPとTSP(D)
TSPは最短ツアーを求める問題。
TSP(D)はある整数B以下のツアーがあるか決定する問題。

#### TSPとTSP(D)の関係

TSPが解けたら、TSP(D)は解ける。あたりまえ。

逆は？実は

TSP(D)を多項式回解けば、TSPの解がもとまる。

### 補題：HAMILTON PATH ∝ TSP(D)

ハミルトンパス問題のグラフをGとする。
Gの枝(i,j)があるときdij=1, ないときdij=2, として隣接距離（対称）行列Dをつくる。B = n+1とする。

TSP(D)を解いて、長さn+1以下のツアーがあると判定された
-> パスn本で長さn+1だから、長さ2の枝は高々1本
-> そのツアーの中では長さ1のパスをn-1本連続で通っている。
-> それってハミルトンパスになっている。

・問題の変換はO(logn)

### NP
NPは全てSATに帰着できる。

#### SATとは
充足判定問題:
CNF論理関数が与えられたとき、それが充足可能か判定する。

ある論理関数が充足可能：【定義】ある真理値割当が存在し、論理関数が真になること。

#### HAMILTONPATH ∝ SAT

#### 完全性
* C-complete:任意のL' in CがLに帰着可能
* closed under reductions: L ∝ L' in C
* PとNPは帰着に関して閉じている。

#### SATはNP-complete(Cookの定理)

* NPの任意の問題は非決定チューリングマシンで多項式時間で解ける。
* 「非決定チューリングマシンのプログラムが多項式時間p(n)で状態Yで停止」
同値
「論理関数は充足可能」
* つまり、NPの任意の問題がSATに帰着可能。
* つまり、SATはNP-complete

#### SAT ∝ HAMILTONPATH ∝ TSP(D) ∝ SAT
全てNP-complete

### Bin-Packing問題
前からみてくのが2-近似アルゴリズム


### 万能チューリングマシンU
U(M;x)=M(x), UはMの動作をまねしてる。

#### The HALTING Problem
言語H: 全てのチューリングマシンと停止する入力を符号化した文字列の集合
Hを認識するMHの存在を仮定して背理法を目指す。
＜対角線論法で示す＞


