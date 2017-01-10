---
title: "chainer document"
date: "2017-01-09"
layout: post
path: "/chainer_document/"
category: "nn"
description: "chainer関数の知らなかったけど便利そうな関数まとめ"
---

## 目的
深層学習の基礎をなんとなく学習し、簡単なCNNを書いてみたのですが、
以外とchainerをフレームワークとして色々な機能を提供していたことに気づき、
新たてちゃんとドキュメントを読み直してみることにしたので、それをここにまとめます。   
随時追加していきますが、かなり適当にメモ的に書いています。


- [ここ](http://docs.chainer.org/en/latest/reference/core/link.html#chainer.Link)のexampleを見ることでlayerを自作したい時のヒントが得られる。
- `Link.add_param('name', size)`は自分でLinkクラスを継承して新しいLinkを定義した際にパラメーターを自クラスに追加する時に使用できる。
- `Link.children` returns a generator of all child links
- `Link.links(skipself=False)` returns a generator of all links under the hidrarchy
- 再認識: `Chain`クラスは`Link`をオブジェクトライクにまとめておくインターフェイス
- `Optimizer.t`は`update()`された回数を参照することができる
- `Optimizer.epoch`は`new_epoch()`された回数
- chainer関係ないメモ
    - clipping gradients -> 勾配が大きくなりすぎないように、gradientの値を計算した後に値が閾値を超えていたら修正する
- `optimizer.GradientNoise()` 勾配計算の後に勾配にnoiseを加えたい時にhookしておける
- `dataset.DatasetMixin()` データセットを定義する際のbaseクラス [参考](http://qiita.com/tttamaki/items/9d854e9fab13dbba25be)
- `dataset.concat_examples(batch, ...)` データセットに他のバッチを連結する関数
- [trainerの例](http://qiita.com/xolmon/items/6d1f0d38bc00b3b828b6)
- trainerはプロパティとして、`elasped_time`を持っていて学習に要した時間を蓄えておくことができる。
- [ここ](http://docs.chainer.org/en/stable/tutorial/basic.html#example-multi-layer-perceptron-on-mnist)でインスタンス化される`Trainer()`の第二引数に渡されている`(20, 'epoch')`は`stop_trigger()`に渡される`run()`が終了する条件
- `chainer.set_debut(True)`でdebugモードすることができる。
- `chainer.computational_graph.build_computational_graph(outputs, ...)`を使用することで、`outputs`からネットワークの構造をグラフにしてファイルに出力してくれる。
