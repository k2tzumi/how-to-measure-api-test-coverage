---
theme: seriph
background: https://source.unsplash.com/collection/94734566/1920x1080
class: text-center
highlighter: shiki
lineNumbers: false
info: |
    APIテストにおいてのカバレッジは２つの意味を持ちます。２つのカバレッジについて、それぞれ意味とその取得方法について紹介  

drawings:
  persist: false
transition: slide-left
title: APIテストでもカバレッジ測定したい！
mdc: true
addons:
  - "@katzumi/slidev-addon-qrcode"
  - "slidev-addon-components"
---

# APIテストでもカバレッジ測定したい！
API テストのカバレッジは２つの意味を持つ

[PHPerKaigi 2024](https://phperkaigi.jp/2024/)　March 9, 2024.  
v0.0.1

<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/k2tzumi/how-to-measure-api-test-coverage" target="_blank" alt="GitHub" title="Open in GitHub"
    class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
layout: two-cols-header
---

# 自己紹介

katzumi（かつみ）と申します。

以下のアカウントで活動しています。

::left::

<img src="https://pbs.twimg.com/profile_images/799890486773170176/KN4gKfS2_400x400.jpg" class="rounded-full w-40 mt-16 mr-12　float-left"/>  
<QRCode width="180" height="180" value="https://twitter.com/katzchum" color="4329B9" image="Logo_of_X.svg" />

<simple-icons-x /> [katzchum](https://twitter.com/katzchum)  

::right::

<img src="https://avatars.githubusercontent.com/u/1182787?v=4" class="rounded-full w-40 mt-16 mr-12"/>

<logos-github-octocat /> [k2tzumi](https://github.com/k2tzumi)  
<simple-icons-zenn /> [katzumi](https://zenn.dev/katzumi)  

<br />

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>


---
layout: two-cols-header
transition: fade-out
---

# お願い

写真撮影、SNS での実況について

登壇者の励みになるので是非ともご意見やご感想など、フィードバック頂けると助かります mm  
あとでスライドを公開します

::left::

<Transform :scale="2.5">
　　　🙆‍♀📷<ph-projector-screen-chart-light /><br />
　　　🙅‍♂📹💸<br />
　　　🙅📸👨‍👦‍👦<br />
</Transform>

::right::

<br />
<Transform :scale="2">
<fa6-brands-square-x-twitter />
</Transform>
<br />
<a href="https://twitter.com/search?q=%23phperkaigi%20%23TrackA">#phperkaigi #TrackA</a>

<!-- 本セッションでは、撮影やSNS拡散を歓迎しています。ご自由に写真を撮影して、XなどのSNSでシェアしてください。 　　
ただし、以下の点にご注意ください。　　

著作権などの法的な問題を避けるために、スライドや登壇者の写真や動画を無断で商用利用しないでください。　　
他の参加者のプライバシーや迷惑にならないように、撮影や投稿する際には配慮してください。　　
SNSでシェアする際には、ハッシュタグ「#phperkaigi #TrackA」をつけてください。　　
これにより、本セッションの関連情報を簡単に検索できるようになります。 -->

---
layout: fact
transition: fade-out
---

# APIテスト
# 書いていますか？　✋

---
layout: fact
transition: fade-out
---

# Controllerテスト
# じゃないよ！　

---
layout: fact
transition: fade-out
---

# APIテストは
# いいぞ 👍

---
layout: fact
transition: fade-out
---

# 突然の宣伝！

---
transition: fade-out
layout: two-cols-header
---

# APIシナリオテストを書くべき10の理由
トークしました

::left::


https://www.docswell.com/s/katzumi/5EN8N1-10-reasons-to-write-api-scenario-tests
<img src="https://k2tzumi.github.io/10-reasons-to-write-api-scenario-tests/thumbnail/001.png" class="float-left" />

<QRCode width="80" height="90" value="https://www.docswell.com/s/katzumi/5EN8N1-10-reasons-to-write-api-scenario-tests" color="4329B9" />

::right::

https://youtu.be/iqPsUaqjGGM @YouTube より 
<Youtube id="iqPsUaqjGGM" />

---
layout: center
---

# 伝えたかったこと
他に色々あるけれども..

<img src="https://k2tzumi.github.io/10-reasons-to-write-api-scenario-tests/thumbnail/023.png" class="h90 shadow" />

---
layout: fact
transition: fade-out
---

# APIテストにとって
# カバレッジとは？　🤔

---

# カバレッジとは？　
網羅率。どれだけテストしたかの指標

<blockquote>
<p>ソフトウェアテストで用いられる「カバレッジ(網羅率)」とは対象のプログラム全体のうち、どこまでテストが実施(網羅)されたかを示す割合のことです。</p>
<p>テストを実施する際にカバレッジを測定/分析することでソフトウェアの品質を定量的に評価することができます。</p>
</blockquote>
<a href="https://www.qbook.jp/column/632.html">ソフトウェアテストのカバレッジ(網羅率)とは｜設定するメリット２つと注意点【ソフトウェア開発・テスト用語 】| Qbook</a> より

---
transition: fade-out
---

# APIテストでのテスト観点とは？
単体テストの観点とは違う

1. エンドポイントの API の Spec 通りか？  
    * リクエストが正しく受け付けられるか？  
    * レスポンスが仕様どおりか？  
2. API をチェーンさせて呼び出して期待通りに動くか？  
    * 例えば登録 API を呼び出し、発行（レスポンス）されたコードを使って更新 API が呼ばれること
    * ユースケース観点での動作検証

---
layout: fact
transition: slide-up
---

# APIテストのカバレッジは
# ２つの意味を持つ！
サブタイトル回収

---

# ２つのカバレッジ
テスト観点での優先順位

1. インターフェース上での網羅性
2. ロジック上での網羅性

---

# <material-symbols-counter-1 />インターフェース上での網羅性
エンドポイントに対しての網羅率を見る

* OpenAPI Document に対するカバレッジを取得する  
API 仕様書をテストに組み込む  
テストのリクエスト内容が正しいか？  
レスポンスが仕様書通りか？

---

# <material-symbols-counter-1 />インターフェース上での網羅性
OpenAPI Document に対するカバレッジを取得する

* API シナリオテストツールの runn ならできます！  
  <Transform :scale="0.6">

  ![runn's coverage execution results](runn_coverage.png)

  </Transform>

---
transition: fade-out
---

# <material-symbols-counter-1 />インターフェース上での網羅性
runn のシナリオは yaml で書きます

<Transform :scale="0.6">

```yaml
desc: OpenAPIのSpecのカバレッジを広げる
runners:
  req:
    endpoint: https://petstore3.swagger.io/api/v3
vars:
  status: "sold"
steps:
  findPetsByStatus:
    desc: "Finds Pets by status"
    req:
      /pet/findByStatus?status={{ vars.status }}:
        get:
          header:
            accept: application/json
    test: |
      # ステータスコードが200であること
      current.res.status == 200
      # ペットのステータスが正しいこと
      && current.res.body[0].status == vars.status
  findPetById:
    desc: "Find pet by ID"
    req:
      /pet/{{ steps.findPetsByStatus.res.body[0].id }}:
        get:
          header:
            accept: application/json
    test: |
      # ステータスコードが200であること
      current.res.status == 200
      # 指定されたIDで取得できること
      && current.res.body.id == steps.findPetsByStatus.res.body[0].id
      # ペットのステータスが正しいこと
      && current.res.body.status == vars.status
```

</Transform>

---
layout: image-right
image: https://source.unsplash.com/collection/94734566/960x1080
---

# FAQ

もっとくわしく

---

# Q１.　リクエストパラメータの組み合わせは？
<v-clicks>

エンドポイントだけカバーできればいいの？


* 条件網羅 (condition coverage) C1  
* 複合条件網羅 (multiple condition coverage) C2  
  

# A1.　組み合わせは見たほうがいい
がっつりやりたいなら Controller テストの方がいい

* 最低限 Example（すべてのパラメータあり）と必須項目のみ  
これだけでもやっておくと安心感が違う
* プロパティベースドテストも良さそう  
https://github.com/schemathesis/schemathesis  

</v-clicks>

---
transition: slide-up
---

# Q2. runn ってどうなの？　
<v-clicks>

新しいツールなので学習コストが気になるハズ

* Postman とかの違いは？  

# A2. 書き味が良くテストを量産させやすい  
テキストベースなのでパラメータ違いを別シナリオとしてコピペ量産ができる

* curl のコマンドから、runn new でシナリオとテストを自動生成できる  
* データ駆動テストもできるよ
* チュートリアルもあるよ！  
<a href="https://qiita.com/advent-calendar/2023/runn-tutorial">runn チュートリアル Advent Calendar 2023</a><QRCode width="180" height="180" value="https://qiita.com/advent-calendar/2023/runn-tutorial" color="4329B9" />

</v-clicks>

---

# <material-symbols-counter-2 />ロジック上での網羅性
ユースケースをどこまでカバー出来ているか？

<v-clicks>

* ユースケース毎にエンドポイント別れていることが大半  
CRUD で HTTP メソッドが変わる
* ユースケース内に条件分岐がある場合、単一責任の原則に違反している可能性  
条件分岐があったとしても、その粒度でカバレッジ漏れが発生することはあまりなくない？
* テストに対してカバレッジの紐づけはどうする？🤔
* そもそも `コード` カバレッジで見る意味はあるか？😅

</v-clicks>

---
layout: end
transition: fade
---

# 完
## ご静聴ありがとうございました

---
layout: fact
transition: fade
---

# ・　・　・　・

---
layout: fact
transition: fade
---

# でもやっぱり見たいですよね？

---

# E2Eでカバレッジを取る方法
API テスト以外にも適用できます

* Xdebug を有効にする  
通常の PHPUnit でコードカバレッジ取得するのと同じ
* スクリプト実行時にカバレッジ計測の関数を呼び出す [^1] 
  1. xdebug_start_code_coverage  
  計測対象の処理を実行する直前に呼び出す
  2. xdebug_stop_code_coverage  
  スクリプトが終了する前呼び出す
  3. xdebug_get_code_coverage  
  カバレッジをファイル出力する
* 計測完了後にカバレッジファイルからレポートファイル(HTML)出力

[^1]: auto_prepend_file を利用して処理をフックしても良い

---

# middleware作った
Laravel の HTTPmiddleware を composer 化

PHPUnit のカバレッジ設定を参照しカバレッジ計測の関数を呼び出す。  
特定のリクエストヘッダーがある場合カバレッジ取得する  
https://github.com/k2tzumi/laravel-coverage-middleware

<Transform :scale="0.7">

* インストール方法  
  ```console
  $ composer require --dev k2tzumi/laravel-coverage-middleware
  $ php artisan vendor:publish --provider="K2tzumi\LaravelCoverageMiddleware\Providers\CoverageServiceProvider"
  $ php artisan coverage:install {group}
  ```
* 使い方
  1. runn でシナリオ作成する  
httpRunner の trace を `true` にする
    ```yml {,4} 
    runners:
    req:  
      endpoint: https://petstore3.swagger.io/api/v3
      trace: true
    ```
  2. シナリオ実行する  
  ```console
  $ runn run --verbose path/to/**/*.yml  
  ```
  3. カバレッジファイルを集計してレポート作成する
  ```console
  $ php -d memory_limit=-1 vendor/bin/phpcov merge --html coverage/html storage/coverage  
  ```

[^1]: 必要に応じて `config/coverage.php` を修正

</Transform>

---

# カバレッジ結果
コードカバレッジを分析できる

<Transform :scale="0.8">

<img src="phpcov.png" class="h-40 shadow"/>

runn のシナリオの id が表示される

```console
% runn list --long --id 87996e05872c153740b740b85ceff5b84bcebecd path/to/**/*.yml
  id:                                       desc:                                if:  steps:  path                     
-----------------------------------------------------------------------------------------------------------------------
  87996e05872c153740b740b85ceff5b84bcebecd  OpenAPIのSpecのカバレッジを計測する            1  day19/exec-coverage.yml  

% runn run --scopes run:exec --verbose --id 51672f3b69495f76959c4dc3a295f3a6a958ca2f **/*.yml
=== OpenAPIのSpecのカバレッジを広げる (day19/open-api-coverage.yml) ... ok
    --- Finds Pets by status (findPetsByStatus) ... ok
    --- Find pet by ID (findPetById) ... ok

1 scenario, 0 skipped, 0 failures
```

id からシナリオとステップを特定し、再実行できる

</Transform>

----

# 参考資料

* リモートホストで動く PHP アプリケーションに対する E2E テストでカバレッジを測定する方法
https://blog.freedom-man.com/e2e_coverage
* runn クックブック  
https://zenn.dev/k1low/books/runn-cookbook

---
layout: end
---

# ご静聴ありがとうございました
