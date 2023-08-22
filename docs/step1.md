# Azure OpenAI を使うための初期設定

## 前提条件
この手順を実施する前に、[事前準備](step0.md)として以下の条件を満たしている必要があります。
- 所属する会社から払い出しを受けた、有効な Azure Subscription を持っている
- 利用する Azure Subscription で Azure OpenAI の利用申請が完了している

## Azure OpenAI のアカウントを作成する
[Azure Portal](https://portal.azure.com/) にログインし、左上のハンバーガーメニュー（横３本線のアイコン）を展開し、リソースの作成ボタンをクリックします。

![リソースの作成ボタン](./img/CreateAOAI001.png)

MarketPlace の画面が開きますので、左上の検索窓から "Azure OpenAI" と検索して、検索結果に Azure OpenAI が出てくることを確認します。

![MarketPlace 検索](./img/CreateAOAI002.png)

検索結果の左下にある「作成」ボタンをクリックし、そこから展開される "Azure OpenAI" をクリックします。
すると次に "Azure OpenAI の作成" という画面が表示されますので、必要な情報を入力します。

![Azure OpenAI の作成](.img/../img/CreateAOAI003.png)

一般的には、以下のような形で入力することになるかと思います。

- サブスクリプション
  - Azure OpenAI を利用しようとしている Azure Subscription 名を選択
- リソースグループ
  - 任意の一意の名前を入力
- リージョン
  - Azure OpenAI を利用したいリージョンを選択
    - 現状、EastUS が一番多くのモデルを利用できる一方、ChatGPT であれば JapanEast が一番応答は早いと思います。
  - 名前
    - 任意の一意の名前を入力
  - 価格レベル
    - Standard S0 を選択

「次へ」をクリックし、「ネットワーク」の画面では今回、「インターネットを含むすべてのネットワークがこのリソースにアクセスできます」を選択します。
!> ここで他のオプションを選択することで、例えば Azure 上にある Web サーバーからの呼び出しのみ許可する形のように、限られたネットワークの範囲からのみのアクセスを許可するような構成も可能です。

![Azure OpenAI のネットワーク構成](.img/../img/CreateAOAI004.png)

残りの画面は「次へ」で飛ばしていただき、「レビューおよび送信」の画面まで行ったら「作成」ボタンを押してください。

![Azure OpenAI の作成画面](./img/CreateAOAI005.png)

デプロイ状況の確認画面が表示されますので、ステータスが完了になるのを待機します。

![Azure OpenAI 作成中](./img/CreateAOAI006.png)

以下の画面が出たら、Azure OpenAI のリソースの作成は完了です。

![Azure OpenAI 作成完了](./img/CreateAOAI007.png)
## Azure OpenAI のアカウントが作成されたことを確認する
一旦、[Azure Portal](https://portal.azure.com/) に戻り、画面上部の検索窓で "Azure OpenAI" と検索します。

![AOAI検索](./img/CheckAOAI001.png)

検索結果から、”Azure OpenAI” を探してクリックします。
すると、サブスクリプションにデプロイされている Azure OpenAI のアカウントのリストが表示されます。

その中に、先ほど作ったものがあることを確認してください。

![AOAI確認](./img/CheckAOAI002.png)

先ほど作った OpenAI の名前の部分をクリックし、OpenAI の管理画面に移行します。

## Azure OpenAI の Azure Portal 側の管理画面
Azure OpenAI の Azure Portal 側の管理画面は下記のような形で表示されます。
（Azure Portal 側の、と称しているのは、実はこの後に別の URL でホストされる専用の別のポータルも使うからです）

左ペインに各種メニューがあり、右ペインもしくは別画面にて詳細な情報の確認もしくは操作を実施するような形です。

![AOAI 管理画面](./img/AOAIModelDeploy001.png)


### Azure OpenAI の管理画面のメニュー項目について
Azure Portal にある Azure OpenAI の管理画面にて実行できる操作（主な左ペインのメニューの項目）についてここで解説します。

- 概要
  - この画面には Azure OpenAI の エンドポイントの URL や、デプロイ名やデプロイされているリージョンなどの情報がまとまっています。
- Keys and Endpoint
  - この画面から Azure OpenAI にアクセスするのに必要なキーの情報を取得します
- Model deployments
  - この画面から Azure OpenAI のモデルデプロイ画面に移行します
- Networking
  - この画面から、対象の Azure OpenAI にアクセス可能なネットワークの設定が可能です。

## Azure OpenAI のモデルをデプロイする
モデルのデプロイ方法を書く。