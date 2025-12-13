---
theme: default
background: '#FAF9F5'
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## まだ間に合う！Claude Code元年をふりかえる
  2025年にリリースされたClaude Codeを振り返り、SubagentsとAgent Skillsの使い分けを学ぶ
drawings:
  persist: false
transition: slide-left
title: まだ間に合う！Claude Code元年をふりかえる
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
.slidev-page-23 .slidev-page-number {
  display: none !important;
}
</style>

<div class="mt-8">
<h1>まだ間に合う！<br/><span class="accent">Claude Code元年</span>を<br/>ふりかえる</h1>

</br>

Speaker：nogu（@_nogu66）

2025年12月13日(土) Japan AI 大忘年会 2025

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

# <span class="accent">今日のアジェンダ</span>

<div class="tegxt-left text-2xl mt-12 ml-8">

1. **Claude Codeの概要**

2. **2025年の振り返り**

3. **主要な機能**

4. **Hooks**

5. **Subagents**

6. **Skills**

</div>

---

# <span class="accent">Claude Codeとは？</span>

Anthropicが提供する<span class="accent">エージェントティック・コーディング</span>を実現するコマンドラインツール。

自然言語でのタスク指示から、コードベース全体を理解し、<span class="accent">自律的にタスクを遂行。</span>

開発者が使い慣れたIDEやターミナルから離れることなくAIの能力を最大限に活用。

<img src="./images/claude-code.png" alt="Claude  Code" class="mx-auto h-70 mt-8" />

---

# <span class="accent">Claude Code 2025年</span>を振り返ろう

<img src="./images/claude-code-timeline.png" alt="タイムライン" class="mx-auto h-60 mt-24" />

---


# 主要な機能

<div class="text-xl mt-8 space-y-8">

### <span class="accent">1. Hooks</span>

イベントに応じて自動実行されるシェルコマンド
開発フローを自動化し、効率を向上

### <span class="accent">2. Subagents</span>

独自のコンテキストウィンドウ、カスタムシステムプロンプト、および特定のツール権限を備えたAIアシスタント

### <span class="accent">3. Agent Skills</span>

Claudeがタスクに関連するタイミングで動的に検出・読み込みする指示、スクリプト、リソースを含むフォルダ

</div>

---
layout: center
---

# では、本題へ

<h1 class="text-3xl accent font-bold mt-8">
Hooks、Subagents、Skills をどう使うか？
</h1>

---
layout: two-cols
---

# <span class="accent">Hooks とは</span>

**特定のイベントが発生した際に自動的に実行されるカスタムシェルコマンド**

<div class="text-left">

##### 特徴
- イベントドリブンな自動化（ツール実行の前後など）
- 設定ファイルで簡単にカスタマイズ可能
- 開発ワークフローへのシームレスな統合

<br>

##### 使用例
- コミット前のlint/format自動実行
- ファイル変更時の自動テスト実行
- セキュリティチェックの自動実行

</div>

::right::

<img src="./images/hooks.png" alt="Hooks" class="mx-auto h-100" />

---

<div>

# <span class="accent">Hooksの設定方法</span>

<span class="accen mt">.claude/settings.json</span>でイベントごとにコマンドを定義

<div class="mt-8">
```json
{
  "hooks": {
    "PreToolUse": [
      {
        "matcher": "Write",
        "hooks": [
          {
            "type": "command",
            "command": "your-command-here"
          }
        ]
      }
    ]
  }
}
```
</div>

</div>


---

# <span class="accent">Subagents とは</span>

**特定の種類のタスクを処理するために呼び出すことができる特化したAIアシスタント**

<div class="text-left">

#### 特徴
- 特定タスクに最適化された専門エージェント
- 独立したコンテキストで動作（メインのコンテキストを汚染しない）
- タスク完了後は自動的に終了し、リソースを解放
- Task toolを使って呼び出す
- <span class="accent">(New)非同期モード追加</span>

<br>

#### 使用例
- コードレビュー（code-reviewer）
- テスト実行・修正（test-writer-fixer）`

</div>

---

# <span class="accent">SubAgentsの本質: 独立したタスク実行環境</span>

<img src="./images/subagents-diagram.png" alt="Subagents" class="mx-auto mt-8 h-100" />

---

# <span class="accent">Agent Skills とは</span>

**再利用可能な専門知識パッケージ**

タスクに関連するタイミングで動的に検出・読み込みされる指示、スクリプト、リソースを含むフォルダ

<div class="text-left">

#### 特徴
- 特定のドメイン知識を保持する永続的なパッケージ
- ベストプラクティスとガイドラインが組み込まれている
- 繰り返し使用でき、継続的に改善可能
- プロジェクトやグローバルレベルで管理

<br/>

#### 使用例
- Slidevプレゼン作成（slidev-writer）
- Zenn記事執筆（zenn-article-writer）
- PDF処理（pdf）
- Excel操作（xlsx）

</div>

---

# <span class="accent">Skillsの段階的な開示</span>

<img src="./images/skills-progressive-disclosure.png" alt="Agent+Skills+Computer" class="mx-auto h-110" />


---

# <span class="accent">なぜSkillsが優れているのか？</span>

#### エージェント（Claude Codeなど）は、非常に優秀な「知性」や「能力」を持っている。

#### <span class="accent">実際の作業に必要な専門知識（expertise）</span>が常に備わっているわけではない。

<br/>

#### スキルは、この<span class="accent">ギャップを埋める</span>ために作成されました。

---

# <span class="accent">機能同士の連携</span>

<div class="text-left text-xl mt-8">

### Hooks、Subagents、Skillsは<span class="accent">独立した機能ではない</span>

<div class="mt-6 space-y-4s">

**Subagents + Skills**
- SubagentがSkillsを読み込んで専門知識を活用

**Subagents + Hooks**
- Subagent実行の前後でHooksが自動実行

**Subagents + Skills + Hooks**
- SubagentがSkillsを使ってタスク実行
- 完了時にHooksで自動チェック
</div>

<br/>

### <span class="accent">→ 連携することで、1 + 1 + 1 が 3 以上の価値を生む</span>

</div>

---

# <span class="accent">3つのSubAgentが単一のSkillsを共有する研究エージェント</span>

<img src="./images/research-agent-example.png" alt="研究エージェント" class="mx-auto h-100" />


---

# <span class="accent">具体例で理解しよう</span>

<img src="./images/claude_code_workflow.png" alt="Subagents + Skills + Hooks" class="mx-auto h-100" />

---

# <span class="accent">この組み合わせの利点</span>

<div class="text-left text-xl space-y-6 mt-8">

### 1. <span class="accent">効率性</span>
SubAgentの並列実行で作業時間を短縮

### 2. <span class="accent">品質保証</span>
Hooksによる自動チェックで人的ミスを防止

### 3. <span class="accent">一貫性</span>
Skillsで毎回同じクオリティを保証

### 4. <span class="accent">スケーラビリティ</span>
同じパターンで複数プロジェクトに適用可能

</div>

---

# <span class="accent">エコシステムの比較</span>

<img src="./images/feature-comparison-table.png" alt="機能比較" class="mx-auto h-110" />

---

# <span class="accent">まとめ</span>

<div class="text-left text-2xl space-y-6 mt-8">

### 1. <span class="accent">Hooksで開発フローを自動化</span>
イベント駆動で品質チェックやテストを自動実行

### 2. <span class="accent">Subagentsで専門タスクを分離</span>
独立したコンテキストで効率的にタスクを処理

### 3. <span class="accent">Skillsで専門知識を再利用</span>
一度作れば何度でも活用できる知識パッケージ

### 4. <span class="accent">実践で学ぶことが最重要</span>
理論より、実際に使って体感することで深く理解できる

</div>

---

# <span class="accent">公式ブログは読んだ方がいい！</span>

<img src="./images/claude-blog.png" alt="ブログ" class="mx-auto h-115" />

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
