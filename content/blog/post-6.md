---
title: " GoogleAnalytics使い方メモ"
date: 2021-01-08
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "tool"
tags:
  
# post type
type: "draft"
---

## はじめてのGoogle Analytics
無料で使えるアクセス解析ツール
### 見れるデータ
ほぼ全部。代表的なものは
* PV数：ページ表示回数
* セッション数：流入〜離脱回数（30分で新セッション開始）
* 滞在時間：ページに滞在した平均時間

### メニューバー
ホーム・カスタム・リアルタイム

ユーザ・集客・行動・コンバージョン
だれが・どこから来て・どのページをみて・何をしたか

アトリビューション

### Google Analyticsはどうやってアクセスを解析してるの？

HTMLにJavascriptのタグが記述してある。
全ページに計測タグが必要。ないとセッションが途切れて正確な回数がカウントできなくなる。

### 流入元判定
Organic Search, Paid Search, Social, Referral, etc.
[公式](https://support.google.com/analytics/answer/3297892?hl=ja)
#### Google Analytics用パラメータ
パラメータとは、URLの末尾についている「？」が入っている文字列

medium（メディア） + source（参照元） + campaign（キャンペーン） + term（キーワード） + content（広告のコンテンツ）から成る。




