# Marp4VSCode-CSS-CustomPrompt

Marp for VS Code で美しいプレゼンテーションを作成するためのカスタムCSSテーマとAI支援ガイド

![Sample Slide](sample-slide.pdf)

## 📋 目次

- [特徴](#-特徴)
- [デモ](#-デモ)
- [使い方](#-使い方)
- [AI支援によるスライド作成](#-ai支援によるスライド作成)
- [レイアウト機能](#-レイアウト機能)
- [カスタマイズ](#-カスタマイズ)
- [ライセンス](#-ライセンス)

---

## ✨ 特徴

- **🎨 美しいデザイン**: 日本語フォント最適化と見やすいカラースキーム
- **📐 豊富なレイアウト**: 2段組・3段組、ハイライトボックスなど
- **🤖 AI支援**: プロンプトガイドでAIと協力してスライド作成
- **🌐 CDN対応**: GitHub Pagesから直接読み込み可能
- **📱 レスポンシブ**: 様々な画面サイズに対応

---

## 🎬 デモ

### タイトルページ
![タイトルページ例](https://via.placeholder.com/800x450/00AB8E/ffffff?text=Marp+Custom+Theme)

### 2段組レイアウト
![2段組例](https://via.placeholder.com/800x450/ffffff/262626?text=2-Column+Layout)

### ハイライトボックス
![ハイライト例](https://via.placeholder.com/800x450/fff8e6/FFAA00?text=Highlight+Box)

👉 **[サンプルPDFを見る](sample-slide.pdf)**

---

## 🚀 使い方

### 1. CDN経由で使用（推奨）

Markdownファイルの先頭に以下を追加：

```markdown
---
marp: true
theme: custom-yoshi
paginate: true
footer: 'プレゼンテーションタイトル'
style: |
  @import url('https://yoshizawariku.github.io/Marp4VSCode-CSS-CustomPrompt/custom-theme.css');
---
```

### 2. ローカルファイルで使用

1. `docs/custom-theme.css` をプロジェクトにコピー
2. Markdownファイルで読み込み：

```markdown
---
marp: true
theme: custom-yoshi
style: |
  @import 'custom-theme.css';
---
```

### 3. VS Codeでプレビュー

1. [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode) 拡張機能をインストール
2. `.md` ファイルを開く
3. プレビューボタンをクリック

---

## 🤖 AI支援によるスライド作成

このリポジトリには、**AIエージェント（ChatGPT、Claude、Copilotなど）と協力してスライドを作成するためのガイド**が含まれています。

### 📖 MARP_GUIDE.mdの活用

`prompt/MARP_GUIDE.md` には、Marpスライド作成のベストプラクティスが網羅されています：

- ✅ 基本構造とページ設定
- ✅ レイアウトパターン（2段組、3段組など）
- ✅ 画像挿入とサイズ指定
- ✅ テーブルの作成方法
- ✅ よくあるミスと対策
- ✅ デバッグのヒント

### 🎯 AIへの指示例

```
以下のガイドラインに従って、〇〇についてのプレゼンテーションスライドを作成してください。

[MARP_GUIDE.mdの内容をコピー&ペースト]

トピック: △△△
スライド数: 10枚程度
含める内容:
- 背景説明
- 主要な課題
- 提案手法
- 実験結果
```

### 💡 メリット

- **⏱️ 時間短縮**: AIが構造化されたスライドを自動生成
- **✨ 品質向上**: ベストプラクティスに基づいた一貫性のあるデザイン
- **🔧 簡単修正**: Markdownベースで細かい調整も容易
- **🎓 学習効果**: ガイドを通じてMarpの使い方を習得

---

## 🎨 レイアウト機能

### 2段組レイアウト

```markdown
<div class="two-columns">

<div>

## 左側の内容

- ポイント1
- ポイント2

</div>

<div>

## 右側の内容

![画像](image.png)

</div>

</div>
```

### ハイライトボックス

```markdown
<div class="highlight-box">

**重要な情報をここに記載**

</div>
```

### センター配置テーブル

```markdown
<div class="center-table">

| 列1 | 列2 | 列3 |
| --- | --- | --- |
| A   | B   | C   |

</div>
```

### テキスト装飾

- **強調テキスト**: `**テキスト**` → オレンジ色で表示
- *重要テキスト*: `*テキスト*` → グリーン色で表示

---

## 🎨 カラースキーム

| 用途         | カラーコード | 説明                 |
| ------------ | ------------ | -------------------- |
| メインカラー | `#00AB8E`    | 見出し、重要テキスト |
| アクセント   | `#FFAA00`    | 強調、ハイライト     |
| テキスト     | `#262626`    | 本文テキスト         |
| 背景         | `#FFFFFF`    | ページ背景           |

---

## 📁 ファイル構成

```
Marp4VSCode-CSS-CustomPrompt/
├── docs/
│   ├── custom-theme.css    # カスタムテーマ（公開用）
│   └── index.html           # GitHub Pages ランディングページ
├── prompt/
│   └── MARP_GUIDE.md        # AI用スライド作成ガイド
├── sample-slide.md          # サンプルスライド（Markdown）
├── sample-slide.pdf         # サンプルスライド（PDF）
└── README.md
```

---

## 🔧 カスタマイズ

### フォントサイズの変更

`custom-theme.css` の`:root`セクションを編集：

```css
:root {
    --font-size-title: 40px;   /* タイトル */
    --font-size-body: 26px;    /* 本文 */
    --font-size-small: 22px;   /* 小さいテキスト */
}
```

### カラーの変更

見出しやアクセントカラーを変更：

```css
h1 {
    color: #00AB8E;  /* お好みの色に変更 */
}

strong {
    color: #FFAA00;  /* 強調色を変更 */
}
```

---

## 📦 エクスポート

### PDF出力

VS Codeのコマンドパレット（`Cmd+Shift+P` / `Ctrl+Shift+P`）から：

```
Marp: Export slide deck...
```

### PowerPoint出力

```
Marp: Export slide deck...
```

形式で `.pptx` を選択

---

## 🌐 GitHub Pagesでの公開

このテーマはGitHub Pagesで公開されています：

**🔗 https://yoshizawariku.github.io/Marp4VSCode-CSS-CustomPrompt/**

CSSファイルを直接CDN経由で利用できます。

---

## 🤝 コントリビューション

バグ報告や機能追加の提案は [Issues](https://github.com/yoshizawariku/Marp4VSCode-CSS-CustomPrompt/issues) へお願いします。

---

## 📄 ライセンス

MIT License

---

## 🙏 謝辞

- [Marp](https://marp.app/) - Markdown Presentation Ecosystem
- [Marp for VS Code](https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode)

---

**作成者**: [yoshizawariku](https://github.com/yoshizawariku)
