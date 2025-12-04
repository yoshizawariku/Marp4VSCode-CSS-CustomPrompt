# Marp スライド作成ガイド

## 目次
1. [基本構造](#基本構造)
2. [ページ設定](#ページ設定)
3. [レイアウトパターン](#レイアウトパターン)
4. [画像の挿入](#画像の挿入)
5. [テーブル](#テーブル)
6. [カスタムCSS](#カスタムcss)
7. [よくあるミスと対策](#よくあるミスと対策)

---

## 基本構造

### スライドの開始部分（必須）

```markdown
---
marp: true
theme: custom
paginate: true
footer: 'プレゼンテーションのフッター'
style: |
  @import 'custom-theme.css';
---
```

**重要ポイント:**
- `marp: true` は必須
- `theme: custom` でカスタムテーマを指定
- `style: |` の後に改行してから `@import` を記述
- CSSファイルのインポートは相対パス

### ページ区切り

```markdown
---

# 新しいページのタイトル

内容...

---

# 次のページのタイトル
```

**重要ポイント:**
- ページは `---` で区切る
- `---` の前後には必ず空行を入れる

---

## ページ設定

### 特定ページの設定変更

```markdown
<!-- _class: lead -->
<!-- _paginate: false -->
<!-- _footer: '' -->

# タイトルページ
```

**設定項目:**
- `_class: lead` - タイトルページ用の中央揃えクラス
- `_paginate: false` - ページ番号を非表示
- `_footer: ''` - フッターを非表示

**注意:**
- `_` プレフィックスは現在のページのみに適用
- プレフィックスなしは全ページに適用

---

## レイアウトパターン

### 1. 2段組レイアウト

```markdown
<div class="two-columns">

<div>

## 左側の内容

- 箇条書き1
- 箇条書き2

</div>

<div>

## 右側の内容

![画像](path/to/image.png)

</div>

</div>
```

**重要ポイント:**
- `<div>` タグの前後に**必ず空行**を入れる
- 空行がないとマークダウンとして解釈されない
- 閉じタグ `</div>` の後にも空行

**NG例（空行なし）:**
```markdown
<div class="two-columns">
<div>
内容
</div>
</div>
```

### 2. ハイライトボックス

```markdown
<div class="highlight-box">

**重要な内容をここに記載**

</div>
```

### 3. センター配置テーブル

```markdown
<div class="center-table">

| 列1 | 列2 | 列3 |
| --- | --- | --- |
| A   | B   | C   |

</div>
```

---

## 画像の挿入

### 基本構文

```markdown
![代替テキスト](path/to/image.png)
```

### サイズ指定

```markdown
# 幅指定
![w:600](image.png)
![w:100%](image.png)

# 高さ指定
![h:400](image.png)
![h:450](image.png)

# 幅と高さの両方
![w:800 h:600](image.png)
```

**サイズ指定の方法:**
- `w:数値` - 幅をピクセルで指定
- `w:数値%` - 幅をパーセントで指定
- `h:数値` - 高さをピクセルで指定

### 2段組内での画像配置

```markdown
<div class="two-columns">

<div>

テキスト内容

</div>

<div>

![w:100%](figure/envs_new/example.png)

</div>

</div>
```

**ポイント:**
- 右側に画像を配置する場合は `w:100%` を使用すると良い
- 画像のパスは相対パス（`.md`ファイルからの相対位置）

---

## テーブル

### 基本テーブル

```markdown
| 列1     | 列2     | 列3     |
| ------- | ------- | ------- |
| データ1 | データ2 | データ3 |
| データ4 | データ5 | データ6 |
```

### 複数行セル（改行）

```markdown
| 項目         | 説明                      |
| ------------ | ------------------------- |
| ハードウェア | 6,144 CPU<br>+ 8 V100 GPU |
| 学習時間     | 30時間                    |
```

**ポイント:**
- セル内で改行したい場合は `<br>` を使用
- `\n` や実際の改行は使えない

### 中央揃えテーブル

```markdown
<div class="center-table">

| 用途             | 推奨ツール |
| ---------------- | ---------- |
| RL研究           | Isaac Gym  |
| 視覚ベースタスク | Isaac Sim  |

</div>
```

---

## カスタムCSS

### CSSファイルの基本構造

```css
/* custom-theme.css */

/* ベーステーマのインポート */
@import 'default';

section {
  background-color: #ffffff;
  color: #333333;
  font-family: 'Helvetica Neue', Arial, 'Hiragino Sans', sans-serif;
  font-size: 28px;
  padding: 60px;
}

/* タイトルページ用 */
section.lead {
  text-align: center;
  justify-content: center;
}
```

### 2段組レイアウト用CSS

```css
.two-columns {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 40px;
  align-items: start;
}

.two-columns > div {
  min-width: 0;
}
```

**重要ポイント:**
- `display: grid` で2カラム化
- `grid-template-columns: 1fr 1fr` で均等分割
- `gap: 40px` でカラム間の余白
- `align-items: start` で上揃え

### ハイライトボックス用CSS

```css
.highlight-box {
  background-color: #e3f2fd;
  border-left: 5px solid #1976d2;
  padding: 20px;
  margin: 20px 0;
  border-radius: 5px;
}
```

### センター配置テーブル用CSS

```css
.center-table {
  display: flex;
  justify-content: center;
  margin: 20px 0;
}

.center-table table {
  margin: 0 auto;
}
```

### 見出しスタイル

```css
h1 {
  color: #1976d2;
  font-size: 48px;
  margin-bottom: 30px;
  border-bottom: 3px solid #1976d2;
  padding-bottom: 10px;
}

h2 {
  color: #1976d2;
  font-size: 36px;
  margin-top: 20px;
  margin-bottom: 20px;
}

h3 {
  color: #424242;
  font-size: 28px;
  margin-top: 15px;
  margin-bottom: 15px;
}
```

---

## よくあるミスと対策

### ミス1: HTMLタグ周辺の空行忘れ

**❌ NG:**
```markdown
<div class="two-columns">
<div>
内容
</div>
</div>
```

**✅ OK:**
```markdown
<div class="two-columns">

<div>

内容

</div>

</div>
```

**対策:** HTMLタグの前後には必ず空行を入れる

---

### ミス2: CSSインポートの記法ミス

**❌ NG:**
```markdown
---
marp: true
style: @import 'custom-theme.css';
---
```

**✅ OK:**
```markdown
---
marp: true
style: |
  @import 'custom-theme.css';
---
```

**対策:** `style: |` を使用し、次の行からインデントしてCSSを記述

---

### ミス3: 画像パスの間違い

**❌ NG:**
```markdown
![](./figure/image.png)  <!-- 不要な ./ -->
![](/figure/image.png)   <!-- 絶対パスは使わない -->
```

**✅ OK:**
```markdown
![](figure/image.png)
![](figure/envs_new/Ant_crop.png)
```

**対策:** .mdファイルからの相対パスを使用（`./` は不要）

---

### ミス4: テーブル内の改行

**❌ NG:**
```markdown
| 項目   | 説明   |
| ------ | ------ |
| A      | 複数行 |
| の内容 |
```

**✅ OK:**
```markdown
| 項目 | 説明             |
| ---- | ---------------- |
| A    | 複数行<br>の内容 |
```

**対策:** セル内改行は `<br>` タグを使用

---

### ミス5: CSSセレクタの優先順位

**問題:** カスタムスタイルが適用されない

**原因:** セレクタの詳細度が足りない

**✅ 解決策:**
```css
/* 詳細度を上げる */
section h1 {
  color: #1976d2;
}

/* または !important を使用（非推奨だが確実） */
h1 {
  color: #1976d2 !important;
}
```

---

### ミス6: 2段組の幅調整

**問題:** 左右の幅を変えたい

**❌ NG:** マークダウン側で調整しようとする

**✅ OK:** CSS側で調整
```css
/* 左：右 = 2：1 の比率 */
.two-columns {
  grid-template-columns: 2fr 1fr;
}

/* 左：右 = 1：2 の比率 */
.two-columns-reverse {
  grid-template-columns: 1fr 2fr;
}
```

---

## チェックリスト

スライド作成時に確認すべき項目:

- [ ] Front Matter（`---` で囲まれた部分）に `marp: true` がある
- [ ] CSSファイルが正しくインポートされている
- [ ] 各ページが `---` で区切られている
- [ ] HTMLタグの前後に空行がある
- [ ] 画像パスが相対パスで正しい
- [ ] テーブルのフォーマットが整っている
- [ ] 2段組内の `<div>` タグが正しくネストされている
- [ ] フッターやページ番号の設定が意図通り

---

## デバッグのヒント

### プレビューが正しく表示されない場合

1. **VSCodeのMarp拡張機能を確認**
   - Marp for VS Code がインストールされているか
   - プレビュー機能が有効か

2. **HTMLタグの閉じ忘れチェック**
   ```markdown
   <div class="two-columns">
   <!-- ... -->
   </div>  <!-- 閉じタグの確認 -->
   ```

3. **CSSファイルの読み込み確認**
   - ファイル名が正しいか
   - ファイルパスが正しいか
   - CSS構文エラーがないか

4. **空行チェック**
   - HTMLタグの前後
   - マークダウンの見出しの前後

---

## サンプルテンプレート

### 完全な最小構成

```markdown
---
marp: true
theme: default
paginate: true
footer: 'My Presentation'
---

# タイトルページ

副題

---

# 通常のページ

## セクション

- 箇条書き1
- 箇条書き2

---

# 2段組のページ

<div class="two-columns">

<div>

## 左側

内容

</div>

<div>

## 右側

![画像](image.png)

</div>

</div>

---

# まとめ

ありがとうございました
```

---

## 参考リンク

- **Marp公式ドキュメント**: https://marpit.marp.app/
- **Marp CLI**: https://github.com/marp-team/marp-cli
- **VSCode拡張機能**: https://marketplace.visualstudio.com/items?itemName=marp-team.marp-vscode

---

## 更新履歴

- 2025年12月2日: 初版作成
  - 基本構造、レイアウトパターン、CSS記法を網羅
  - よくあるミスと対策を追加
  - チェックリストとデバッグヒントを追加


## スライドの内容に関するルール
- 1スライド1メッセージを基本に
- 箇条書きは3つまで