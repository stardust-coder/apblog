---
title: "学科長の20年前の研究"
date: 2021-01-04
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 
  - "lectures"
  - "computer science"
tags:
  - "algorithm"
  
  
# post type
type: "post"
---

学科長の20年前の研究らしい、興味あり！

### 接尾辞木
1973年
全ての接尾辞を格納したcompacted trie

#### trie（トライ）全人類知ってるん？

* 語源は"retrieval"
* あるノードの配下の全ノードは、自身に対応する文字列に共通するプレフィックス（接頭部）があり、ルート（根）には空の文字列が対応している。
* [Wikipedia](https://ja.wikipedia.org/wiki/トライ_(データ構造))

#### compacted trieってなんですか
なにがコンパクトなんだろう

### 接尾辞配列（suffix array)
1993年
接尾辞のポインタを辞書順にソートした配列
検索は二分探索で行える
二分探索木の高さはO(logn)だった
mは検索したい文字列の長さ、一回の比較につき長さmの文字列比較なのでO(m)かかる。
-> 計算量はO(mlogn)

```perl:suffixarray.pl
#!/usr/bin/perl -w
use strict;
my $t = "hogehogehogege";		# この中から
my @sa = (0..length($t)-1);	# Suffix Array初期化

### Suffix Array の作成
@sa = sort {substr($t, $a) cmp substr($t, $b)} @sa;
for (0..$#sa) { print "$_ $sa[$_] ",substr($t, $sa[$_]),"\n"; }
#ポイントは、ポインタ（数字）が辞書順にソートされている

### バイナリサーチ
my $k = "ppi"; #これがいる場所を探す
my ($l, $u) = (0, $#sa);
while ($l <= $u) {
    my $i = int(($l + $u)/2);
    my $c = $k cmp substr($t, $sa[$i], length($k));
    if ($c > 0) {
        $l = $i + 1;
    } elsif ($c < 0) {
        $u = $i - 1;
    } else {
        print qq("$k" is found at $sa[$i]\n);
        last;
    }
}
```



### 圧縮接尾辞配列(compressed suffix array)

* SA の代わりに Φ[i] = SA^-1[SA[i]+1] を格納
* 先頭の1文字を消しても辞書順は同じ -> これを生かして圧縮する -> すご。あたまよ。

#### できること
lookup(i): SA[i] を返す (O(log n) 時間)
inverse(i): SA-1[i] を返す (O(log n) 時間)
Φ[i]: SA-1[SA[i]+1] を返す(O(1) 時間)
substring(i,l): T[SA[i]..SA[i]+l-1]を返す – O(l) 時間

#### しくみはむずいけど、使ってみるか
リンク切れてた。。。

[](https://echizen-tm.hatenadiary.org/entry/20101028/1288267336)
[](https://echizen-tm.hatenadiary.org/entry/20100818/1282149909)