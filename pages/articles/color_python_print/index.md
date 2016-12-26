---
title: "pythonでの標準出力に色をつける"
date: "2016-12-27"
layout: post
path: "/color_python_print/"
category: "python"
description: "termcolorを使ってpythonでの標準出力に色をつける"
---

## 経緯
LTでライブプログラミングのようなことをする機会があるのですが、
その際のprint()での出力に色が付いていたら少しおしゃれだなってことでライブラリを調べました。
## やること
pythonコード内でのtermialコマンドライン内への標準出力の文字列に色をつける方法を探す
## 使うパッケージ
- termcolor
## ソースコード
上記のtermcolorというライブラリを使用すれば簡単にprint()に色をつけることができました。
```py
from termcolor import cprint

cprint('hello word', 'red')
```
## 感想
`termcolor.cprint`モジュールを使用すれば非常に簡単に出力に色をつけることがわかり、
LTの際に少しカッコをつけれることがわかりました。
## 今後
pythonでかけるcliで表示するpptライブラリのようなものを発見したい。
