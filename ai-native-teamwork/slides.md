---
theme: default
background: '#FAF9F5'
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## 人の役割は変わりつつある
  AIネイティブ開発時代のチームワーク
drawings:
  persist: false
transition: slide-left
title: 人の役割は変わりつつある - AIネイティブ開発時代のチームワーク
mdc: true
pagination: true
---

<style>
:root {
  --slidev-theme-primary: #D97757;
  --slidev-theme-background: #FAF9F5;
}

.slidev-layout {
  background-color: #FAF9F5;
  color: #000000 !important;
}

h1 {
  color: #000000 !important;
  font-weight: bold;
}

h2, h3, h4, h5, h6 {
  color: #000000 !important;
}

p, li, div, span {
  color: rgba(0, 0, 0, 1) !important;
  font-family: "Nunito Sans" !important;
  opacity: 1 !important;
}

/* コードブロックのスタイル調整 */
pre, .slidev-code, .shiki {
  background-color: #f5f5f5 !important;
  padding: 1rem !important;
  border-radius: 0.5rem !important;
}

/* コードブロック内のテキストでシンタックスハイライトを有効化 */
pre code span,
.slidev-code span,
.shiki span,
pre span,
code span {
  color: revert !important;
  opacity: 1 !important;
}

pre code,
.slidev-code code,
code {
  color: revert !important;
  font-family: 'Fira Code', monospace !important;
}

/* タイトルスライドの全テキストを黒に */
.slidev-layout.text-center p,
.slidev-layout.text-center div {
  color: rgba(0, 0, 0, 1) !important;
}

.accent {
  color: #D97757 !important;
  font-weight: bold;
}

.highlight-box {
  background-color: rgba(217, 119, 87, 0.1);
  border-left: 4px solid #D97757;
  padding: 1rem;
  margin: 1rem 0;
}

/* ページ番号を表示 */
.slidev-page-number {
  display: block !important;
  opacity: 1 !important;
  color: #D97757 !important;
  font-size: 1.2rem !important;
  font-weight: bold !important;
  background-color: rgba(255, 255, 255, 0.8) !important;
  padding: 0.3rem 0.6rem !important;
  border-radius: 0.25rem !important;
  bottom: 1rem !important;
  right: 1rem !important;
}

/* タイトルスライド（1枚目）と最後のThank Youスライドでページ番号を非表示 */
.slidev-page-1 .slidev-page-number,
.slidev-page-12 .slidev-page-number {
  display: none !important;
}

/* タイトルページのプロフィール画像を円形にして右下に配置 */
.profile-circle-container {
  position: absolute;
  bottom: 2rem;
  right: 2rem;
  width: 120px;
  height: 120px;
  border-radius: 50%;
  background-color: #FAF9F5;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
  overflow: hidden;
}

.profile-circle {
  width: 100%;
  height: 100%;
  object-fit: cover;
  display: block;
}

/* テーブルスタイル */
table {
  width: 100%;
  border-collapse: collapse;
  margin: 2rem 0;
}

th, td {
  padding: 1rem;
  text-align: left;
  border-bottom: 2px solid #D97757;
}

th {
  background-color: rgba(217, 119, 87, 0.1);
  font-weight: bold;
}

/* ワークフローボックス */
.workflow-box {
  background-color: rgba(217, 119, 87, 0.05);
  border: 2px solid #D97757;
  border-radius: 0.5rem;
  padding: 1.5rem;
  margin: 1rem 0;
  text-align: center;
  font-size: 1.2rem;
}

.arrow {
  font-size: 2rem;
  color: #D97757;
  margin: 0 0.5rem;
}
</style>

<div class="mt-8">
<h1>人の役割は<br/><span class="accent">変わりつつある</span></h1>

<div class="text-2xl mt-8">
AIネイティブ開発時代のチームワーク
</div>

</br>

Speaker：nogu（@_nogu66）

<div class="profile-circle-container">
  <img src="/images/profile.png" alt="プロフィール" class="profile-circle" />
</div>

</div>

---
layout: two-cols
---

<div class="text-left">

# <span class="accent">ABOUT ME</span>

## <span class="accent">nogu</span> ( @_nogu66 )

<img src="./images/profile.png" alt="プロフィール画像" class="w-60 mt-8" />

</div>

::right::

<div class="mt-32 -ml-16 text-left">

### **ソフトウェアエンジニア** **<span class="accent">/</span> AI愛好家**

<div class="mt-8 text-xl space-y-6">

<span class="accent">•</span>　社内システム開発

<span class="accent">•</span>　生成AI推進

<span class="accent">•</span>　AIエージェント開発

<span class="accent">•</span>　イベント運営・お手伝い

</div>

<div class="mt-5 flex items-center justify-end gap-4">
  <img src="./images/x-qrcode.png" alt="X QRコード" class="w-24" />
</div>

</div>

---

# <span class="accent">従来のハッカソン</span>

<div class="text-left text-2xl mt-12 space-y-8">

### 「全員がコードを書く」が当たり前

<v-clicks>

- <span class="accent">✗</span> エンジニアでないと貢献できない
- <span class="accent">✗</span> 実装スキルが参加条件
- <span class="accent">✗</span> 非エンジニアは企画だけで終わりがち

</v-clicks>

<v-click>

<div class="highlight-box mt-12">
<strong>結果:</strong> チームメンバー全員がコーディングスキルを求められる
</div>

</v-click>

</div>

---

# <span class="accent">変化：今、何が起きているのか</span>

<div class="text-left mt-12">

<v-clicks>

<div class="text-3xl font-bold mb-8">
<span class="accent">「1人で実装できる時代」</span>
</div>

<div class="text-2xl space-y-6">

- AI（Claude Code等）を使えば、**フルスタック開発**も可能
- アイデアから実装まで、**数時間で形に**
- 従来なら数人必要だった作業を**1人で完結**

</div>

</v-clicks>

<v-click>

<div class="text-center text-4xl mt-12">
でも、これで終わり？ 🤔
</div>

</v-click>

</div>

---

# <span class="accent">落とし穴：1人では完璧にならない</span>

<div class="text-left text-xl mt-8">

### AI開発特有の課題

<v-clicks>

<div class="space-y-6 mt-6">

#### <span class="accent">1. バグの見逃し</span>
AIが生成したコードにも、当然バグは存在する

#### <span class="accent">2. エッジケースの考慮漏れ</span>
「普通の使い方」は動くが、想定外の操作で壊れる

#### <span class="accent">3. ユーザー視点の欠如</span>
技術的には正しくても、UXが悪い

</div>

</v-clicks>

<v-click>

<div class="highlight-box mt-8 text-center text-2xl">
<strong>「動く」≠「完成度が高い」</strong>
</div>

</v-click>

</div>

---

# <span class="accent">新しい役割分担の誕生</span>

<div class="text-left text-xl mt-8">

<v-clicks>

<div class="space-y-8">

### <span class="accent">Builder（実装者）</span>
AIと協働してプロダクトを作る
- 要件を理解し、AIに指示を出す
- コードレビューと調整
- 実装のスピードを活かす

### <span class="accent">Validator（検証者）</span>
テスト、デバッグ、イシュー報告で品質を上げる
- ユーザー視点でのテスト
- エッジケースの発見
- イシューの言語化と報告

</div>

</v-clicks>

</div>

---

# <span class="accent">新しいワークフロー</span>

<div class="mt-16">

<div class="workflow-box">
<strong>Builder</strong> <span class="arrow">→</span> 実装
</div>

<div class="text-center text-3xl my-4">↓</div>

<div class="workflow-box">
<strong>Validator</strong> <span class="arrow">→</span> 検証・イシュー化
</div>

<div class="text-center text-3xl my-4">↓</div>

<div class="workflow-box">
<strong>Builder</strong> <span class="arrow">→</span> 修正・改善
</div>

<div class="text-center text-3xl my-4">↓</div>

<div class="workflow-box text-2xl" style="background-color: rgba(217, 119, 87, 0.2);">
<strong>完成度UP ✨</strong>
</div>

</div>

---

# <span class="accent">成功事例：ハッカソンでの実践</span>

<div class="text-left text-xl mt-8">

<v-clicks>

<div class="space-y-8">

### 実践例

<div class="highlight-box">
<strong>チーム構成:</strong> 1人が実装、3人が検証
</div>

#### プロセス
1. **Builder**: AIを使って機能を実装
2. **Validators**: 並行して検証・テスト
3. **イシュートラッカー**: GitHub Issuesで課題管理
4. **反復**: 優先度の高いイシューから修正

### 結果
<span class="accent">✓</span> より高品質なプロダクトが短時間で完成
<span class="accent">✓</span> 全員が価値を提供できる
<span class="accent">✓</span> チーム全体の満足度が向上

</div>

</v-clicks>

</div>

---

# <span class="accent">マインドセットの転換</span>

<div class="mt-8">

### 従来型 vs AIネイティブ

<v-click>

| 従来型 | AIネイティブ |
|--------|--------------|
| 全員がコード書く | **役割分担が明確** |
| エンジニア必須 | **非エンジニアも貢献可能** |
| 実装スピード重視 | **検証プロセス重視** |
| スキル = コーディング | **スキル = 問題発見力** |
| 属人的な品質 | **チーム全体で品質向上** |

</v-click>

<v-click>

<div class="highlight-box mt-8 text-center text-2xl">
<strong>実装は速くなった。だからこそ、検証に時間をかけられる。</strong>
</div>

</v-click>

</div>

---

# <span class="accent">非エンジニアへの指針</span>

<div class="text-left text-xl mt-8">

### コードが読めなくてもできること

<v-clicks>

<div class="space-y-6 mt-8">

#### <span class="accent">1. ユーザー視点でのテスト</span>
「これ、使いにくくない？」が最高のフィードバック

#### <span class="accent">2. エッジケースの発見</span>
「もし〇〇したらどうなる？」を試してみる

#### <span class="accent">3. UI/UXのフィードバック</span>
見た目、動き、使い心地に対する率直な意見

#### <span class="accent">4. イシューの言語化</span>
問題を明確に伝える = エンジニアの時間を節約

</div>

</v-clicks>

<v-click>

<div class="highlight-box mt-8 text-center">
<strong>あなたの「普通のユーザー」視点が、プロダクトを劇的に改善する</strong>
</div>

</v-click>

</div>

---

# <span class="accent">まとめ</span>

<div class="text-left text-2xl mt-12 space-y-8">

<v-clicks>

### <span class="accent">✓</span> AI時代でも「チームワーク」が勝つ
実装は速くなったが、検証の重要性は変わらない

### <span class="accent">✓</span> 役割分担の最適化が成功の鍵
Builder と Validator の協働で完成度を高める

### <span class="accent">✓</span> 誰もが価値を提供できる時代に
コーディングスキルがなくても、貢献できる方法は無数にある

</v-clicks>

<v-click>

<div class="highlight-box mt-8 text-center text-3xl">
<strong>役割は変わった、でも本質は変わらない</strong>
</div>

</v-click>

</div>

---
layout: center
class: text-center
---

# <span class="accent">Thank You!!</span>
<div class="mt-6">
<carbon-logo-x class="inline-block text-2xl"/> のフォローもお願いします！
<br/>
<img src="./images/x-qrcode.png" alt="説明文" class="mx-auto w-50 mt-6" />
<br/>
<p class="accent text-2xl font-bold">@_nogu66</p>
</div>
