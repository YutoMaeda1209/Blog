---
title: "MikanOS 第1章"
date: "2026-02-05T05:13:26Z"
description: ""
tags:
    - "MikanOS"
    - "WSL"
categories:
    - "備忘録"
draft: true
---

## はじめに
最近、[ゼロからのOS自作入門](https://ndlsearch.ndl.go.jp/books/R100000002-I031323308)を読み始めました。
一章を読むごとに、躓いた点や対処方法についてまとめていきたいと思います。

## 環境構築
本書では、Ubuntu上で開発環境を構築することが推奨されていますが、私はWSL2上でUbuntu22.04を立ち上げて開発を行うことにしました。
今後、別用途でUbuntuを使うかもしれないので、Ubuntu-22.04をtarファイルにエクスポートしておき、Ubuntuを複数インストールできるようにしました[[1]](#参考文献)。

## バイナリエディタの選定
せっかくなので、UbuntuCUI上で作業を完結させたかったため、CUI上で動作するバイナリエディタを探しました。
いくつか試した結果、`hexedit`が使いやすかったので、これをインストールしました。

## 参考文献
1. [WSL2の環境をきれいに使う方法](https://qiita.com/GeekMasahiro/items/2b06885b1455ce2ca2a0)
