# zenn-content-sample

Docker、Dev Containerを利用したZenn CLIの環境例です。

## 使い方

最初にVSCodeで開き、Dev Containerでコンテナを起動する。
その後は拡張機能のZenn Editorを利用し、記事を執筆する。

### 画像の貼り付け

VSCodeでファイルを開いて `Ctrl` + `V` とすると、クリップボードにコピーした画像を以下のようなマークダウン記法で挿入できる。
また、画像は `images/{articles or books}/{slug}/` に保存される。

``` markdown
![alt text](../images/articles/sample-20240528/image.png)
```

ただし、Zenn CLIでは `/images/` から始まる絶対パスを指定する必要があるので、以下のように修正する。

``` markdown
![alt text](/images/articles/sample-20240528/image.png)
```

### textlint

拡張機能のvscode-textlintを利用して文章の校正をしている。
ある程度必要とされる設定については既に記述されている。
設定を変更する場合は `.textlintrc` を編集する。
