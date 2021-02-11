---
title: "Question Answeringの勉強をはじめました！"
date: 2021-02-10
draft: true

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "math"
tags:
  - "deeplearning"
  - "NLP"
  
# post type
type: "post"
---


# QA

aim: find short concrete answers

- knowledge based QA
    - simple-relation <= FAQだと意外とこちら？
    - multi-relation 
- text-based QA
    - find the most similar text between candidate answer texts
    - Given: Q, {A1,A2...An}
    - Recent DNN models

![代替テキスト](./taxonmy.png)

QAの精度をあげるにはどうすればいい！  
=> 日本語の訓練データが足りない！  
=> QG とか BT とかで増やしたい！

# QG

・・・QAPairsからQを生成する

[基本(Microsoft2017)](https://www.aclweb.org/anthology/D17-1090.pdf) 

* traindata: large scale QA pairs from crawling
* CNN, RNN
* by using generated questions as an extra signal, sig- nificant QA improvement can be achieved
* in English ->日本語では難しいのか？

学習データ、コーパスのリソースが英語が多く難しい。

