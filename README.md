## テックキャンプの最終課題紹介資料
### 概要
テックキャンプの最終課題にて作成したアプリケーションを紹介します。<br>
また本資料では、自身で実装した箇所、および開発を通じて得られた経験についても紹介します。

### アプリケーション概要
チーム開発でフリーマーケットのアプリケーションを作成しました。
#### ● 接続先情報
- URL http://52.199.193.193/
- ID: admin
- Pass: pass1111
#### ○ テスト用アカウント等
##### ■ 購入者用
- メールアドレス: tanaka@tanaka.com
- パスワード: tanaka1234
##### ■ 購入用カード情報
- 番号: 4242424242424242
- 期限: 04/23
- セキュリティコード:2222
##### ■ 出品者用
- メールアドレス名: guest@guest.com
- パスワード: guest1234
#### ● Githubリポジトリ
- https://github.com/mibokatsu1/fleamarket_sample_78c

### 開発状況
#### ● 開発環境
- Ruby/Ruby on Rails/MySQL/Github/AWS/Visual Studio Code
#### ● 開発期間と平均作業時間
- 開発期間:6/29~7/24 (約4週間)
- 1日あたりの平均作業時間:10時間
#### ● 開発体制
- 人数:5
- アジャイル型開発(スクラム)
- Trelloによるタスク管理

### 動作確認方法
- Chromeの最新版を利用してアクセスしてください。
- ただしデプロイ等で接続できないタイミングもございます。その際は少し時間をおいてから接続ください。
- 接続先およびログイン情報については、上記の通りです。
- 同時に複数の方がログインしている場合に、ログインできない可能性がございます。


- 出品方法は以下の手順で確認できます<br>
テストアカウントでログイン→トップページから出品ボタン押下→商品情報入力→商品出品
- 購入方法は以下の手順で確認できます<br>
テストアカウントでログイン→トップページから商品一覧→商品選択→商品購入
- 確認後、ログアウト処理をお願いします。<br>

### 開発担当箇所 担当箇所一覧と確認方法
- DB設計
- トップページ(フロントエンド)<br>
<img width="1440" alt="スクリーンショット 2020-07-24 21 06 49" src="https://user-images.githubusercontent.com/66307448/91628754-ecf99a00-e9fd-11ea-9bb7-0cf47bab9ef1.png">
<img width="1440" alt="スクリーンショット 2020-07-24 21 09 11" src="https://user-images.githubusercontent.com/66307448/91628756-f125b780-e9fd-11ea-8199-9847dba7f2ed.png">

○ http://52.199.193.193/ <br>
にアクセスするとご覧いただけます。
- 出品商品一覧新着表示機能(バックエンド)<br>
○ http://52.199.193.193/ <br>
にてご覧いただけます。
- 出品ページ(フロントエンド)<br>
○ 出品用アカウントでログイン後、トップページの右下の出品するボタンから遷移してご覧いただけます。
<img width="1440" alt="スクリーンショット 2020-07-24 21 23 16" src="https://user-images.githubusercontent.com/66307448/91628774-3649e980-e9fe-11ea-9184-4d80a6fcd539.png">

- ルーティングの設定(バックエンド)
- パンくず機能(バックエンド)<br>
○ 本人情報確認ページ等の上部にてご覧いただけます。
<img width="574" alt="スクリーンショット 2020-07-27 9 55 13" src="https://user-images.githubusercontent.com/66307448/91628789-57aad580-e9fe-11ea-9a3a-0dae9390bc98.png">

商品購入機能(バックエンド)<br>
○ 購入者用アカウントでログイン後、トップページの商品一覧から適当な商品を選択することで商品購入画面へ進めます。<br>
  クレジットカード情報の入力を求められた際は、上記の購入用カード情報を入力することで購入できます。
<img width="658" alt="スクリーンショット 2020-07-24 21 37 24" src="https://user-images.githubusercontent.com/66307448/91628814-7610d100-e9fe-11ea-9c55-4d9ad581bd51.png">

### 各担当箇所の詳細
- DB設計<br>
○ 概要<br>
 ■ 必要なテーブル、カラムの選定<br>
 ■ アソシエーションの決定<br>
○ 担当内容<br>
  ■ ER図の作成<br>
  ■ 各テーブルの作成<br>
  ■ モデルへのアソシエーションの記述

- トップページ(商品新着一覧ページ)<br>
○ 概要<br>
  ■ 新着順に商品が10件表示されるページ<br>
  ■ ピックアップアイテムに該当商品を出品すると、トップページに5件表示される<br>
○ 担当内容(バックエンド)<br>
  ■ コントローラーにて、アイテム一覧から新着アイテムとピックアップアイテムの該当商品を新着順に一覧表示<br>
○ 担当内容(フロントエンド)<br>
  ■ haml,scss,javascriptを使用しトップページのマークアップ作業<br>

- パンくず機能<br>
○ 概要<br>
  ■ 現在表示されているページの階層がわかりやすくなるように、ページの左上にパンくず機能を設置<br>
○ 担当内容(バックエンド)<br>
  ■ Ruby on Railsの”**gretel**”というgemを使用し、パンくず機能を追加<br>

- 商品購入機能
○ 概要<br>
  ■ 商品をクレジットカード決済を用いて購入する機能<br>
○ 担当内容(バックエンド)<br>
  ■ クレジットカードへのアクセスキーを保存するモデル、コントローラ、 ルーティングの作成<br>
  ■ APIの"**payjp**"を導入し、カード登録時にpayjp側へカード情報と顧客情報を 新規作成<br>
  ■ 登録した情報にアクセスする為のキーをDBへ保存する機能の実装<br>
  ■ DBのキーを利用してpayjpのクレジットカード情報を取得し、自分のカード情報(下4桁,期限など)を表示する機能の実装<br>
  ■ 商品購入時にDBのキーを使ってpayjpの自分のカードを使用し、決済が完了する機能の実装<br>
  ■ 決済が完了すると注文情報、売上情報のレコードを作成する処理の実装<br>

- 商品出品機能<br>
○ 概要<br>
  ■ 商品画像を5枚まで選択して商品を出品する機能<br>
  ■ 販売価格を入力すると販売手数料、販売利益が計算される機能<br>
○ 担当内容(フロントエンド)<br>
  ■ JavaScriptを使用し、商品画像を非同期通信で5枚まで追加<br>
  ■ JavaScriptを使用し、販売利益が自動計算で表示される実装<br>
○ 概要<br>
  ■ 多階層の商品カテゴリーを選択して商品を出品する機能<br>
○ 担当内容(バックエンド)<br>
  ■ Ruby on Railsの”**ancestry**”というgemを使用し、商品のカテゴリーを追加<br>
  ■ カテゴリーは多階層となっており、商品分類を3階層で絞り込む実装

- 商品コメント機能<br>
○ 概要<br>
  ■ 商品詳細ページから商品に関するコメントを購入者および出品者が書き込める機能<br>
○ 担当内容(フロントエンド)<br>
  ■ **JavaScript**を使用し、商品に関するコメントを追加<br>
  ■ コメントは出品者のみ仮削除、完全削除が可能。仮削除したコメントは復帰できる実装<br>

### 開発を通じて得られた知見
#### 工夫した点
##### ① チームとして工夫を行った点<br>
開発方針について、最初にエラー解決手順をチームで決め、問題点を相談し合える環境を作 りました。エラーが生じた際に、個人で長期間抱え込んでしまうと、チーム開発スケジュールが大幅に遅れてしまいます。そこで、エラー解決時間を1時間に設定し、1時間はしっかり個人で仮説検証を行い、解決しない場合は、slackでチーム全体にエラー状況をアウトプットして、問題点を共有して解決しました。共有して問題解決することで、チーム全員の問題解決力が アップして、開発スピードがアップしました。<br>
作業面では、マークアップ作業を行った人が、そのページのバックエンド作業を行うことにしたため、作業を非常にスムーズに進めることができました。また、はじめにマークアップ作 業をまとめ終わらせました。そのため、メンバー内で前工程タスクの実装待ちのような無駄な時間が発生せず、スムーズにチーム開発を進捗できました。<br>
##### ② 個人として工夫を行った点<br>
GitHubでプルリクエストを送る際に、実装のポイントと意義を理解しやすいように記述することを心がけました。カリキュラムでは習っていない新しい機能は実装をした際には、担当していないメンバーにも短時間で概要が理解出来るようにアウトプットすることで、個人開発の 何倍も効率が良く学習出来ると感じました。<br>
技術的な部分では、トップページの商品一覧の表示、商品をカテゴリーから検索するための 検索タブを実装した際にRuby on Railsの”ancestry”というgemを初めて使用しました。公式リ ファレンスやQitaの記事等を調べながら、gemの導入、カテゴリーテーブルの作成、seedファイルを利用してテーブルへデータを登録しました。また、JavaScript、jQuery、Ajax、JsonBuilder を使用してカテゴリーの読み出しを非同期通信で行えるよう実装しました。
#### 苦労した点
##### ① DB設計、migrationファイルの整合性<br>
1人のユーザーが商品の出品、購入、さらにコメントができる多機能なアプリケーションの開発が初めてでした。そのため、どのようなテーブル、カラムがあり、アソシエーションが必要な のかイメージしづらく、DB設計に苦労しました。<br>
チームメンバー全員でDB設計を行いましたが、開発を進めていく中で必要な、もしくは不要なテーブル、カラムに気がつき変更を加えて行きました。そして、変更の都度、ローカル環境、本番環境でmigrationエラーが発生し、整合性をとる作業が必要になって苦労しましたが、理解を深めることができました。
     
##### ② JavaScriptの非同期通信実装<br>
JavaScriptはフロントエンドでHTMLの見た目を単純に変更するだけではなく、イベント発火 を元にAjax通信をして、JsonBuilderで作成したデータを元にHTMLを作り替えるため、サーバーサイドの動きも理解しなければならず、苦労しました。console.logやdebuggerを利用して挙動 を確認しながら、開発することで少しづづコードに慣れることができました。

##### ③ GitHub<br>
作業当初は各々がマージする際にコンフリクトが発生することを心配しておりました。開発を進めていく中で、コンフリクトが起こる箇所の予測が出来るようになり、解消する際の残すコードの選択一も慣れることができました。<br>
また、ブランチでgemをインストールした時や、テーブルの情報を書き換えた時など、ブランチをマージすると他のメンバーにどんな影響が出るか把握できるようになり、マージする際にメンバーへ注意を促すことができるようになりました。<br>
<br>以上



# FLEAMARKET DB設計
# usersテーブル
|Coumn|Type|Options|
|-----|----|-------|
|nickname|string|null: false|
|email|string|null: false, unique: true|
|password|string|null: false|
### Association
- has_one :profile
- has_many :send_informations
- has_many :items
- has_one :credit

# profileテーブル
|Coumn|Type|Options|
|-----|----|-------|
|family_name|string|null: false|
|first_name|string|null: false|
|family_name_kana|string|null: false|
|first_name_kana|string|null: false|
|birth_day|date|null: false|
|user_id|reference|foreign_key: true|
### Association
- belongs_to :user

# send_informationテーブル
|Coumn|Type|Options|
|-----|----|-------|
|family_name|string|null: false|
|first_name|string|null: false|
|family_name_kana|string|null: false|
|first_name_kana|string|null: false|
|post_code|string|null: false|
|prefecture_id|reference|null: false|
|city|string|null: false|
|house_number|string|null: false|
|apartment|string||
|phone-number|string|unique: true|
|user_id|reference|foreign_key: true|
### Association
- belongs_to :user
- belongs_to_active_hash :prefecture_id


# itemテーブル
|Coumn|Type|Options|
|-----|----|-------|
|name|string|null: false|
|produce|text|null: false|
|price|integer|null: false|
|deliveryfee_id|reference|null: false|
|brand_id|reference||
|itemcategory_id|reference|foreign_key: true|
|condition_id|reference|null: false|
|prefecture_id|reference|null: false|
|deliverydate_id|reference|null: true|
|selleruser_id|reference|foreign_key: true|
|buyeruser_id|reference||
### Association
- belongs_to :selleruser, class_name:"User"
- belongs_to :buyeruser, class_name:"User"

- has_many :images, dependent: :destroy
- belongs_to_active_hash :brand_id
- belongs_to :itemcategory
- belongs_to_active_hash :condition_id
- belongs_to_active_hash :prefecture_id
- belongs_to_active_hash :deliverydate_id
- belongs_to_active_hash :deliveryfee_id

# imageテーブル
|Coumn|Type|Options|
|-----|----|-------|
|image|text|null: false|
|item_id|reference|foreign_key: true|
### Association
- belongs_to :item

# commentテーブル
|Coumn|Type|Options|
|-----|----|-------|
|item_id|reference|foreign_key: true|
|user_id|reference|foreign_key: true|
|delete_check|integer|default: 0|
|comment|string||
### Association
- belongs_to :user
- belongs_to :item


# creditテーブル
|Coumn|Type|Options|
|-----|----|-------|
|user_id|reference|foreign_key: true|
|customer_id|string|null: false|
|card_id|string|null: false|
### Association
- belongs_to :user

# itemcategoriesテーブル
|Coumn|Type|Options|
|-----|----|-------|
|name|string|null: false|
|ancestry|string||
### Association
- has_many :items
- has_ancestry

# brands(active_hash)
|Coumn|Type|Options|
|-----|----|-------|
|name|string||
### Association
- has_many :items

# conditions(active_hash)
|Coumn|Type|Options|
|-----|----|-------|
|name|string|null: false|
### Association
- has_many :items

# prefectures(active_hash)
|Coumn|Type|Options|
|-----|----|-------|
|name|string|null: false|
### Association
- has_many :send_informations
- has_many :items

# deliverydates(active_hash)
|Coumn|Type|Options|
|-----|----|-------|
|name|string|null: false|
### Association
- has_many :items

# deliveryfees(active_hash)
|Coumn|Type|Options|
|-----|----|-------|
|name|string|null: false|
### Association
- has_many :items
