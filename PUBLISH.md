# ChromebookからGitHub Pagesへ公開

このアプリはビルド不要です。`index.html` をそのまま公開できます。
GitHub FreeではPublic（公開）リポジトリを使います。アプリのソースコードとページが公開されます。勉強記録は各利用者のブラウザに保存され、GitHubには送られません。

## 公開する構成

リポジトリ名を `study-app` にし、その直下に次のファイルを置きます。リポジトリ内にさらに `study-app` フォルダを作る必要はありません。

```text
index.html
.nojekyll
.gitignore
README.md
PUBLISH.md
```

`.nojekyll` はHTMLをそのまま配信するための空ファイルです。`.gitignore` は記録のバックアップなどをGitへの追加対象から除外します。

## 対話で進める最初の手順

ChromebookのLinuxターミナルで、以下を実行します。

```bash
cd ~/study-app && ls -a
```

`index.html` と `.nojekyll` が表示されたら準備できています。「そのようなファイルやディレクトリはありません」と出たら、ファイルの保存場所を確認してから進めます。空のフォルダを作って進めないでください。

## この後の流れ

対話では、実行結果を確認してから1手順ずつ案内します。

1. GitとGitHub CLIの有無を確認し、必要ならインストールします。
2. GitHubアカウントで、GitHub CLIのブラウザ認証を行います。
3. `study-app` フォルダだけをGit管理し、ブランチ名を `main` にします。コミット用の名前とメールアドレスはこのリポジトリに設定します。メールにはGitHubのSettings → Emailsに表示されるnoreplyアドレスも使えます。
4. 公開用の上記5ファイルを指定してコミットします。勉強記録のJSONファイルは追加しません。
5. 自分のGitHubアカウントにPublicの `study-app` リポジトリを作り、アップロードします。同名のリポジトリがある場合は、その状態を確認してから進めます。
6. GitHubのリポジトリでSettings → Pagesを開きます。Sourceを「Deploy from a branch」、Branchを「main」、フォルダを「/ (root)」にしてSaveを押します。
7. デプロイが完了したら、Pagesに表示される公開URLを開きます。通常は `https://ユーザー名.github.io/study-app/` です。反映まで数分かかる場合があります。

独自ドメインや有料プランは不要です。公開URLはChromebookやスマホのChromeで開けます。

## 以前の記録を公開サイトへ移す

ローカルファイルと公開サイトは保存場所が異なるため、自動では記録を引き継ぎません。

1. 今まで使っていたアプリで「バックアップを保存」を押します。
2. 公開URLを開き、「バックアップを復元」でそのJSONファイルを選びます。
3. 受験日は別途設定してください。バックアップには受験日の設定は含まれません。

記録のバックアップはGitHubにアップロードしないでください。スマホとChromebookの記録は自動同期しません。

## 公開後の確認

- 科目と30分を記録し、集計が更新されること。
- 再読み込みしても記録が残ること。
- テスト用に作った記録を削除すると集計が戻ること。
- スマホでも記録フォームとグラフを表示できること。

公式手順：https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
