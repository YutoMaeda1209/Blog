---
title: "DevContainerでGUIアプリ開発（WSLg）"
date: "2025-11-28T01:55:08Z"
description: ""
tags:
    - "DevContainer"
    - "WSLg"
categories:
    - "未分類"
draft: false
---

## 動機
大学の授業でC言語のGUIアプリを開発することになった。GUIライブラリはGTKを利用することにした。
Windows向けにGTKアプリを開発するには、Msys2をインストールして環境を整える必要がある。
しかし、ローカル環境を汚したくなかったので、DevContainerで開発することにした。
WindowsのDockerはWSL2上で動作しており、WSL2にはWSLgというGUIアプリを動かすための仕組みがある。
これを利用してDevContainerでGUIアプリを開発してみようと思う。

## 注意
DevContainerを理解していることを前提としている。
そのため、DevContainerの基本的な説明は省略する。

## WSLのアップデート
まず、WSLを最新バージョンにアップデートする。
私はWSLをアップデートしていなかったため、ここで躓いた。
```bash
wsl --update
```

## Dockerの設定
Docker Desktopで、WSL Integrationを有効にする。
{{< img url="./img/docker-desktop.webp" alt="Docker DesktopのWSL Integration設定をオンにする様子" >}}

## DevContainerの設定
DevContainerの`docker-compose.yml`に以下を追記する。
サービス名は適宜変更すること。
```yaml
services:
  devcontainer:
    volumes:
      - type: bind
        source: /tmp/.X11-unix
        target: /tmp/.X11-unix
      - type: bind
        source: /mnt/wslg
        target: /mnt/wslg
    environment:
      - DISPLAY=$DISPLAY
      - WAYLAND_DISPLAY=$WAYLAND_DISPLAY
      - XDG_RUNTIME_DIR=$XDG_RUNTIME_DIR
      - PULSE_SERVER=$PULSE_SERVER
```

## DevContainerの立ち上げ
以上で設定は完了。
DevContainerを立ち上げて、GUIアプリを実行してみる。
{{< img url="./img/gui_application.webp" alt="DevContainer上でGUIアプリを実行している様子" >}}

## 参考サイト
- [WSL を使用して Linux GUI アプリを実行する | Microsoft Learn](https://learn.microsoft.com/ja-jp/windows/wsl/tutorials/gui-apps)
- [【WSL 2】dockerコンテナでGUIアプリを実行してWindowsで表示させたい | DevelopersIO](https://dev.classmethod.jp/articles/wsl2-docker-gui-app-windows-display/)
