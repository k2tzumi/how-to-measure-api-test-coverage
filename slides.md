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
  - '@katzumi/slidev-addon-qrcode'
  - slidev-addon-components
  - slidev-addon-rabbit
---

# APIテストでもカバレッジ測定したい！
API テストのカバレッジは２つの意味を持つ

[PHPerKaigi 2024](https://phperkaigi.jp/2024/)　March 9, 2024.  
v0.0.5  
@katzumi (かつみ)

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
サブタイトルには触れない
-->

---
transition: fade-out
layout: two-cols-header
---

# 自己紹介

katzumi（かつみ）と申します。

「障害のない社会をつくる」をビジョンに掲げている「りたりこ」という会社に所属しています
<a href="https://litalico.co.jp/">
<img src="https://litalico.co.jp/ogp.png" class="w-40" />
</a>

以下のアカウントで活動しています。

::left::

<div class="float-left">
<img src="https://pbs.twimg.com/profile_images/1764238086572253184/FxgJkwUL_400x400.jpg" class="rounded-full w-40 mr"/>  
<simple-icons-x /> <a href="https://twitter.com/katzchum">katzchum</a></div>  
<QRCode width="180" height="180" value="https://twitter.com/katzchum" color="4329B9" image="Logo_of_X.svg" />

::right::

<img src="https://avatars.githubusercontent.com/u/1182787?v=4" class="rounded-full w-40 mr-12"/>

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

<!--
かつみと申します  
リタリコという会社に所属しています  
以下のアカウントで活動していますので、よかったらフォローをお願いします  
-->

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
<a href="https://twitter.com/search?q=%23phperkaigi%20%23a">#phperkaigi #a</a>

<!--
後でスライド公開します  

本セッションでは、撮影やSNS拡散を歓迎しています。ご自由に写真を撮影して、XなどのSNSでシェアしてください。 　　
ただし、以下の点にご注意ください。　　

著作権などの法的な問題を避けるために、スライドや登壇者の写真や動画を無断で商用利用しないでください。　　
他の参加者のプライバシーや迷惑にならないように、撮影や投稿する際には配慮してください。　　
SNSでシェアする際には、ハッシュタグ「#phperkaigi #a」をつけてください。　　
これにより、本セッションの関連情報を簡単に検索できるようになります。
-->

---
layout: fact
transition: fade-out
---

# APIテスト
# 書いていますか？　✋

<!--
[会場で手を上げてもらう。]  
手を上げた方、是非懇親会等で仲良くさせてください！
-->

---
layout: fact
transition: fade-out
---

# APIテストは
# いいぞ 👍

<!--
いいぞということで。。
-->

---
layout: fact
transition: fade-out
---

# 突然の宣伝！

<!--
宣伝です！
-->

---
transition: fade-out
---

# APIシナリオテストを書くべき10の理由
昨年トークしてきました

API シナリオテスト is 何？という方は是非！
 <a href="https://www.docswell.com/s/katzumi/5EN8N1-10-reasons-to-write-api-scenario-tests"><img src="https://k2tzumi.github.io/10-reasons-to-write-api-scenario-tests/thumbnail/001.png" class="h90" /></a>

<!--
昨年、「APIシナリオテストを書くべき１０の理由」という内容で登壇してきました。  
APIシナリオテストを知らない人におすすめの内容となっていますので是非ご覧ください
-->

---
transition: fade-out
---

# APIシナリオテストを書くべき10の理由
YouTube でみれます

<Youtube id="iqPsUaqjGGM" class="h100 w150" />

<!--
YouTubeでも見れます
-->

---
layout: center
---

# 伝えたかったこと
他に色々あるけれども..

<img src="https://k2tzumi.github.io/10-reasons-to-write-api-scenario-tests/thumbnail/023.png" class="container w-190 object-center shadow object-cover" />

<!--
こちらのトークで伝えたかった内容としては、「効率よくカバレッジを上げることができる」点となります
-->

---
layout: fact
transition: fade-out
---

# APIテストにとって
# カバレッジとは？　🤔

<!--
、、となりますが
-->

---

# カバレッジとは？　
網羅率。どれだけテストしたかの指標

<blockquote>
<p>ソフトウェアテストで用いられる「カバレッジ(網羅率)」とは対象のプログラム全体のうち、どこまでテストが実施(網羅)されたかを示す割合のことです。</p>
<p>テストを実施する際にカバレッジを測定/分析することでソフトウェアの品質を定量的に評価することができます。</p>
</blockquote>
<a href="https://www.qbook.jp/column/632.html">ソフトウェアテストのカバレッジ(網羅率)とは｜設定するメリット２つと注意点【ソフトウェア開発・テスト用語 】| Qbook</a> より

<!--
網羅率のことです。これはどれだけテストをしたかの指標です  
もう少し深ぼっていきます、
-->

---
transition: fade-out
---

# APIテストでのテスト観点とは？
単体テストの観点とは違う

<Transform :scale="1.4">

1. エンドポイントの仕様の正確性を確認  
    * エンドポイントは API の仕様通りに実装されているかを確認
    * リクエストが正しく受け付けられているかどうかを検証  
    * レスポンスが仕様通りに返されているかを確認  
2. API チェーンの検証  
    * API を連鎖させて呼び出すことで、期待通りに動作するかを確認  
    * 例えば、登録 API を呼び出し、そのレスポンスに含まれる  
    コードを使用して更新 API が呼ばれることを確認  
    * ユースケース観点での動作検証

</Transform>

<!--
網羅率を考える上で重要なのが、APIテストのテスト観点です。  
大きく２つの観点があります。  
* １つ目はエンドポイントの仕様の正確性の担保  
* ２つ目はAPIをチェーンで呼び出してのユースケース観点での動作の担保  

です
-->

---
layout: fact
transition: slide-up
---

# APIテストの
# カバレッジは
# ２つの意味を持つ！
サブタイトル回収

<!--
ここでサブタイトルを回収となります　　
-->

---

# ２つの網羅性
テスト観点での優先度順

<Transform :scale="2.5">

1. インターフェース上での網羅性
2. ロジック（ユースケース）上での網羅性

</Transform>

<!--
次のスライドから２つの意味（網羅性）について見ていきます
-->

---

# <material-symbols-counter-1 />インターフェース上での網羅性
OpenAPI Spec に対するカバレッジ


エンドポイントに対しての網羅率を見る！  
<img src="/swagger.png" alt="OpenAPI Spec" class="h-90 ml-4 shadow" />

<!--
まず一つ目はインターフェース上での網羅性です。  
API仕様書に記載されているエンドポイントに対してのテストがあるか？になります
-->

---

# <material-symbols-counter-1 />インターフェース上での網羅性
エンドポイントに対してのカバレッジの見える化


API シナリオテストツール runn でできる！  
<img src="/runn-coverage.png" alt="runn's coverage execution results" class="h-90 ml-4 shadow" />


<img src="https://github.com/k2tzumi/zenn/blob/main/images/books/runn-tutorial/coverage-report.png?raw=true" alt="カバレッジコメント" class="absolute right-10 bottom-10 z-10 h-45 shadow" />

<!--
図の様にエンドポイントに対してカバーしているテストケース数をカウントしてカバレッジ率を計算します。  
こちらはAPIシナリオテストツールのrunnを使うことで簡単にできます。  
１つ目のカバレッジを見れるようになりましたが、次のスライドにある様な疑問が出てきます、、
-->

---
transition: slide-up
layout: center
---

# 　Q.リクエストパラメータの組み合わせは？🤔
エンドポイントだけカバーできればいいの？

<Transform :scale="1.8">

* 条件網羅 (condition coverage) C1  
* 複合条件網羅 (multiple condition coverage) C2  

</Transform>

<!--
エンドポイントのカバー率だけなの？  
リクエストパラメータの組み合わせは見なくていの？  
と。。
-->

---
transition: fade-out
layout: center
---

# A.　組み合わせは検証したほうがいい
がっつりやるなら Controller テストの方がいい

<Transform :scale="1.4">

* 最低限 Example（すべてのパラメータあり）と必須項目のみ  
これだけでもやっておくと安心感が違う
* プロパティベースドテストも良さそう  
https://github.com/schemathesis/schemathesis  

</Transform>

<!--
パラメータの組み合わせのテストパターンは必要です。  
ただガッツリやるならControllerテストでやるのをおすすめします。  
I/Fの品質の観点ではExampleや必須項目のみのテストは最低限行うことをオススメします。
-->

---
transition: slide-up
layout: center
---

# Q.runn ってどうなの？🤔　

新しいツールなので学習コストが気になるハズ

<Transform :scale="1.8">

* 他のツールとの違いは？  
* テストの書き味は？

</Transform>

<!--
次に先ほど出てきたrunn(ランエヌ)というツールに対しての疑問についてお答えしたいと思います
-->

---
transition: fade-out
layout: center
---

# A.書き味が良くテストを量産させやすい  
テスト内容をコード・レビューができる

<Transform :scale="1.4">

## テキストベースなのでパラメータ違いの
## 別シナリオをコピペ量産できる！

</Transform>

<!--
書き味が大変良いと感じています。  
テキストベースでシナリオを書くことができ、コピペ量産し易いです。
-->

---
transition: fade-out
layout: two-cols
---

## こんな感じのyaml


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
```

::right::

## （続き）

```yaml
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
      && current.res.body.id == 
           steps.findPetsByStatus.res.body[0].id
      # ペットのステータスが正しいこと
      && current.res.body.status == vars.status
```

<!--
ここでは詳しく説明しないですが、こんなyamlで書けます！
-->

---

# その他runnのメリット

<Transform :scale="1.4">

* curl のコマンドから、runn new でシナリオとテストを自動生成できる  
* データ駆動テストもできる
* CI Friendly

</Transform>

<!--
色々推しポイントがあるのですが。。
-->

---
layout: image-right
image: >-
  https://github.com/k2tzumi/zenn/blob/main/books/runn-tutorial/cover.png?raw=true
backgroundSize: contain
---

# チュートリアル本作りました　🎉🎉

<Tweet id="1758870210076098610" />

<!--
この度runnの魅力を詰め込んだチュートリアル本を作りました！  
こちらも是非お願いします。
-->

---

# <material-symbols-counter-2 />ロジック上での網羅性
ユースケースをどこまでカバー出来ているか？

<Transform :scale="1.8">

* ユースケース毎にエンドポイント別れていることが大半  
CRUD で HTTP メソッドが変わる

<v-click>

　→　エンドポイントのカバレッジで事足りるが..

</v-click>

</Transform>

<!--
２つ目になりますが、ユースケースでの網羅性となりますが、、  
先程紹介したエンドポイントのカバー率で事足ります。  
とはいえ、カバレッジを見たくなるのはエンジニアの性だと思います
-->

---

# コードカバレッジまで見たいか？
ユースケース内の条件分岐とか..

<Transform :scale="1.8">

* phpunit/php-code-coverage の HTML レポートを出力したい！  
コードの行単位にカバレッジを見たい！

<v-clicks>

* 別プロセスで動いている PHP のカバレッジをとるには？🤔
* テストに対してカバレッジの紐づけるには？🤔

</v-clicks>

</Transform>

<!--
phpunitでのHTMLレポートを見ている人はコードの行単位に見たくなるはずです。  
しかし、いくつかハードルがあり  
* 別プロセスでどうやって、、  
* テストと紐づけて見たいけれど、、  

という課題があります。  
次のスライドで、先に結果から見ていきます
-->

---
transition: fade
---

# こんな感じで見える化👀
phpunit/php-code-coverage での出力結果

runn のシナリオの id が表示される

<img src="/phpcov.png" class="h-80 shadow"/>

<!--
このような形でカバレッの可視化ができました。  
こちらもrunnを使ってテストした結果です。  
runnのシナリオのidと紐づけて見れるようになりました。  
こちらはrunnのトレーサビリティの機能を利用して実現しています。
-->

---

# runnにはトレーサビリティがある！
runn はリクエストにカスタムヘッダーを付与できる

id からシナリオとステップが特定し、再実行できる
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

<!--
runnにはリクエストにカスタムヘッダーをつけるという機能があります。  
ヘッダーからシナリオのidとステップを特定できるようになっています。  
またidを指定して再実行も可能です。  
次にPHP側のカバレッジの取得方法について説明します。
-->

---

# リモートホストで動くPHPアプリケーションの
# カバレッジ取得方法
API テスト以外でも適用できます

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

<!--
Xdebugを使う感じになります。  
こちらに記載した通りにゴニョゴニョすればできます。  
詳しくは本日きんじょうひできさんがphp-code-coverageについて神トークされていたのでオススメです！  
https://fortee.jp/phperkaigi-2024/proposal/8543c51c-7e06-45d5-a216-cba29cb29789
-->

---

# middleware作った
Laravel の HTTPmiddleware を composer 化

PHPUnit のカバレッジ設定を参照し、カバレッジ計測の関数を呼び出す。  
特定のリクエストヘッダーがある場合にのみリクエスト単位にカバレッジ取得する  
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

<!--
毎回Xdebugを仕込むのが面倒だと思ったので、、  
カバレッジ取得用のmiddlewareを作成しました。   
Laravel向けにはなります。  
ライブラリ化で一番苦労した点はセットアップコマンドの準備でしたｗ
-->

---

# 参考資料＆リンク

* リモートホストで動く PHP アプリケーションに対する E2E テストでカバレッジを測定する方法
https://blog.freedom-man.com/e2e_coverage
* runn クックブック  
https://zenn.dev/k1low/books/runn-cookbook
* runn チュートリアル  
https://zenn.dev/katzumi/books/runn-tutorial
* laravel-coverage-middleware  
https://github.com/k2tzumi/laravel-coverage-middleware

<!--
最後に参考資料をつけておきますのでご参照ください。  
ご静聴ありがとうございました！
-->
