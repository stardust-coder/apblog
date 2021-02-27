---
title: "面白い論文を見つけた"
date: 2021-02-26
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "programming"

tags:
  - "swift"
  
  
# post type
type: "post"
---


# KUSUGURI: A Shared Tactile Interface for Bidirectional Tickling

10年以上前か〜。テーマが面白い！

日本語に訳すと

くすぐり：相互くすぐりのための共有触覚インターフェース

かな...？

[解説ページ](https://sites.google.com/site/masahirofurukawa/home/projects/kusuguri)

[Masahiro FURUKAWA 先生](https://sites.google.com/site/masahirofurukawa/home/home_e)


# 仕組み

視覚 × 触覚 

てのひらにスマホを乗っける。リアル感を出すためにこのときスマホにはちょうど良いサイズでてのひらの画像を表示しておく。

## 視覚ついて

もともとくすぐられる仕草を見せられると、実際には触れていなくてもくすぐったく感じるらしい。。。へ〜

それを視覚に応用した。

スマホを指でなぞると、その場所どおりの一位置を伝達し、２台目のスマホに指の映像が流れるというもの。

これ、イメージとしてはカメラが上にあって、撮影している感じに見える。でも実際にはカメラはなくて、ディスプレイのタップした位置を取得してその座標を送信して、２台目の画面に指を表示しているみたい。

## 触覚について

上記の視覚と連動して、スマホの裏側に取り付けた振動子を
作動している。

## というかリンク内の動画を見るのが早い！！！

今後はスマホ内部の振動でって言ってるけど、当時はなかったのかな〜わざわざ振動子を取り付けている。

調べてみたら、TapticEngine（iPhoneでタップとかボタンとかおすとカチって言ってるかのような感覚になるギミック）が搭載されてるのはiPhone7からだったーーー

# 参考にして（ぱくって）実装してみた。

まあ単にSwiftとAudioKitやらTapticEngineを触ってみたかっただけなんですけど...

## 環境
* iOS14.4
* Xcode 12.4 （アプデのためのMac容量解放にn年かかった...）
* Swift5.3
* iPhone8

## 手順

1. てのひらを撮影し、背景として表示。(UIViewを全画面サイズにした。)
2. 適当な背景透過画像（今回はやもりのシルエットにした）を用意する。
3. 2. をアニメーションで動かす。(UIImageView.animate)
4. 3.に合わせて振動させる（AudioKitのSystemAudio）


# 感想

微妙すぎる！
ぜんぜんおもんない...

なぜに本家とここまで差が出るのか...

やっぱり今回省いた「遠隔で連動」ってのが本質的な面白さ説あるな。

せっかく触覚に興味出てきたんだけどなぁ


