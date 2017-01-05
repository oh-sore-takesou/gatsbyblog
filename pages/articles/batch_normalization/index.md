---
title: "batch normalization"
date: "2017-01-05"
layout: post
path: "/batch_normalization/"
category: "nn"
description: "batch normalizationまとめのまとめ"
---

## 参考
[qiita 2016年の深層学習を用いた画像認識モデル](http://qiita.com/aiskoaskosd/items/59c49f2e2a6d76d62798#4-batch-normalization-accelerating-deep-network-training-by-reducing-internal-covariate-shift)

## まとめ
### やっていること
チャンネル間の分布の平均と分散を用いて入力値を正規化している
γc, βcをパラメーターとして学習することで、正規化の際に失われてしまう情報を保持しようとしている。

chainerではone line
