# zenn-content-sample

Docker、Dev Containerを利用したZenn CLIの環境例です。

## 使い方

最初にVSCodeで開き、Dev Containerでコンテナを起動した後に拡張機能のZenn Editorを利用して記事を執筆します。

普段はmainブランチと別のブランチで作業し、mainブランチにPRすることを想定しています。
mainブランチへのPR時にGitHub Actionsでtextlintによる校正が行われます。

### 画像の貼り付け

VSCodeでファイルを開いて `Ctrl` + `V` とすると、クリップボードにコピーした画像を以下のようなマークダウン記法で挿入できます。
また、画像は `images/{articles or books}/{slug}/` に保存されます。

``` markdown
![alt text](../images/articles/sample-20240528/image.png)
```

ただし、Zenn CLIでは `/images/` から始まる絶対パスを指定する必要があるので、以下のように修正する必要があります。

``` markdown
![alt text](/images/articles/sample-20240528/image.png)
```

### 文章の校正

[使い方](#使い方)でも書いたようにmainへのPR時にtextlintによる校正が行われます。
また、ローカルでも拡張機能のvscode-textlintを利用して文章の校正が可能です。

校正の設定は `.textlintrc` に記述されています。

#### 修正

textlintによる指摘点の中には機械的に修正可能なものがあります。
VSCodeのターミナルで `npm run fix` を実行することでこれらの修正が行われます。
修正の対象となるのはorgin/mainブランチとの差分があるファイルです。
