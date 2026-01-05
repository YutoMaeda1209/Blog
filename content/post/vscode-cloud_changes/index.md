---
title: "意外と知られてないVSCodeのCloud Changes機能について"
date: "2026-01-05T04:42:27Z"
description: "意外と知られていないVSCodeのCloud Changes機能について説明します。"
tags:
    - "VSCode"
    - "CloudChanges"
categories:
    - "Tips"
draft: true
---

## 異なるデバイス間での変更の同期
Gitを使って作業中に、まだコミットはしたくないけど、別のデバイスで作業を続行したい場面があります。
例えば、家のデスクトップPCで開発していたのを、外出先のノートPCで続けたい場合などです。
このような場合は、VSCodeのCloud Changes機能を利用すると便利です。

## 使い方（変更のコピー元）
1. ユーザーアイコンをクリックし、「Turn on Cloud Changes...」を選択し、Cloud Changes機能を有効にする。
2. ステージングしていない状態で、F1キーでコマンドパレットを開き、「Cloud Changes: Store Working Changes in Cloud」を選択する。

## 使い方（変更のコピー先）
1. F1キーでコマンドパレットを開き、「Cloud Changes: Show Cloud Changes」を選択する。
2. 左ペインの上部にあるリロードアイコンをクリックして、クラウド上の変更内容を取得する。
3. 変更内容一覧に表示されたアイテムにカーソルを合わせて、「Resume Working Changes」をクリックする。

## 参考サイト

- [VSCodeの隠し機能Cloud Changesを使って、複数端末で作業を同期する](https://zenn.dev/qrtz/articles/524e1835d4162b)
