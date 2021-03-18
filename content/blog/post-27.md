---
title: "HuggingFace の Transformers を使う"
date: 2021-03-08
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "tutorial"

tags:
  - "nlp"

# post type
type: "post"
---

# HuggingFace Transformers

[npakaさんのnote](https://note.com/hashtag/HuggingFace)
にいろいろ書いてある。

## Autoregressive models
* 古典的な言語モデルでpretrain
* 一連のトークンに続くトークンを予測
* 得意なタスクは「テキスト生成」
* GPTたち, Transformer-XL, XLNet

## Autoencoding models
* 入力トークンを破損させ、再構築させることでpretrain
* 通常分全体の双方向表現を構築
* 得意なタスクは「テキスト分類」「トークン分類」
* BERT系, XLM, ELECTRA, Longformer

## Seq2seq models
* sequence to sequence の問題に変換する
* 得意なタスクは「翻訳」「要約」「QA」
* Transformer, BART, MarianMT, T5

## Multimodal models
* テキスト入力を画像などと混合し、与えられたタスクに特化する
* 「分類」のためにのみ機能
* MMBT

## Retrieval-based models
* 学習と推論の間に、文書検索を使用。
* Dense Passage Retrieval
  - 質問エンコーダ: 質問をベクトルとしてエンコード。
  - コンテキストエンコーダ : コンテキストをベクトルとしてエンコード。
  - リーダー: 検索されたコンテキスト内の質問の答えを、関連性スコアとともに抽出。


# BlendorBotで遊んでみる

```
pip install transformers
```
でインストールしておく。

```
cannot import name 'BlenderbotTokenizer' from 'transformers' 
```
transformersのバージョンが2.9.1だった。

```
pip install --upgrade transformers
```
バージョンが4.3.3になった。

うわ、なんか大きめのファイルのダウンロードが始まった🥺
嫌だったのでconda環境を専用に作り直してやりました。
ちなみにPyTorchとTensorflowが必要です。