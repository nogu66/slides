---
theme: default
background: https://images.unsplash.com/photo-1451187580459-43490279c0fa?w=1920
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Claude Skills: Building Blocks for AI Workflows
  AIワークフローを効率化する再利用可能な専門知識
drawings:
  persist: false
transition: slide-left
title: Claude Skills - AIワークフローの構成要素
mdc: true
---

# Claude Skills

AIワークフローを効率化する<br>再利用可能な専門知識

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

---
layout: center
---

# こんにちは、noguです

<div class="flex items-center justify-center gap-8 mt-8">
  <div class="text-left">
    <div class="text-xl mb-4">
      <carbon:logo-x class="inline text-blue-400"/> X (Twitter)
    </div>
    <div class="text-2xl font-bold text-blue-400">
      @_nogu66
    </div>
    <div class="mt-4 text-gray-400">
      https://x.com/_nogu66
    </div>
  </div>
</div>

---
layout: center
---

# 今日のアジェンダ

<v-clicks>

1. <carbon:warning class="inline text-yellow-400"/> **問題提起** - AIエージェントとの非効率なやりとり
2. <carbon:lightbulb class="inline text-blue-400"/> **解決策** - Claude Skillsとは何か
3. <carbon:tools class="inline text-green-400"/> **エコシステム** - 他のツールとの違い
4. <carbon:rocket class="inline text-purple-400"/> **実践例** - 複数ツールを組み合わせた活用法

</v-clicks>

---
layout: center
class: text-center
---

# こんな経験ありませんか？

<v-clicks>

<div class="text-left max-w-3xl mx-auto mt-8 space-y-6">

😫 毎回Claudeに同じ説明を繰り返している

💭 「このプロジェクトではこの規約に従ってください...」

📝 データ分析の手順を何度も指示している

📋 ブランドガイドラインを会話のたびに伝えている

</div>

</v-clicks>

---
layout: fact
---

# 時間の無駄

説明の一貫性も保てない

---
layout: center
---

# 既存のツールでは不十分

<div class="grid grid-cols-2 gap-8 mt-8">

<div v-click>

### <carbon:chat class="inline text-blue-400"/> Prompts

✅ 会話に指示を与えられる

❌ 1つの会話だけに有効

</div>

<div v-click>

### <carbon:folder class="inline text-green-400"/> Projects

✅ 永続的なコンテキスト

❌ プロジェクトをまたげない

</div>

</div>

<div v-click class="mt-12 text-2xl font-bold text-center">
<carbon:arrow-down class="inline"/> もっと良い解決策が必要
</div>

---
layout: cover
background: https://images.unsplash.com/photo-1558494949-ef010cbdcc31?w=1920
---

# Claude Skills

専門知識をポータブルに<br>パッケージ化する仕組み

---
layout: two-cols
---

# Claude Skillsとは

<div class="mt-8">

特定のドメインに関する<br>**指示・スクリプト・リソース**<br>をまとめた専門知識フォルダー

<v-click>

Claudeが関連性のある<br>Skillsを**動的に発見・ロード**

</v-click>

</div>

::right::

<v-click>

```
.claude/
└── skills/
    └── excel-expert/
        ├── SKILL.md
        ├── templates/
        └── examples/
```

</v-click>

<v-click>

<div class="mt-8 p-4 bg-blue-900 bg-opacity-30 rounded">

💡 必要なときだけロード<br>
🔄 すべての会話で再利用<br>
📦 ポータブルで共有可能

</div>

</v-click>

---
layout: center
---

# Skillsの3つの特徴

<div class="grid grid-cols-3 gap-6 mt-12">

<v-click>
<div class="p-6 bg-gradient-to-br from-blue-500 to-blue-700 rounded-lg">
  <div class="text-4xl mb-4">📊</div>
  <div class="font-bold text-xl mb-2">Progressive Disclosure</div>
  <div class="text-sm">メタデータ先読み<br>必要なときだけ全体をロード</div>
</div>
</v-click>

<v-click>
<div class="p-6 bg-gradient-to-br from-green-500 to-green-700 rounded-lg">
  <div class="text-4xl mb-4">⚡</div>
  <div class="font-bold text-xl mb-2">Dynamic Loading</div>
  <div class="text-sm">関連するSkillsだけ<br>自動的に有効化</div>
</div>
</v-click>

<v-click>
<div class="p-6 bg-gradient-to-br from-purple-500 to-purple-700 rounded-lg">
  <div class="text-4xl mb-4">♻️</div>
  <div class="font-bold text-xl mb-2">Reusable Expertise</div>
  <div class="text-sm">会話・プロジェクト<br>をまたいで再利用</div>
</div>
</v-click>

</div>

---
layout: center
---

# なぜSkillsが必要なのか

<div class="grid grid-cols-3 gap-8 mt-12">

<v-click>
<div class="text-center">
  <div class="text-5xl mb-4">🏢</div>
  <div class="font-bold text-lg mb-3">組織の手順</div>
  <div class="text-sm text-gray-300">
    • コンプライアンス<br>
    • ブランド標準<br>
    • 文書テンプレート
  </div>
</div>
</v-click>

<v-click>
<div class="text-center">
  <div class="text-5xl mb-4">🔬</div>
  <div class="font-bold text-lg mb-3">専門知識</div>
  <div class="text-sm text-gray-300">
    • データ分析手法<br>
    • PDF操作<br>
    • フレームワーク
  </div>
</div>
</v-click>

<v-click>
<div class="text-center">
  <div class="text-5xl mb-4">⚙️</div>
  <div class="font-bold text-lg mb-3">個人ワークフロー</div>
  <div class="text-sm text-gray-300">
    • ノート取り<br>
    • コーディング規約<br>
    • タスク管理
  </div>
</div>
</v-click>

</div>

---
layout: center
---

# Skillの実装例

````md magic-move
```markdown
# Excel Expert Skill

## Description
Provides expertise in Excel analysis

## When to Use
- Analyzing spreadsheet data
- Creating complex formulas
```

```markdown
# Excel Expert Skill

## Description
Provides expertise in Excel analysis

## When to Use
- Analyzing spreadsheet data
- Creating complex formulas
- Generating reports from Excel files

## Instructions
When working with Excel files:
1. Always validate data types
2. Use VLOOKUP for cross-referencing
3. Apply conditional formatting
```

```markdown
# Excel Expert Skill

## Description
Provides expertise in Excel analysis

## When to Use
- Analyzing spreadsheet data
- Creating complex formulas
- Generating reports from Excel files

## Instructions
When working with Excel files:
1. Always validate data types
2. Use VLOOKUP for cross-referencing
3. Apply conditional formatting

## Templates
- Monthly report template
- Data validation rules
```
````

<v-click>

<div class="mt-8 text-center text-xl">
<carbon:checkmark class="inline text-green-400"/> Claudeが自動的に関連タスクを検出してロード
</div>

</v-click>

---
layout: center
---

# Claudeエコシステム

<div class="mt-8">

| ツール | 目的 | 永続性 |
|--------|------|--------|
| **Prompts** | 会話の指示 | 単一の会話 |
| **Projects** | コンテキストワークスペース | プロジェクト内 |
| **Subagents** | タスク委譲 | セッションベース |
| **Skills** | 再利用可能な専門知識 | **すべての会話** |
| **MCP** | 外部ツール接続 | 継続的アクセス |

</div>

<v-click>

<div class="mt-8 text-center text-xl font-bold">
それぞれ異なる役割を持つ<br>
<span class="text-blue-400">組み合わせることで真の力を発揮</span>
</div>

</v-click>

---
layout: two-cols
---

# Skills vs MCP

<div class="mt-8">

<v-click>

### <carbon:education class="inline text-blue-400"/> Skills

**「方法」を教える**

- Excelレポートの<br>フォーマット方法
- 数式の使い方
- ベストプラクティス

</v-click>

</div>

::right::

<div class="mt-8">

<v-click>

### <carbon:connect class="inline text-green-400"/> MCP

**「アクセス」を提供**

- 実際のファイルへの<br>アクセス
- Google Drive接続
- GitHub連携

</v-click>

</div>

---

<v-click>

<div class="mt-12 p-6 bg-gradient-to-r from-blue-500 to-green-500 bg-opacity-20 rounded-lg text-center">
  <div class="text-2xl font-bold">
    Skillsは「どのようにやるか」を教え<br>
    MCPは「何にアクセスするか」を可能にする
  </div>
  <div class="mt-4 text-gray-300">
    両者は補完的な関係
  </div>
</div>

</v-click>

---
layout: two-cols
---

# Skills vs Subagents

<div class="mt-8">

<v-click>

### <carbon:book class="inline text-purple-400"/> Skills

**知識の提供**

ポータブルな専門知識

<div class="mt-4 text-sm">
例:
- データ分析の手法
- コーディング規約
</div>

</v-click>

</div>

::right::

<div class="mt-8">

<v-click>

### <carbon:rocket class="inline text-orange-400"/> Subagents

**タスクの実行**

独立したワークフロー

<div class="mt-4 text-sm">
例:
- データ収集から分析まで<br>
  全体を実行
</div>

</v-click>

</div>

---
layout: center
class: text-center
---

# 実践例

複数ツールを組み合わせた<br>**研究エージェント**

---
layout: center
---

# 研究エージェントの構成

<div class="grid grid-cols-2 gap-6 mt-8">

<v-click>
<div class="p-4 bg-blue-900 bg-opacity-30 rounded">
  <div class="font-bold text-lg mb-2"><carbon:folder class="inline"/> Project</div>
  <div class="text-sm">研究テーマの背景知識<br>過去の会話履歴</div>
</div>
</v-click>

<v-click>
<div class="p-4 bg-green-900 bg-opacity-30 rounded">
  <div class="font-bold text-lg mb-2"><carbon:connect class="inline"/> MCP</div>
  <div class="text-sm">Google Drive<br>GitHubリポジトリ</div>
</div>
</v-click>

<v-click>
<div class="p-4 bg-purple-900 bg-opacity-30 rounded">
  <div class="font-bold text-lg mb-2"><carbon:education class="inline"/> Skills</div>
  <div class="text-sm">分析フレームワーク<br>レポートテンプレート</div>
</div>
</v-click>

<v-click>
<div class="p-4 bg-orange-900 bg-opacity-30 rounded">
  <div class="font-bold text-lg mb-2"><carbon:rocket class="inline"/> Subagents</div>
  <div class="text-sm">文献調査<br>データ分析</div>
</div>
</v-click>

</div>

---
layout: center
---

# ワークフローの流れ

<v-clicks>

<div class="space-y-4 mt-8 text-left max-w-3xl mx-auto">

<div class="flex items-center gap-4">
  <div class="text-3xl">1️⃣</div>
  <div>ユーザーが研究テーマについて質問</div>
</div>

<div class="flex items-center gap-4">
  <div class="text-3xl">2️⃣</div>
  <div><span class="text-blue-400 font-bold">Project</span>から背景知識がロード</div>
</div>

<div class="flex items-center gap-4">
  <div class="text-3xl">3️⃣</div>
  <div><span class="text-purple-400 font-bold">分析Skill</span>が自動的に有効化</div>
</div>

<div class="flex items-center gap-4">
  <div class="text-3xl">4️⃣</div>
  <div><span class="text-green-400 font-bold">MCP</span>経由でGoogle Driveから文書取得</div>
</div>

<div class="flex items-center gap-4">
  <div class="text-3xl">5️⃣</div>
  <div><span class="text-orange-400 font-bold">Subagent</span>が文献調査を実行</div>
</div>

<div class="flex items-center gap-4">
  <div class="text-3xl">6️⃣</div>
  <div><span class="text-purple-400 font-bold">レポートSkill</span>のテンプレートで結果をまとめ</div>
</div>

</div>

</v-clicks>

---
layout: fact
---

# 個別のツールを超えた

強力なワークフローを実現

---
layout: center
---

# 実際に使ってみた結果

<div class="grid grid-cols-3 gap-6 mt-12">

<v-click>
<div class="text-center">
  <div class="text-5xl mb-4">⏱️</div>
  <div class="font-bold text-2xl mb-2">5〜10分</div>
  <div class="text-sm text-gray-300">1タスクあたりの<br>時間削減</div>
</div>
</v-click>

<v-click>
<div class="text-center">
  <div class="text-5xl mb-4">✅</div>
  <div class="font-bold text-2xl mb-2">一貫性向上</div>
  <div class="text-sm text-gray-300">規約・形式が<br>自動適用</div>
</div>
</v-click>

<v-click>
<div class="text-center">
  <div class="text-5xl mb-4">♻️</div>
  <div class="font-bold text-2xl mb-2">知識の蓄積</div>
  <div class="text-sm text-gray-300">複数プロジェクトで<br>専門知識を活用</div>
</div>
</v-click>

</div>

---
layout: center
---

# 直面した課題と解決方法

<v-clicks>

<div class="space-y-6 mt-8 max-w-3xl mx-auto">

<div class="p-4 bg-red-900 bg-opacity-20 rounded">
  <div class="font-bold text-lg mb-2"><carbon:warning class="inline text-yellow-400"/> 課題1: どのSkillが使われているか分からない</div>
  <div class="text-sm text-gray-300">
    <carbon:checkmark class="inline text-green-400"/> 解決: メタデータに明確な「When to Use」を記述<br>
    <carbon:checkmark class="inline text-green-400"/> 具体的なトリガー条件を記載
  </div>
</div>

<div class="p-4 bg-red-900 bg-opacity-20 rounded">
  <div class="font-bold text-lg mb-2"><carbon:warning class="inline text-yellow-400"/> 課題2: Skillの内容が古くなる</div>
  <div class="text-sm text-gray-300">
    <carbon:checkmark class="inline text-green-400"/> 解決: 定期的にレビューする習慣<br>
    <carbon:checkmark class="inline text-green-400"/> Gitでバージョン管理
  </div>
</div>

</div>

</v-clicks>

---
layout: center
---

# 効果的に使うためのポイント

<div class="grid grid-cols-3 gap-6 mt-12">

<v-click>
<div class="p-6 bg-blue-900 bg-opacity-30 rounded-lg">
  <div class="text-3xl mb-4">🎯</div>
  <div class="font-bold mb-2">具体的な条件</div>
  <div class="text-sm text-gray-300">
    抽象的な説明を避け<br>
    具体的なトリガーを定義
  </div>
</div>
</v-click>

<v-click>
<div class="p-6 bg-green-900 bg-opacity-30 rounded-lg">
  <div class="text-3xl mb-4">📏</div>
  <div class="font-bold mb-2">5,000トークン以内</div>
  <div class="text-sm text-gray-300">
    本当に必要な<br>
    情報だけを含める
  </div>
</div>
</v-click>

<v-click>
<div class="p-6 bg-purple-900 bg-opacity-30 rounded-lg">
  <div class="text-3xl mb-4">🔗</div>
  <div class="font-bold mb-2">MCPと組み合わせ</div>
  <div class="text-sm text-gray-300">
    知識とアクセスを<br>
    組み合わせて真の力を
  </div>
</div>
</v-click>

</div>

---
layout: center
---

# 重要なポイント（まとめ）

<v-clicks>

<div class="space-y-6 mt-8 max-w-3xl mx-auto text-left text-lg">

<div class="flex items-start gap-4">
  <div class="text-3xl">1️⃣</div>
  <div>
    <span class="font-bold text-blue-400">Skillsは専門知識を再利用可能にする</span><br>
    <span class="text-sm text-gray-300">毎回同じ説明をする必要がなくなる</span>
  </div>
</div>

<div class="flex items-start gap-4">
  <div class="text-3xl">2️⃣</div>
  <div>
    <span class="font-bold text-green-400">他のツールと補完的に機能する</span><br>
    <span class="text-sm text-gray-300">Prompts、Projects、MCP、Subagentsと組み合わせて強力に</span>
  </div>
</div>

<div class="flex items-start gap-4">
  <div class="text-3xl">3️⃣</div>
  <div>
    <span class="font-bold text-purple-400">効率的なAIワークフローを構築できる</span><br>
    <span class="text-sm text-gray-300">時間削減、一貫性向上、知識の蓄積を実現</span>
  </div>
</div>

</div>

</v-clicks>

---
layout: center
---

# 今すぐ始めるには

<v-clicks>

<div class="space-y-4 mt-8 max-w-2xl mx-auto text-left">

<div class="flex items-center gap-4 p-4 bg-blue-900 bg-opacity-30 rounded">
  <div class="text-2xl font-bold text-blue-400">1</div>
  <div><code>.claude/skills/</code>ディレクトリを作成</div>
</div>

<div class="flex items-center gap-4 p-4 bg-green-900 bg-opacity-30 rounded">
  <div class="text-2xl font-bold text-green-400">2</div>
  <div>最初のSkillフォルダーを作成（例: <code>excel-expert</code>）</div>
</div>

<div class="flex items-center gap-4 p-4 bg-purple-900 bg-opacity-30 rounded">
  <div class="text-2xl font-bold text-purple-400">3</div>
  <div><code>SKILL.md</code>ファイルに説明と指示を記述</div>
</div>

<div class="flex items-center gap-4 p-4 bg-orange-900 bg-opacity-30 rounded">
  <div class="text-2xl font-bold text-orange-400">4</div>
  <div>Claudeを使ってSkillが適切にロードされるか確認</div>
</div>

</div>

</v-clicks>

---
layout: cover
background: https://images.unsplash.com/photo-1519389950473-47ba0277781c?w=1920
---

# ありがとうございました！

Skillsを使って<br>AIワークフローをさらに効率化しましょう

---
layout: center
---

# 詳しくは記事をチェック

<div class="mt-8 text-center">

<div class="text-xl mb-8">
  📝 **Zenn記事で詳細を解説**
</div>

<div class="p-6 bg-gradient-to-r from-blue-500 to-purple-500 bg-opacity-20 rounded-lg max-w-2xl mx-auto">
  <div class="font-bold text-2xl mb-4">
    AIワークフローの複雑化を<br>Claude Skillsで解決する
  </div>
  <div class="text-sm text-gray-300 mb-4">
    • 詳細な実装例<br>
    • トラブルシューティング<br>
    • より深い技術解説
  </div>
  <div class="text-blue-400">
    zenn.dev で公開予定
  </div>
</div>

</div>

---
layout: end
---

# フォローお願いします！

<div class="text-center mt-12">
  <div class="text-3xl mb-4">
    <carbon:logo-x class="inline text-blue-400"/> X (Twitter)
  </div>
  <div class="text-4xl font-bold text-blue-400 mb-8">
    @_nogu66
  </div>
  <div class="text-xl text-gray-400">
    https://x.com/_nogu66
  </div>
</div>

<div class="mt-12 text-center text-gray-400">
  この記事が役に立ったら、フォローしていただけると嬉しいです！
</div>
