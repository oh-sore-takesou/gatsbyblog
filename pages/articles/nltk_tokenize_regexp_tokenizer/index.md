---
title: "nltkのtokenize.RegexpTokenizer()に引数を与えてtokenizeの条件を設定する"
date: "2016-06-16"
layout: post
path: "/nltk_tokenize_regezptoken/"
category: "NLP"
description: "nltkのtokenizeの正規表現を自分で編集する"
---

普通にnltk.tokenize.word_tokenize(text)としても良いのだがこれだと、

'I'm a student.' -> ['I', "'m", 'a', 'student', '.']

となって場合によっては都合が悪い。

そんな時はnltk.tokenize.RegexpTokenizerを使うと自分で分け方を正規表現を用いて指定できる。

上の分を例にして考えると、

```python
from nltk.tokenize import RegexpTokenizer

tokenizer = RegexpTokenizer("[\w']+")

tokenizer.tokenize("I'm a student.")
```

とすると

["I'm", 'a', 'student']

になる。



句読点などを残したい際にはand演算子で正規表現を加えていくと良い。

```python
tokenizer = RegexpTokenizer("[\w']+|[\.]")
```

----

[参考サイト]

[impythonist](https://impythonist.wordpress.com/2014/02/11/language-translation-with-python/)
