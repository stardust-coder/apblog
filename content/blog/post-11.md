---
title: "ニューラルネットワークの構成要素"
date: 2021-02-08
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "math"
tags:
  - "deeplearning"
  
# post type
type: "post"
---

### ネットワーク構造

データの性質を見て考える。

なにをつかうか？全結合層、CNN、RNN・・・

パラメータは？CNNならチャネル数、・・・

テキストならAttention, Transformer・・・

活性化関数は何使う？sigmoid, ReLU, tanh・・・

### 目的関数

cross entropy, MSE, Triplet損失 などなどどれを使おう？

タスクによって変わってくる。

### 最適化手法

* SGD（確率的勾配降下法）
* モメンタム
* Adam
* バッチサイズや学習率mエポック数
* early stoppingの有無
* アニーリング
etc.

### Tips
* バッチ正規化
* Dropout
* Data Augmentation
* L2正則化
* アンサンブル学習
* 補助タスク
etc.

大きな構造はどのタスクでも似ているなあ

