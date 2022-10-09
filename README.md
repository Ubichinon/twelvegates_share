# 十二門GitHubへようこそ！

基本的には、このGitHubレポジトリ上でWeb/ITの情報を共有していきます。
同時に、**Discord上でレポジトリ変更の連絡をする**こととします。

### GitHub運用上の諸注意
***
1. 基本的に、文字のみの場合は**Markdown(.md)**ファイルに内容を記載すること。
2. Markdown記法は簡単。左記URLより適宜サンプル集を見ること　[Qiita先生](https://qiita.com/tbpgr/items/989c6badefff69377da7)
3. Gitの使い方をある程度わかっておくこと。(最低限、基礎コマンドとFork/Pull/Push/Clonくらいは)
4. Git/GitHubでわからないことがあれば、まずは[公式](https://docs.github.com/ja)
それでもダメならわかる人に聞く。
ほったらかしは×　適当にいじるのはもっと×　最悪Gitがクラッシュしたり、PCが逝ってしまう可能性もある。
5. 複数人で作業しているファイルは、GitHubで直接編集しない。

以上を守れば快適なGitライフが待っています!


## Gitの導入
***
### Git インストール
GitはGitクライアントとGitサーバを使って操作します。
以下、Windows向け説明です。

1. Git公式サイトからDL [Git公式](https://git-scm.com/)
2. インストール　基本全部next押してればOK

### Git Bash起動～ローカルディレクトリ作成
1. スタートメニューから「Git Bash」を探す。
2. 起動したら、[PCユーザー名@コンピュータ名　MINGW64 ~]と出ていればOK
3. ローカルディレクトリ(自分のPCにGit用のフォルダ)を作成する。下記のコマンドをGit Bashに入力。($マークは入力しない)
```
$ mkdir tg(半角英数字)
```

4. ディレクトリに何が入っているか確認する
-- カレントディレクトリ一覧に先ほど設定したディレクトリ名があればOK！

### Visual Studio Code ダウンロード
コード、Markdown、テキストはVSCodeで編集するのが楽なのでダウンロードします

1. [Microsoft公式](https://azure.microsoft.com/ja-jp/products/visual-studio-code/)からVSCodeダウンロード
2. インストール後、VSCode起動

### Gitの一般設定
ユーザー名、メールアドレス、エディタを設定して環境構築！

1. ユーザー名、メールアドレス設定 -> 設定内容確認
 1. ユーザー名設定
 ```
 git config --global user.name 好きな名前
 ```

 2. メールアドレス設定
 ```
 git config --global user.email 自分のメールアドレス
 ```

 3. 設定内容確認
 user.nameとuser.email先ほど設定した値と正しいかチェック！
 ```
 git config --list
 ```

2. エディタ設定
 1. Visual Studio Codeを設定する
 ```
 git config --global core.editor "code --wait"
 ```

 2. 設定内容確認
 下記コマンドを打って、code --waitと出ればOK
 ```
 git config core.editor
 ```


### ローカルリポジトリを作る
1. tgディレクトリに移動
 1. 先に作成した[tg]ディレクトリに移動する
 ```
 cd tg
 ```

 2. ローカルリポジトリ作成
 ```
 git init
 ```

 3. ディレクトリ内を確認
 下記コマンドを打って、.gitがあればOK
 ```
 ls -a
 ```

### GitHubを登録する
1. [GitHub公式](https://github.com/)でアカウント作成
プランは、「フリープラン」でOK


### GitHubに公開鍵を設定する
1. SSH Keyの生成
Git Bash上で、以下のコマンドを実行する
```
ssh-keygen -t ed25519 -C "自分のメールアドレス"
```


2. 鍵の保存場所を確認する
「Enter file in which save the key」と出たらEnterを押す

3. パスワード設定
Enter Passphraseと出たら、好きなパスワードを入れる。
GitHubのパスワードとは違うフレーズを設定する

4. 生成した公開鍵をクリップボードにコピー
以下のコマンドをGit Bashで打つと、「ctrl+c」でコピーしたのと同義になる。
```
clip < /c/Users/自分のPCユーザー名/.ssh/id_ed25519.pub
```

5. GitHubの設定画面で公開鍵を貼り付ける
 1. GitHubの右上アイコンをクリック
 2. Settingsを選択
 3. SSH and GPG keysを選択
 4. 緑のNew SSH keysをクリック
 5. title(なんでもいい)を入力後、Key欄に公開鍵をペースト[ctrl+v] 

6. Git Bashで確認用コマンドを入力
GitHubで鍵の設定がうまくいったか確認するため、以下のコマンドを入力
```
ssh -T git@github.com
```
**「Are you sure you want to continue connecting(yes/no/[fingerprint])」は「yes」と入力**

7. 3で設定したパスフレーズを入力
「Hi ユーザー名! You're Successfully authenticated」と表示されればOK！

### GitHubからプロジェクトをフォーク
1. リモートリポジトリは下記URL。「Fork」ボタンを押すだけ
https://github.com/Ubichinon/twelvegates_share.git


### フォークしたプロジェクトをローカル環境にクローンする
1. GitHub上でクローンに必要なURLを取得する
フォークしたリポジトリ内のCode(緑のボタン)からSSHタブを選択、URLをコピーする

2. クローンを実行(Git Bash上)
以下を入力
```
git clone git@github.com:Ubichinon/twelvegates_share.git
```

3.クローンされたリポジトリのディレクトリに移動する(Git Bash上)
```
cd twelvegates_share/
```

### 終わりに
とりあえずのGit/GitHub導入までを行いました。

実際にローカル(Git)からリモート(GitHub)に上げるための方法は、別で資料を作りたいと思います。

読んでいただきありがとうございます！

2022.10.07 Kei Miyakawa