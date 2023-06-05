# Exercise4: Bot Service / App Service デプロイ

## 【目次】

![](images/e04-0000-deploy.png)

1. [Bot Service 作成](#bot-service-作成)
1. [App Service 作成](#app-service-作成)
1. [Botアプリのデプロイ](#botアプリのデプロイ)
1. [Botアプリ設定のデプロイ](#botアプリ設定のデプロイ)

## Bot Service 作成

1. Azure ポータル上部にある検索窓で「Bot Service」を検索して、「Bot Service」を選択

    ![](images/e04-0101-deploy.png)

1. 「作成」を選択

    ![](images/e04-0102-deploy.png)

1. 「さらに読み込む」を何度か押下して「Azure Bot - Microsoft」を選択

    ![](images/e04-0103-deploy.png)

1. 「Azure Bot」の「作成」を選択

    ![](images/e04-0104-deploy.png)

1. 「Azure Bot Service」の作成

    1. 「基本」ページ

        * ボットハンド： （ボットのリソース名。任意名称）
        * サブスクリプション： （今回利用予定のサブスクリプション）
        * リソースグループ：（作成済みのもの）
        * データ所在地： `グローバル`
        * 価格レベル： `Standard`
        * アプリの種類： `ユーザー割り当て済みマネージドID`
        * 作成の種類： `新しい Microsoft アプリID の作成`

        ![](images/e04-0105-deploy.png)

    1. 「タグ」はデフォルトのまま

    1. 「確認と作成」ページ

        内容を確認して「作成」

1. Bot Service の一覧に作成したリソースが増えていることを確認


## App Service 作成

1. Azure ポータル上部にある検索窓で「App Service」を検索して、「App Service」を選択

    ![](images/e04-0201-deploy.png)

1. 「作成」を選択

    ![](images/e04-0202-deploy.png)

1. App Service 作成

    1. 「基本」ページ

        * サブスクリプション： （今回利用予定のサブスクリプション）
        * リソースグループ：（作成済みのもの）
        * 名前： （任意名称。 **グローバルで一意になるよう注意** ）
        * 公開： `コード`
        * ランタイム： `Node 16 LTS` （ローカル開発で利用しているバージョンにあわせる）
        * OS： `Linux`
        * 地域： `Japan East`
        * Linuxプラン： （任意名称）
        * 価格プラン： `Basic B1` (選択肢にない場合、 `価格プランを確認する` から探す)

        ![](images/e04-0203-deploy.png)

    1. 「デプロイ」ページ

        * 継続的デプロイ： `無効化`

        ![](images/e04-0204-deploy.png)

    1. 「ネットワーク」ページ

        * パブリックアクセス： `オン`
        * ネットワークインジェクション： `オフ`

        ![](images/e04-0205-deploy.png)

    1. 「監視」はデフォルトまま

        * Application Insights： `いいえ`

        ![](images/e04-0206-deploy.png)

    1. 「タグ」はデフォルトまま

    1. 「確認および作成」ページ

        内容を確認して「作成」

1. App Service の一覧に作成したリソースが増えていることを確認


## Botアプリのデプロイ

1. Visual Studio Code で Bot アプリ（ `my-chat-bot` フォルダ ）を開く

1. 「Azure」タブへ移動して「Sign in to Azure...」から Azure へサインイン

    ![](images/e04-0301-deploy.png)

1. [(サブスクリプション)]-[App Services]-[(作成済み App Service)]を展開

    ![](images/e04-0302-deploy.png)

1. 展開したい App Service を右クリック、「Deploy to Web App...」を選択

    ![](images/e04-0303-deploy.png)

1. 開いているプロジェクトフォルダ（ `my-chat-bot` ）を選択

    ![](images/e04-0304-deploy.png)

1. 「Deploy」を選択して強制的に上書きデプロイを実行

    ![](images/e04-0305-deploy.png)

1. デプロイ完了を確認

    ![](images/e04-0306-deploy.png)


## Botアプリ設定のデプロイ

1. 「Application Settings」を右クリック、「Upload Local Settings...」を選択

    ![](images/e04-0401-deploy.png)

1. `.env` ファイルを選択してデプロイ

    ![](images/e04-0402-deploy.png)

1. 「Application Settings」を開いてアップロードされたことを確認

    ![](images/e04-0403-deploy.png)

