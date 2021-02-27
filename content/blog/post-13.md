---
title: "情報幾何の新展開"
date: 2021-02-11
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "math"
tags:
  - "information geometry"
  
# post type
type: "post"
---


## 情報幾何(Information Geometry)について

統計学や情報理論を（微分）幾何学的な視点で捉え直す学問. 

## 教科書

甘利先生の「情報幾何の新展開」を自主ゼミで通読しています。初学者がとっつきやすいような, なるべく簡潔な説明を書きたい！.
    
    
    
### 幾何学構造をどうやって定義する？

はじめのうちは「空間に構造を入れる」とかがいまいちピンと来なかった.

確率分布族：多様体, 点の近傍：接空間, 接空間での定規：計量（内積）, 距離を測る：ダイバージェンス, 点同士を結ぶ：接続

nこのパラメタで定まる確率分布全体の集合（確率分布族/統計的モデル）をn次元多様体Sとして扱う.

一般に,計量と接続を外から与えてやると, 多様体の構造が決定でき, 平坦性が定義できる.

### 第１部

割と微分幾何を使わない

凸関数->座標系->ダイバージェンス->計量の流れ。

### 距離尺度

<details><summary>
    距離尺度
    </summary>
    よく登場するものが何種類かあるようのでまとめてみる.
    <ul>
    <li>L1 norm </li>
    <li>L2 norm</li>
    <li>KL divergence</li>
    <li>JS divergence</li>
    <li>Wasserstein distance 輸送コスト最小化問題の解. 堆積した土を移し替えるイメージらしい.</li>
    <li>α-divergence: positive measure下で唯一flatでinvariant, "α=-1でKL, α=1でdual KL, α=0でHellinger"</li>
    </ul>
</details>
  
（追記中）

