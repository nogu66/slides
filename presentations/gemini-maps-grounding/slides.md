---
theme: default
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
  ## Gemini API Google Maps Grounding
  位置情報認識AI応答を実現する新機能
drawings:
  persist: false
transition: slide-left
title: Gemini APIのGoogle Maps Grounding
mdc: true
---

# Gemini APIの<br/>Google Maps Grounding

位置情報認識AI応答を実現する

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

---
layout: center
---

# 自己紹介

<div class="text-left">

こんにちは、**nogu**です。

<div class="mt-8">

- AI開発ツールとモバイル開発に興味があります
- X (Twitter): [@_nogu66](https://x.com/_nogu66)

</div>

</div>

---
layout: center
---

# アジェンダ

<v-clicks>

1. 問題: AIの位置情報応答の課題
2. 解決策: Google Maps Grounding
3. 実装方法とコード例
4. 実践的なユースケース
5. 重要なポイントとまとめ

</v-clicks>

---
layout: center
---

# こんな経験ありませんか？

<v-clicks>

- AIに「近くのおすすめカフェは?」と聞いても古い情報が返ってくる
- 店舗の営業時間や電話番号が不正確
- 情報のソースが不明で信頼性を確認できない
- ユーザーの現在地に基づいた適切な提案ができない

</v-clicks>

<v-click>

<div class="mt-8 text-center text-xl text-red-400">
位置情報ベースのAIアプリ開発が困難...
</div>

</v-click>

---
layout: two-cols
---

# 従来のAIの課題

<v-clicks>

### 情報の鮮度
学習データの時点での情報のみ

### 情報の精度
詳細な住所や評価が不正確

### 検証可能性
回答のソースが不明確

### パーソナライゼーション
現在地ベースの提案不可

</v-clicks>

::right::

<v-click>

# 影響

<div class="mt-8">

開発が困難なアプリケーション:

- 旅行プランナー
- ローカルガイド
- レストラン推薦
- 位置情報チャットボット

</div>

</v-click>

---
layout: center
class: text-center
---

# 解決策

<div class="text-6xl font-bold text-gradient">
Google Maps Grounding
</div>

<div class="mt-8 text-2xl">
Gemini APIとGoogle Mapsデータの統合
</div>

---
layout: default
---

# Google Maps Groundingとは

Gemini APIの生成能力とGoogle Mapsの豊富なデータを統合する機能

<v-clicks>

## 主な特徴

- <carbon:location class="text-blue-500"/> **正確な位置情報**: 2億5,000万以上の場所データベース
- <carbon:user-avatar class="text-green-500"/> **パーソナライゼーション**: ユーザー位置に基づく推薦
- <carbon:map class="text-purple-500"/> **インタラクティブウィジェット**: Google Maps埋め込み対応
- <carbon:document class="text-orange-500"/> **検証可能なソース**: Google Mapsリンク付き引用

</v-clicks>

---
layout: two-cols
---

# 実装は簡単

<div class="text-sm">

```python {all|6|7-10|all}
from google import genai
from google.genai import types

client = genai.Client()

response = client.models.generate_content(
    model='gemini-2.5-flash-lite',
    contents="近くのイタリアンは?",
    config=types.GenerateContentConfig(
        # Maps Groundingを有効化
        tools=[types.Tool(
            google_maps=types.GoogleMaps()
        )],
        # 位置情報を提供
        tool_config=types.ToolConfig(
            retrieval_config=types.RetrievalConfig(
                lat_lng=types.LatLng(
                    latitude=35.6812,
                    longitude=139.7671
                )
            )
        ),
    ),
)
```

</div>

::right::

<v-click>

# ポイント

<div class="mt-16">

1. **ツールの有効化**
   `google_maps=types.GoogleMaps()`

2. **位置情報の指定**
   `lat_lng` パラメータ（推奨）

3. **ソース情報の取得**
   `grounding_metadata` に含まれる

</div>

</v-click>

---
layout: default
---

# JavaScriptでの実装

```javascript {all|8|9-14|all}
import { GoogleGenAI } from "@google/gnai";

const ai = new GoogleGenAI({});

const response = await ai.models.generateContent({
  model: "gemini-2.5-flash",
  contents: "What are the best Italian restaurants nearby?",
  config: {
    // Google Maps Groundingを有効化
    tools: [{ googleMaps: {} }],
    toolConfig: {
      retrievalConfig: {
        latLng: {
          latitude: 35.6812,
          longitude: 139.7671,
        },
      },
    },
  },
});
```

---
layout: default
---

# ソース情報の取得

レスポンスには `groundingMetadata` が含まれる

```python
# ソース情報の表示
if grounding := response.candidates[0].grounding_metadata:
    if grounding.grounding_chunks:
        print("Sources:")
        for chunk in grounding.grounding_chunks:
            print(f'- [{chunk.maps.title}]({chunk.maps.uri})')
```

<v-click>

<div class="mt-8">

### 出力例

```
Sources:
- [Heaven on 7th Marketplace](https://maps.google.com/?cid=...) - Google Maps
- [Bella Italia](https://maps.google.com/?cid=...) - Google Maps
```

</div>

</v-click>

---
layout: center
---

# Google Mapsウィジェット

より豊かなUXを提供

````md magic-move
```python
# 基本的な実装
tools=[types.Tool(google_maps=types.GoogleMaps())]
```

```python
# ウィジェットを有効化
tools=[types.Tool(
    google_maps=types.GoogleMaps(enable_widget=True)
)]
```

```python
# ウィジェット用トークンの取得
if grounding := response.candidates[0].grounding_metadata:
    if widget_token := grounding.google_maps_widget_context_token:
        print(f'<gmp-place-contextual context-token="{widget_token}"></gmp-place-contextual>')
```
````

---
layout: default
---

# レスポンス構造

```json {all|5-13|14-22|23|all}
{
  "candidates": [{
    "content": { "parts": [{ "text": "..." }] },
    "groundingMetadata": {
      "groundingChunks": [
        {
          "maps": {
            "uri": "https://maps.google.com/?cid=...",
            "title": "Restaurant Name",
            "placeId": "places/ChIJ..."
          }
        }
      ],
      "groundingSupports": [
        {
          "segment": {
            "startIndex": 0,
            "endIndex": 79,
            "text": "..."
          },
          "groundingChunkIndices": [0]
        }
      ],
      "googleMapsWidgetContextToken": "widgetcontent/..."
    }
  }]
}
```

---
layout: center
---

# 実践的なユースケース

<v-clicks>

## 1. 詳細な場所の質問
"1st通りとMain通りの角にあるカフェで外席はある?"

## 2. パーソナライズ推薦
"子供連れに優しいレストランで遊び場の評価が高い所は?"

## 3. 旅行プラン作成
"サンフランシスコで1日のプランを作って"

</v-clicks>

---
layout: two-cols
---

# ユースケース詳細

### 場所の詳細質問

```python
prompt = """
Is there a cafe near the
corner of 1st and Main
that has outdoor seating?
"""

response = client.models.generate_content(
    model='gemini-2.5-flash-lite',
    contents=prompt,
    config=types.GenerateContentConfig(
        tools=[types.Tool(
            google_maps=types.GoogleMaps()
        )],
        tool_config=types.ToolConfig(
            retrieval_config=types.RetrievalConfig(
                lat_lng=types.LatLng(
                    latitude=34.050481,
                    longitude=-118.248526
                )
            )
        ),
    ),
)
```

::right::

<v-click>

### 得られる情報

<div class="mt-16">

- カフェの名前と住所
- 営業時間
- 外席の有無（レビュー情報）
- Google Mapsへのリンク
- レビュー評価

</div>

</v-click>

---
layout: default
---

# 旅行プラン作成の例

```python
prompt = """
Plan a day in San Francisco for me.
I want to see the Golden Gate Bridge, visit a museum,
and have a nice dinner.
"""

response = client.models.generate_content(
    model='gemini-2.5-flash',
    contents=prompt,
    config=types.GenerateContentConfig(
        tools=[types.Tool(google_maps=types.GoogleMaps(enable_widget=True))],
        tool_config=types.ToolConfig(
            retrieval_config=types.RetrievalConfig(
                lat_lng=types.LatLng(latitude=37.78193, longitude=-122.40476)
            )
        ),
    ),
)
```

<v-click>

AIが実際の場所データに基づいた、実用的なプランを生成

</v-click>

---
layout: fact
---

# $25 / 1,000リクエスト

無料枠: 500リクエスト/日

---
layout: default
---

# 料金体系

<v-clicks>

## 課金対象
- グラウンディングされたプロンプト: **$25 / 1,000件**
- 通常のGemini API料金（入出力トークン）も別途発生

## 無料枠
- 1日あたり最大**500件**のリクエスト

## 課金のタイミング
- Google Mapsのソースが含まれる場合のみ課金
- 1リクエスト内の複数クエリは1件としてカウント

</v-clicks>

---
layout: default
---

# 重要な注意点

<v-clicks>

## 1. ソースの帰属表示（必須）

```html
<div class="GMP-attribution">
  <a href="ソースのURI">ソースのタイトル</a> - Google Maps
</div>
```

- Google Mapsのテキストは変更・翻訳不可
- 生成コンテンツの直後に配置

## 2. 禁止地域

中国、クリミア、キューバ、イラン、北朝鮮、シリア、ベトナムなど

## 3. 対応モデル

Gemini 2.5 Flash-Lite、2.5 Pro、2.5 Flash、2.0 Flashのみ

</v-clicks>

---
layout: center
---

# ベストプラクティス

<v-clicks>

## <carbon:location-filled class="text-blue-500"/> 1. 位置情報は常に提供
`latLng` パラメータで最適な結果を取得

## <carbon:settings class="text-green-500"/> 2. 必要な場合のみ有効化
パフォーマンスとコストを最適化

## <carbon:map class="text-purple-500"/> 3. ウィジェットで視覚的体験
`enable_widget=True` で地図を表示

## <carbon:dashboard class="text-orange-500"/> 4. レイテンシのモニタリング
P95レイテンシを監視

</v-clicks>

---
layout: default
---

# 制限事項

<v-clicks>

## モデルサポート
- Gemini 2.5 Flash-Lite、2.5 Pro、2.5 Flash、2.0 Flashのみ
- Lite variantは非対応

## マルチモーダル
- テキストとコンテキストマップウィジェットのみ
- 画像入出力は現在未対応

## デフォルト状態
- デフォルトではオフ
- 明示的に有効化が必要

</v-clicks>

---
layout: center
---

# 重要ポイント

<v-clicks>

## 1. 正確な位置情報
2億5,000万以上の場所データで正確な応答

## 2. 簡単な実装
`tools` パラメータに `googleMaps` を指定するだけ

## 3. パーソナライゼーション
ユーザー位置に基づくカスタマイズ推薦

</v-clicks>

---
layout: center
class: text-center
---

# まとめ

<div class="mt-8">

Google Maps Groundingは<br/>
位置情報ベースのAIアプリ開発における<br/>
大きな課題を解決する強力な機能

</div>

<v-clicks>

<div class="mt-12">

## 今後の可能性

- 会話型旅行プランナー
- 位置情報ベースのパーソナルアシスタント
- ローカルビジネス向けチャットボット
- インテリジェントな推薦システム

</div>

</v-clicks>

---
layout: center
class: text-center
---

# ありがとうございました！

<div class="mt-8">

詳しくは記事をご覧ください

**Gemini APIのGoogle Maps Groundingで位置情報認識AI応答を実現する**

[Zenn記事へ](https://zenn.dev/nogu66/articles/gemini-api-google-maps-grounding)

</div>

<div class="mt-12">

Xをフォローしていただけると嬉しいです！

[@_nogu66](https://x.com/_nogu66)

</div>

---
layout: center
---

# 参考リンク

<div class="text-left mt-8">

- [Google Maps Grounding 公式ドキュメント](https://ai.google.dev/gemini-api/docs/maps-grounding)
- [Gemini API 料金ページ](https://ai.google.dev/gemini-api/docs/pricing)
- [Google Maps JavaScript API](https://developers.google.com/maps/documentation/javascript)

</div>
