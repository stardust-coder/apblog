---
title: "文章間距離メモ"
date: 2021-02-24
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "nlp"  

tags:
  
# post type
type: "post"
---


# 文書間距離（類似度）
方針は大きく２つ！

## 文書をベクトル化し、ベクトル空間上でcos類似度を計算する
* 分散表現の加重平均をとる
* cos類似度
* 実用的

## 単語の分散表現をベクトル空間にマッピングし、ベクトル空間上での単語群間の距離を計算
* EMD -> WMD -> WRD
* WMD・・・単語単位で考える。変換するときのコストの総和が高い方が意味が離れているとする。直感的！gensimにメソッドがあるので実装が簡単。
* WRD・・・単語の分散表現を超球面上に射影 [論文](https://arxiv.org/abs/2004.15003v1)  
<= 発想は1つめのと似てないですか？



