---
marp: true
theme: custom-yoshi
paginate: true
footer: 'Marp Custom Theme サンプル'
style: |
  @import 'docs/custom-theme.css';
---

<!-- _class: lead -->
<!-- _paginate: false -->
<!-- _footer: '' -->

# Marp Custom Theme

**custom-yoshi サンプルスライド**

2025年12月3日

---

# はじめに

このスライドは**custom-yoshi**テーマのサンプルです

- 日本語フォント最適化
- 見やすいカラースキーム
- 豊富なレイアウト機能

---

# 基本的な使い方

## テキスト装飾

通常のテキストに加えて、**強調（オレンジ）**や*重要（グリーン）*を使えます

---

# 箇条書きの例

## 主な機能

- レスポンシブデザイン対応
- 2段組・3段組レイアウト
- カスタマイズ可能なカラー

---

# 2段組レイアウト

<div class="two-columns">

<div>

## 左側のコンテンツ

- ポイント1
- ポイント2
- ポイント3

テキストと画像を並べて表示できます

</div>

<div>

## 右側のコンテンツ

コードブロックの例：

```python
def hello():
    print("Hello, Marp!")
```

</div>

</div>

---

# ハイライトボックス

<div class="highlight-box">

**重要なポイント**

このボックスは重要な情報を強調表示するために使用します

</div>

通常のテキストはハイライトボックスの外に配置します

---

# テーブルの例

<div class="center-table">

| 項目    | 説明                  | 備考           |
| ------- | --------------------- | -------------- |
| Marp    | Markdown Presentation | プレゼンツール |
| CSS     | カスタムテーマ        | スタイル定義   |
| VS Code | エディタ              | 開発環境       |

</div>

---

# 3段組レイアウト

<div class="three-columns">

<div>

## カラム1

最初の列の内容

</div>

<div>

## カラム2

2番目の列の内容

</div>

<div>

## カラム3

3番目の列の内容

</div>

</div>

---

# カラースキーム

## 主要カラー

- **メインカラー**: *#00AB8E*（グリーン）
- **アクセント**: **#FFAA00**（オレンジ）
- テキスト: #262626（ダークグレー）

---

# コードの表示

## インラインコード

`const theme = 'custom-yoshi';`

## ブロックコード

```javascript
// JavaScript の例
const presentation = {
  theme: 'custom-yoshi',
  slide: 'sample'
};
```

---

# 複数行テーブル

| 項目     | 詳細                      |
| -------- | ------------------------- |
| システム | macOS<br>Windows<br>Linux |
| エディタ | VS Code                   |
| 拡張機能 | Marp for VS Code          |

---

# リストのネスト

## 階層構造の例

1. 第一階層
   - サブ項目A
   - サブ項目B
2. 第二階層
   - サブ項目C

---

<!-- _class: lead -->

# まとめ

**custom-yoshi**テーマで
美しいプレゼンテーションを作成できます

