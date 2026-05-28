# Blog (Hugo)

Hugo + [hugo-theme-stack](https://github.com/CaiJimmy/hugo-theme-stack) で構築した個人ブログ。

- URL: https://www.yuchigames.com
- テーマ: hugo-theme-stack
- 言語設定: 日本語 (`ja-jp`)

---

## よく使うコマンド

### ローカルサーバー起動

```bash
hugo server
```

下書き記事も含めてプレビューしたい場合:

```bash
hugo server -D
```

デフォルトで http://localhost:1313 でアクセスできる。

### 新しい記事を作成

```bash
hugo new post/<記事ディレクトリ名>/index.md
```

`archetypes/default.md` のテンプレートが適用され、タイトル・日付・カテゴリ・`draft: true` が自動設定される。

### 本番用ビルド

```bash
hugo
```

`public/` ディレクトリに静的ファイルが生成される。下書き (`draft: true`) は含まれない。

下書きも含めてビルドしたい場合:

```bash
hugo -D
```

---

## 記事のフロントマター

`archetypes/default.md` に基づくテンプレート:

```yaml
---
title: "記事タイトル"
date: "YYYY-MM-DDTHH:MM:SS+09:00"
description: "記事の概要"
tags:
  - タグ名
categories:
  - カテゴリ名
draft: true  # 公開時は false に変更
---
```

記事を公開するには `draft: false` に変更するか、フィールドごと削除する。

---

## Tips

### 画像の添付

記事ディレクトリに画像を置いて相対パスで参照する（Page Bundle）:

```markdown
![説明](./image.png)
```

### タグ・カテゴリ

- `tags` はフリーワードで複数指定可能
- `categories` はサイドバーの「カテゴリ」ウィジェットに反映される

### 設定ファイルの確認

```bash
hugo config
```

現在の設定値を一覧表示する。

### ビルド時間の計測

```bash
hugo --templateMetrics
```

テンプレートごとのレンダリング時間を表示する（パフォーマンス最適化に便利）。

### サイト情報の確認

```bash
hugo version
```
