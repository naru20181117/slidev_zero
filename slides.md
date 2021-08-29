---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
---

# プレゼン資料使い捨てはMOTTAINAI【エンジニア用のスライド比較】


---
## 結論

個人ブログをプレゼン用に
アレンジしたら良かった話

---

### ターゲット

- LTが好きなエンジニア
- 情報発信をよくするジニア
- 自分の活動をストック型にしたいジニア

---

### 筆者経験

- [LT会の主催者](https://tonihome.connpass.com/)
- これまでQiitaを使ってLTをしてきた

https://qiita.com/naruqiita/items/7888b931beeaaa6b39e7

---

### 理由

```
LT会に参加して見られる良い資料の多くは
　その場でしか拝見できずもったいないと思っていた
Qiitaのスライドモードを使うことによって
　資料を記事として残せる！
```

---

## まだもったいない？

- Qiitaのスライドモード
    - 正直いうと自由度が低い
- 文字の拡大や配置を自由にしたい
- アニメーションもつけたいな

---

#### 例

![スクリーンショット 2021-08-28 20.11.28.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/498701/22706097-2718-7314-b93f-697eafca2f17.png)

---

### 自分でスライドを実装したい

![](https://4.bp.blogspot.com/-6nucQQvGF7M/WzC-BHQmAHI/AAAAAAABM90/mCILacrOAq8IqccOnH1U_umcAD56flJnQCLcBGAs/s800/yaruki_moeru_man.png)

---

### 比較URL
この記事を参考にあまり手を加えずに比較してみる

|技術|URL|
|:-:|:-:|
|Qiita|[Qiitaスライド記事](https://qiita.com/naruqiita/items/78afe211b66c44894f5d)|
|reveal.js|[ブログに付属させたサイト](https://naruhero-blog-slide.netlify.app/?entry_id=2JPpN7S7eEDa0KcVxsBI87)|
|Slidev|url|

---

#### やりたかったこと

**背景**
個人ブログをNuxt ✖️ Contentful(マークダウン)で作っている

- マークダウンで書けるスライドが欲しい
- ContentfulのAPIを使って可変的なページでスライドを表示したい

http://naruhero.site/

---

### Slidevでやってやりたかった

<Tweet id="1430131406961659908"/>

---

### [Slidev](https://sli.dev/)とは

- 2021年5月に発表
- マークダウンで書けるプレゼンテーションツール
- `npm init slidev`だけで始められるオープンソース
- devという名前が入っているように開発者向け
- Vite、Vue3、WindiCSSで作られる

---

### メリット

- 1コマンドで雛形が作れ、編集すればプレゼン資料が完成する手頃さ
- オンライン発表に合わせたプレゼンターモードやインカメラ機能など
- 録画機能付きでアドリブが苦手な人にも優しい

---

### ビデオでの例

[![](https://img.youtube.com/vi/eW7v-2ZKZOU/0.jpg)](https://www.youtube.com/watch?v=eW7v-2ZKZOU)

詳しくは[こちら](https://zenn.dev/ryo_kawamata/articles/introduce-slidev)

---

### 今回選ばなかった理由

- 個人用カスタマイズ性が低い
    - スライド1種類に対して1回buildが必要
        - つまり変更があるたびにbuild必要
    - `APIでデータ渡す→スライド表示`が難しい
- サクッとつくれない（拘る場合）
    - 開発期間3日ほどしかなかった
    - リッチに作れるのが良いことだが作り込みが必要

---

### 選ばれたのは`reveal.js`でした

![Wvu5ArxeXuQ9LWk1630156982_1630157343.jpg](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/498701/8bf2acdc-783a-be13-6eff-f0ae7f0150f5.jpeg)

---

### [reveal.js](https://revealjs.com/)とは

HTMLプレゼンテーションフレームワーク
マークダウンでも対応をしている
dependencyとして既存アプリにインストールして使える
![revealjs.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/498701/f4484e7b-abdd-0362-3bdb-da83d1362bb8.png)
[参考](https://revealjs.com/installation/#installing-from-npm)

---

### データ構成

![データ構成.gif](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/498701/e8d68e2b-80e6-6b22-2583-b4aac96b890e.gif)

---

#### 悔しいポイント

`ContentfulのMD(マークダウン)`→`reveal.jsのMD読み込み`はできなかった
[参考](https://github.com/hakimel/reveal.js/blob/master/plugin/markdown/plugin.js#L37)

`ContentfulのMD`→`VueでのMDをHTMLに変換`→`reveal.jsへ読み込み`
この実装によりContentfulに内蔵されたHTMLの表示がバグる🤮

---

#### 余談

正直マークダウンに拘らなければ
[Speaker Deck](https://speakerdeck.com/)も良い

- パワポなどで作った資料をアップロードするだけ
- SlideShareを使って簡単に埋め込みもできる

---

### 実際に見てみる

http://naruhero.site/blog/6/

※アップデートしていくため見た目が変わる可能性あり

---

#### 補足

- Slidevも作られたばかりで毎日のようにアップデートされている
    - 今後の変更によってはbuildをしないようなAPI構成もありえるかも
- Twitterの埋め込みなど対応していないことが少し目立つ

---

## 結論

記事とスライド作成を手軽に作成したいなら[Qiita](https://qiita.com/Qiita/items/4ff5873776992f0511d6)
マークダウンでリッチに書きたいだけなら[Slidev](https://sli.dev/)
マークダウンで書いてカスタマイズもできるようにするなら[Reveal.js](https://revealjs.com/)
