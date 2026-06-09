# English Words

GitHub Pages で公開するための英単語リストです。`index.html` が `words.csv` を読み込み、英単語の一覧表示とランダムクイズを行います。

## ファイル構成

```text
.
├── index.html   # GitHub Pages で表示されるページ
└── words.csv    # 英単語データ
```

## CSV の形式

`words.csv` は次の列を持つ CSV ファイルです。

```csv
english,japanese,example
progress report,進捗報告,I will give a short progress report today.
```

- `english`: 英単語または英語表現
- `japanese`: 日本語訳
- `example`: 例文

`english` と `japanese` は必須です。`example` は省略できます。

## GitHub Pages の公開設定

このリポジトリを GitHub Pages で公開するには、GitHub 上で次の設定を行います。

1. GitHub のリポジトリページを開く
2. `Settings` を開く
3. 左メニューの `Pages` を開く
4. `Build and deployment` の `Source` を `Deploy from a branch` にする
5. `Branch` を `main`、フォルダを `/ (root)` にする
6. `Save` を押す

設定後、数分待つと次の形式の URL で公開されます。

```text
https://<GitHubユーザー名>.github.io/<リポジトリ名>/
```

このリポジトリの場合、`index.html` がルートにあるため、`/(root)` を選択すればそのまま公開できます。

## リポジトリを Public にする

無料プランで GitHub Pages を使う場合、通常はリポジトリを Public にします。

1. GitHub のリポジトリページを開く
2. `Settings` を開く
3. `General` の一番下にある `Danger Zone` まで移動する
4. `Change repository visibility` を選ぶ
5. `Make public` を選択して確認する

Public にすると、リポジトリ内のファイルは誰でも閲覧できます。公開したくない情報は含めないでください。

## 更新方法

単語を追加・修正する場合は、`words.csv` を編集してコミット、プッシュします。

```bash
git add words.csv
git commit -m "Update words"
git push
```

GitHub Pages には自動で反映されます。反映までに数十秒から数分かかることがあります。

## ローカルで確認する

`index.html` はブラウザで開けますが、ブラウザの制限により `words.csv` の自動読み込みに失敗する場合があります。その場合は、画面上部のファイル選択から `words.csv` を選んで確認できます。

自動読み込みも含めて確認したい場合は、簡易サーバーを起動します。

```bash
python3 -m http.server 8000
```

その後、ブラウザで次の URL を開きます。

```text
http://localhost:8000/
```
