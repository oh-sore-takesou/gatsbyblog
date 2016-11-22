---
title: "youtube-ios-player-helplerでvevoの動画が再生できない問題"
date: "2016-11-23"
layout: post
path: "/ios-youtube-restriction-error/"
category: "iOS"
description: "This video contains content from VEVO. It is restricted from playback on certain sites. Watch on YouTubeの対処法"
---

## 問題     
[ios-youtube-player-helperプラグイン](https://github.com/youtube/youtube-ios-player-helper)を使用して、動画の所有者が[VEVO](https://ja.wikipedia.org/wiki/VEVO)
の動画を再生しようとすると  
"This video contains content from VEVO. It is restricted from playback on certain sites. Watch on YouTube"というエラーが出る

## ios-youtube-player-helperとは
iOSアプリ内でyoutubeの動画を再生するためのプレイヤー等を簡単に設置することのできるYOUTUBEの公式ライブラリです。

## 参考
ios-youtube-player-helperの使い方は[こちらのブログ](http://dev.classmethod.jp/smartphone/youtube-player-ios-helper/)に詳しく解説があります。

## 対処法
[stackoverflowの投稿の中に簡潔な説明](http://stackoverflow.com/questions/30972123/using-ytplayerview-to-play-embedded-youtube-video-in-ios-failed-with-restriction)がありました。   
具体的には動画をロードする際の引数 (playerVars)に`origin`パラメーターを追加してあげるだけです。
```swift
self.playerView.loadWithVideoId("i7P4hjusxB0", playerVars: ["playsinline":1])
```
これを
```swift
self.playerView.loadWithVideoId("i7P4hjusxB0", playerVars: ["playsinline":1, "origin": "https://www.example.com"])
```
に変更してあげるだけです。      
ちなみにパラメーター内のURLはなんでも大丈夫みたいです。 (https://www.example.com)でも大丈夫でした。
