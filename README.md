**Rocky LinuxでGitHubとGitを使用して共同開発する方法**
=====================================

### Gitのインストール

Rocky Linuxには、デフォルトでGitがインストールされていません。以下のコマンドを実行してGitをインストールしてください。
```bash
sudo dnf install git
```
### GitHubアカウントの作成

GitHubアカウントを作成するには、以下の手順に従ってください。

1. [GitHubのウェブサイト](https://github.com/)にアクセスします。
2. 右上の「Sign up」ボタンをクリックします。
3. ユーザー名、メールアドレス、パスワードを入力して「Create account」ボタンをクリックします。

### Gitの設定

Gitを使用する前に、以下のコマンドを実行してGitの設定を行ってください。
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```
### SSHの設定

GitHubにSSH接続するには、以下の手順に従ってください。

1. SSHキーペアを作成します。
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```
2. 公開鍵をGitHubに追加します。
```bash
cat ~/.ssh/ed25519.pub
```
3. GitHubの設定ページに移動し、SSHとGPGキーのページを開きます。
4. 「New SSH key」ボタンをクリックし、公開鍵を貼り付けます。
5. 「Add SSH key」ボタンをクリックします。

### リポジトリの作成

新しいリポジトリを作成するには、以下のコマンドを実行してください。
```bash
mkdir myproject
cd myproject
git init
```
### ファイルの追加とコミット

ファイルを追加してコミットするには、以下のコマンドを実行してください。
```bash
touch README.md
git add README.md
git commit -m "Initial commit"
```
### リモートリポジトリの追加

GitHubにリポジトリを作成し、ローカルのリポジトリをリモートリポジトリに接続するには、以下のコマンドを実行してください。
```bash
git remote add origin git@github.com:your_username/your_repo_name.git
git push -u origin master
```

### リモートリポジトリの更新

リモートリポジトリが更新されてローカルリポジトリにその変更を加えたいときは、以下のコマンドを実行してください。
```bash
git pull
```

### Pull Requestの作成

Pull Requestを作成するには、以下の手順に従ってください。

1. GitHubのウェブサイトにアクセスします。
2. リポジトリのページに移動します。
3. 右上の「New pull request」ボタンをクリックします。
4. Pull Requestのタイトルと説明を入力して、「Create pull request」ボタンをクリックします。

### Pull Requestのmerge

Pull Requestをmergeするには、以下の手順に従ってください。

1. GitHubのウェブサイトにアクセスします。
2. リポジトリのページに移動します。
3. Pull Requestのページに移動します。
4. mergeするPull Requestを選択します。
5. 「Merge pull request」ボタンをクリックします。

### Gitの基本コマンド

以下は、Gitの基本的なコマンドです。

* `git init`: リポジトリを初期化します。
* `git add <file>`: ファイルをステージングエリアに追加します。
* `git commit -m "<message>"`: 変更をコミットします。
* `git log`: コミット履歴を表示します。
* `git branch`: ブランチの一覧を表示します。
* `git checkout <branch>`: ブランチを切り替えます。
* `git merge <branch>`: ブランチをマージします。
* `git remote add <name> <url>`: リモートリポジトリを追加します。
* `git push`: 変更をリモートリポジトリにプッシュします。
* `git pull`: リモートリポジトリの変更をプルします。
