---
title: "自然言語処理"
date: 2021-02-11
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "math"
  - "lectures"

tags:
  - "NLP"
  
  
# post type
type: "post"
---


数理情報工学特論第一とかいう今年から始まったやつ

<details><summary>
    「意味」とは・言語モデル
    </summary>
    【意味】
    Harrisの分散意味論
    単語の「意味（価値？）」　＝　単語の分布？
    意味の合成性　ベクトルの和
    （田2017）||w(st) - 1/2(w(s)+w(t))||^2 <= 1/2 (pi_{s\t}^2 + pi_{t\s}^2 + pi_{s\t}pi_{t\s})
    【言語モデル】
    x = x1,...xn,..., p(xn|x1,...xn-1)を求めること。
</details>

<details><summary>
    n-gram
    </summary>
    n-gramを使うと、原文とシャッフルとモンキー列が識別できる。
    自然言語では長いn-gramでも冪（順位頻度分布両対数プロットで直線）が成り立つ. ランダムはそれが簡単に消える。（モンキーは特に）
    →課題はシャッフル列をもっと明確に大元から峻別する
    時系列解析, 感覚時系列でtheの系列とかなら明確に違いが出る
    「深層学習は愛は語れない」
    極値解析・ワイブル分布
    強定常・弱定常・エルゴード・カオス・複雑系（定義が曖昧）
    自然言語は弱定常ですらない。
</details>

<details><summary>
    Zipf則
    </summary>
    面白いなぁ、数理民にとっては教養らしい、NLP100本ノックの第４章
    マンデルブロー「情報量あたりのコストを最適化している→冪乗則が現れる」
    Fermatの原理的な扱い？
</details>