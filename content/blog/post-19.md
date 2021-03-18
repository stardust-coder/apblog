---
title: "ABCI 初挑戦"
date: 2021-02-25
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories:  
  - "nlp"  
tags:
  - "abci"
  
  
# post type
type: "post"
---

## SSH鍵とはなんぞや
home直下の.sshディレクトリに鍵を保存。
configもいじっておくと楽ちん。

```
ssh abci
```
でログインできるようになった！！！

## 登録する

## ターミナル 操作が基本！！

## sftpコマンド
ローカルで作ったコードとかファイルをget,putで移動すれば良いのか。ふむふむ。
```
sftp abci
```
で

sftp>

ていうモードに。ふむふむ。

!を頭につけたコマンドはローカル側の操作ができるのか〜

ローカルにabci用のフォルダ作ってその中で作業すっかー


## BERTを動かしたい！
日本語版BERTはhuggingfaceのtransmormersに入っているらしいので、それを触ろう。
```
pip install transformers
```

でOKなんか。


## エラーが消えません

venv で仮想環境を作る.
source venv/bin/activate する.

```
(venv) [trial]$ cat run.sh.~~~~~
python: error while loading shared libraries: libpython3.8.so.1.0: cannot open shared object file: No such file or directory
```
わからなみ。




