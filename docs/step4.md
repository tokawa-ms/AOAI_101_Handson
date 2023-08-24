# Azure OpenAI を使った賢いアプリケーションを実装する

## サンプルアプリのダウンロード

[サンプルアプリ](https://github.com/ayako/BuildJapan2023AOAIDemo/blob/main/RecipeCreatorApp202306.zip) をダウンロードし、Zipファイルを展開しておきます。

## サンプルアプリを触ってみる

展開したサンプルアプリ (RecipeCreatorApp202306) を Visual Studio Code で開きます。

![](./img/SampleApp01.png)

**[このフォルダー内のファイルの作成者を信頼しますか]** というメッセージが表示されたら、**[はい...]** をクリックして進みます。

![](./img/SampleApp02.png)

左バナーの **エクスプローラー** をクリックして、フォルダー＆ファイルを表示します。

**[ビルドおよびデバッグに必要な資産がありません...]** というメッセージが表示されたら、**[はい]** をクリックして作成します。

![](./img/SampleApp03.png)

エクスプローラーから **Pages** > **index.cshtml.cs** をクリックして表示します。 

28行目にある Azure OpenAI Service の情報 (デプロイしたモデルのエンドポイント (URL) および API Key) を設定します。

![](./img/SampleApp04.png)

左バナーから **[実行とデバッグ]** をクリックして開きます。**▷** をクリックして、デバッグ実行します。

![](./img/SampleApp05.png)

ブラウザーが立ち上がり、アプリが表示されます。

**[献立メニューを作る]** をクリックすると、Azure OpenAI Service によって生成された献立メニューが画面右側に表示されます。
そのあと **[栄養アドバイスを見る]** をクリックすると、同様に生成された健康アドバイスが画面左下に表示されます

![](./img/SampleApp06.png)

## サンプルアプリのデプロイ

### Azure Portal から Web アプリの作成

ブラウザーで **[Azure Portal](https://portal.azure.com)** を開きます。

**[＋リソースの作成]** をクリックします。

![](./img/CreateWebApp01.png)

**リソースの作成** 画面から **Web アプリ** の作成 をクリックして、Web アプリ作成メニューを開きます。

![](./img/CreateWebApp02.png)

**Web アプリの作成** 画面で必要な項目を設定します。

**リソースグループ** は 作成済みの リソースグループを選択、または**新規作成** をクリックして、お好みの名前を入力してください。

![](./img/CreateWebApp03.png)

**インスタンスの詳細**

- **名前** : お好みの名前を設定してください
- **公開** : コード
- **ランタイムスタック** :　**.NET 7 (STS)**
- **オペレーティングシステム** : Windows
- **地域** : Japan East

![](./img/CreateWebApp04.png)

**価格プラン**

- **Windows プラン** : 作成済みのプランを選択する、または**新規作成** をクリックして、お好みの名前を入力

入力できたら、**[確認および作成]** をクリックして次に進みます。

![](./img/CreateWebApp05.png)

構成の確認が終わったら **[作成]** をクリックして Web アプリを作成します。

![](./img/CreateWebApp06.png)

デプロイ画面に遷移し、**デプロイが完了しました** と表示されたら、Web アプリの作成は完了です。

![](./img/CreateWebApp07.png)

### サンプルアプリを Azure にデプロイ

Visual Studio Code に戻ります。
 
左バナーの **[Azure]** をクリックします。**Resources** > (お使いのサブスクリプション名) > **App Services** をクリックして開き、作成した Web アプリを表示します。

Web アプリを右クリックして、**Deploy to Azure** をクリックします。

![](./img/DeployToAzure01.png)

画面上部にコマンドパレットが表示されます。ローカルのサンプルアプリを選択します。

![](./img/DeployToAzure02.png)

**Required confiration to deploy is missing...** と表示されたら、**[Add config]** をクリックして設定ファイルを自動生成します。

![](./img/DeployToAzure03.png)

**Are you sure to deploy... (上書きします)** と表示されますが、**Deploy** をクリックしてデプロイを実行します。

![](./img/DeployToAzure04.png)

画面右下に **[Deploying ...]** と表示されて、デプロイが実行されます。メッセージが **[Deployed]** になると、ブラウザーが起動して Azure にデプロイされた Web アプリが表示されます。

![](./img/DeployToAzure05.png)
