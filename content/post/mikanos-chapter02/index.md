---
title: "MikanOS 第2章"
date: "2026-02-05T05:52:38Z"
description: ""
tags:
    - "MikanOS"
categories:
    - "備忘録"
draft: true
---

## はじめに
[ゼロからのOS自作入門](https://ndlsearch.ndl.go.jp/books/R100000002-I031323308)第2章のまとめ記事です。

## EDK2のビルドエラー
EDK2でMikanLoaderPkgをビルドしようとしたところ、以下のようなエラーが発生しました。

```
Build environment: Linux-6.6.87.2-microsoft-standard-WSL2-x86_64-with-glibc2.35
Build start time: 15:14:59, Feb.05 2026

WORKSPACE        = /home/yuto/edk2
EDK_TOOLS_PATH   = /home/yuto/edk2/BaseTools
CONF_PATH        = /home/yuto/edk2/Conf
PYTHON_COMMAND   = /usr/bin/python3


Processing meta-data .
Architecture(s)  = X64
Build target     = DEBUG
Toolchain        = CLANG38

Active Platform          = /home/yuto/edk2/MikanLoaderPkg/MikanLoaderPkg.dsc


build.py...
/home/yuto/edk2/MikanLoaderPkg/MikanLoaderPkg.dsc(...): error 4000: Instance of library class [RegisterFilterLib] is not found
        in [/home/yuto/edk2/MdePkg/Library/BaseLib/BaseLib.inf] [X64]
        consumed by module [/home/yuto/edk2/MikanLoaderPkg/Loader.inf]


- Failed -
Build end time: 15:14:59, Feb.05 2026
Build total time: 00:00:00
```

[[1]](#参考文献)を参考に、gitタグを`edk2-stable202011`に変更したところ、無事ビルドが成功しました。

## 参考文献
1. [EDK2を使ってメモリマップを取得してみよう](https://kenpos.dev/edk2%E3%82%92%E4%BD%BF%E3%81%A3%E3%81%A6%E3%83%A1%E3%83%A2%E3%83%AA%E3%83%9E%E3%83%83%E3%83%97%E3%82%92%E5%8F%96%E5%BE%97%E3%81%97%E3%81%A6%E3%81%BF%E3%82%88%E3%81%86/)
