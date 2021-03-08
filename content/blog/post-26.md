---
title: "Low Resource Text Classification with ULMFit and Backtranslation"
date: 2021-03-05
draft: false

# post thumb
image: "images/featured-post/post-2.jpg"

# meta description
description: "this is meta description"

# taxonomies
categories: 

tags:
  - "nlp"

# post type
type: "post"
---

### AWD-LSTM(ASGD Weighte-Dropped LSTM)
・Drop Connect
・Average-SGD(更新時に前回の重みではなく、前のT回分の重みの平均を使う)

#### LSTMの定式化
[Understanding LSTM Networks](http://colah.github.io/posts/2015-08-Understanding-LSTMs/)という2015年の記事を読んでLSTMをunderstandしていく。

##### RNN
* Humans thoughts have persistence. Understanding each word is based on that of previous words.
* RNN is pretty amazing!
* ex.) predicting the last words of 
  - the clouds are in the sky <= EASY!
  - I grew up in France… I speak fluent French. <= need to go back till France
* when the gap like this(long-term dependencies) grows, RNN can't learn to connect the information, first explored in depth by Hochreiter(1991)

##### LSTM(Long Short Term Memory Networks)
* capable of learning long-term dependencies
* the repeating module
  - standard RNN ... a single tanh layer
  - LSTM ... 4 interacting in a very special way
* CELL STATE (a line running through the top of the diagram)
* GATES
  - FORGET GATE ($h_{t-1}$, $x_t$ -> [0,1])




### ULMFit
#### テクニック
Discriminative fine-tuning  
レイヤーが下位になるほど、一般的なドメイン知識を優先させるために学習率を小さくして、なるべく調整しないようにします。

Slanted triangular learning rates(ロバスト性を保って転移学習させるための工夫)  
学習率そのものをiterationごとに変えていく方法

#### Concat Pooling
LSTMでは長期の依存関係を捉えることができるとは言え、最後の時点の隠れ層の値だけだとどうしても過去の情報は曖昧になってしまいます。

そこで、すべての時点の隠れ層の値を使って、次のレイヤーに渡します。

$$𝐡𝐜=[𝐡_{T},\mathrm{maxpool}(H),\mathrm{meanpool}(H)] $$


#### Forward and Backward

[The Bidirectional Language Model](https://medium.com/@plusepsilon/the-bidirectional-language-model-1f3961d1fb27)


### Test Time Augmentation(TTA)
TTA is simply to apply different transformations to test examples. Then feed these different transformed texts to the trained model and (weighted) average the results to get more confident answer. 

[Kaggle解説記事](https://www.kaggle.com/andrewkh/test-time-augmentation-tta-worth-it)

### Vitrual Adversarial Training(VAT)
Purpose : 事後確率の分布を滑らかにすることで汎化性能を上げるテクニック。
Advantages: unlabeledも学習に活用できる。（事後確率同士の距離を損失に、正則化のイメージ）
Stepは
* p(y|x)とp(y|x+r)を近づける(ダイバージェンス最小化)ようなlossを考える. (rは微小摂動)
* 多次元だと難しいので, 最も間違えやすい方向のみで考える(LDS)
* LDSが二次形式にテイラー近似できる。
* Hessian Free（差分法）でヘッシアンを求め、その最大固有ベクトルが求めたいr.
* べき乗法で最大固有ベクトルを求める.

### Logistic Regressionの詳細
ULMFit overweights the last sentence for good reason, validated by Logistic Regression with L1 regularization.

#### Sentence level Sentiment Regression

The regressions in Table 4 try to predict two targets: the document’s label and the model’s prediction, using summary stats of the distribution of sentence-level predictions as inputs. More specifically we fit
$$target = W · [X−1, X[0], avg(X), max(X), min(X), len(X))]$$

where X is a vector whose elements are the model predicted sentiment of each sentence. We use L1
regularization to get force irrelevant features coefficients to zero.