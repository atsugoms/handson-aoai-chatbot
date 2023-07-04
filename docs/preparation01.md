# Preparation1: 事前準備

## 【目次】

1. [Azure環境準備](#azure環境準備)
1. [開発環境準備](#開発環境準備)

## Azure環境準備

1. Azure OpenAI Service 利用申請

    https://aka.ms/oaiapply


## 開発環境準備

1. 以下のツールが事前に開発環境に必要です。

    * [Visual Studio Code](https://code.visualstudio.com/download)
        * [App Service プラグイン](https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-azureappservice)
        * [REST Client プラグイン](https://marketplace.visualstudio.com/items?itemName=humao.rest-client)
    * [Bot Service Emulator](https://github.com/Microsoft/BotFramework-Emulator/releases/)
    * [Node.js (v16 LTS)](https://nodejs.org/ja/download)

(*) Node.js は v18.16.1 の場合、関連するモジュールの動作でエラーが発生することが確認されています。

### (参考) Node.js の複数バージョン管理

Node.js を複数バージョン自分の環境に導入し、切替ながら利用したい場合,
'nvm' と呼ばれるツールを利用します。
Windowsの場合、以下のサイトからダウンロードできます。

1. `nvm` インストール

    1. 「 `nvm-windows` 」 のダウンロード

        https://github.com/coreybutler/nvm-windows/releases

        最新バージョンにある「nvm-setup.exe」をダウンロード

    1. ダウンロードした「nvm-setup.exe」を実行、インストール

1. `node`のインストール

    1. コマンドプロンプト（CMD）を **管理者** で起動
    1. 以下のコマンドを実行してダウンロード可能な Node.js バージョンを確認します。

        ```
        nvm list available
        ```

    1. 表示されたものから **v16** の最新のものを探してインストールします。

        ```
        nvm install 16.20.1
        ```

    1. インストールバージョンを利用するように設定します。

        ```
        nvm use 16.20.1
        ```

    1. 設定変更されたことを確認します。
        現在有効になっているバージョンの先頭に `*` が表示されます。

        ```
        nvm list
        ```

    1. 念のため `node` コマンドでもバージョン確認します。

        ```
        node --version
        ```