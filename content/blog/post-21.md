---
title: "Swiftでアニメーション"
date: 2021-02-26
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories:
  - "programming" 
  - "tutorial"  

tags:
  - "swift"
  
  
# post type
type: "post"
---

# UIView.Animation

アニメーション中にブザーを鳴らしたい・・・

AudioKitを使う。

animationの中に書いてもダメ

結局

Dispatch +0.01s とかにした。スレッドなるものがあるらしい。
同じスレッドで処理されると、アニメーションが終わってから別の処理を呼ぶ（=アニメーション中に再生できない）
のであえて別のスレッドにおいて非同期処理する。

できた。