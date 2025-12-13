# 画像フォルダ

このフォルダにプレゼンテーションで使用する画像を保存してください。

## 使い方

### 1. 画像を保存
このフォルダに画像ファイルを保存します。
例: `screenshot.png`, `diagram.jpg`, `logo.svg`

### 2. スライドで参照

```markdown
# 画像を含むスライド

![説明文](/images/screenshot.png)

<!-- または -->

<img src="/images/screenshot.png" alt="説明文" class="mx-auto w-100" />
```

### 3. 背景画像として使用

```markdown
---
layout: image
image: /images/background.jpg
---

# コンテンツ
```

### 4. 2カラムレイアウトで使用

```markdown
---
layout: image-right
image: /images/diagram.png
---

# 左側のコンテンツ

右側に画像が表示されます
```

## パス指定

- **正しい**: `/images/filename.png` (先頭にスラッシュ)
- **間違い**: `images/filename.png` または `./images/filename.png`

publicフォルダ内のファイルは、ルートパス(`/`)からアクセスします。
