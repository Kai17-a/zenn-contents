---
title: "ローカル環境でAWS SAM Lambda + Java + PostgreSQLを使って掲示板APIを作る ~準備編~"
emoji: "🔧"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ["aws", "lambda", "java", "postgresql"]
published: false
---
## 環境
* OS
Windows10
* java
java-11-amazon-corrett
* ビルドツール
gradle-8.0.1
* テキストエディタ
Visual Stadio Code
* その他
Docker
aws-cli
sam-cli
<br>

## Java インストール
* java-11-amazon-correttをダウンロード
[aws公式サイト](https://docs.aws.amazon.com/corretto/latest/corretto-11-ug/downloads-list.html)から自身のOSに対応しているjava-11-amazon-correttをダウンロード
(今回はhttps://corretto.aws/downloads/latest/amazon-corretto-11-x86-windows-jdk.msiを選択)
![](/images/aws-lambda-java-1/java-11-download.png)
* インストール
基本的にはNextを選択するだけでOK
![](/images/aws-lambda-java-1/java-11-install1.png)
![](/images/aws-lambda-java-1/java-11-install2.png)
![](/images/aws-lambda-java-1/java-11-install3.png)
完了
![](/images/aws-lambda-java-1/java-11-install4.png)
* インストール確認
msiファイルを使用してインストールをした場合は、自動でJAVA_HOMEとpathは設定される
powershellなどで`java --version`と入力して以下のように出力されればインストール完了
![](/images/aws-lambda-java-1/java-11-install5.png)
<br>

## Gradle インストール
* Gradleをダウンロード
[Gradle公式サイト](https://gradle.org/releases/)からGradleをダウンロード(今回はv8.0を使用)
![](/images/aws-lambda-java-1/gradle-install.png)
gradle-8.0.1-bin.zipがダウンロードされるので、cドライブ直下に解凍
* Gradleの環境変数設定
Windows→「設定」→「システム」→「詳細情報」→「システムの詳細情報」→「環境変数」から環境変数を設定する
C:\gradle-8.0.1\bin
![](/images/aws-lambda-java-1/gradle-install2.png)
powershellなどで`gradle -v`と入力して以下のように出力されればインストール完了
![](/images/aws-lambda-java-1/gradle-install3.png)
<br>

## Visual Stadio Code 設定
VscodeにJavaとGradleの拡張機能をインストール
* 「Extension Pack for Java」をインストール
![](/images/aws-lambda-java-1/vscode-setting1.png)
settings.jsonに下記を追加\n
(違う手順でjavaをインストールした場合はそのjdkフォルダを選択)
```"java.jdt.ls.java.home": "C:\\Program Files (x86)\\Amazon Corretto\\jdk11.0.18_10"```
![](/images/aws-lambda-java-1/vscode-setting3.png)

* 「Gradle for Java」をインストール
![](/images/aws-lambda-java-1/vscode-setting2.png)
<br>

## Docker インストール
ローカル環境でAWS Lambdaを動かす場合はDockerが必要
WindowsでDockerを使用する場合はwslが必要となるのでwslをインストールしていない場合は[Microsoft公式](https://learn.microsoft.com/ja-jp/windows/wsl/install)の手順でインストールしてください
* Dockerをダウンロード
[Docker公式サイト](https://www.docker.com/)からDockerをダウンロードしてインストールする
* インストール確認
powershellなどで`java --version`と入力して以下のように出力されればインストール完了
![](/images/aws-lambda-java-1/java-11-install5.png)
<br>

## aws-cli インストール
* [aws公式サイト aws-cli](https://docs.aws.amazon.com/ja_jp/cli/latest/userguide/getting-started-install.html)からインストーラーをダウンロード
基本的にはNextを選択するだけでOK
![](/images/aws-lambda-java-1/aws-cli-install1.png)
![](/images/aws-lambda-java-1/aws-cli-install2.png)
![](/images/aws-lambda-java-1/aws-cli-install3.png)
![](/images/aws-lambda-java-1/aws-cli-install4.png)
powershellなどで`aws --version`と入力して以下のように出力されればインストール完了
![](/images/aws-lambda-java-1/aws-cli-install5.png)
<br>

## aws sam-cli インストール
* [aws公式サイト sam-cli](https://docs.aws.amazon.com/ja_jp/serverless-application-model/latest/developerguide/install-sam-cli.html)からインストーラーをダウンロード
基本的にはNextを選択するだけでOK
![](/images/aws-lambda-java-1/sam-cli-install1.png)
![](/images/aws-lambda-java-1/sam-cli-install2.png)
![](/images/aws-lambda-java-1/sam-cli-install3.png)
![](/images/aws-lambda-java-1/sam-cli-install4.png)
powershellなどで`sam --version`と入力して以下のように出力されればインストール完了
![](/images/aws-lambda-java-1/sam-cli-install5.png)
<br>

## おわり
ローカル環境でAWS Lambdaを起動するための環境構築は以上となります。
次回は今回の掲示板APIで使用するDBなどのインフラ周りを準備します。
<br>