IntellJでプライベートなGitLabにアクセスする方法
-----

### 環境

* macOS Sierra 10.12.6
* PhpStorm 2018.3 EAP Build #PS-183.4284.100, built on November 14, 2018
* AWS EC2上に自社ホスティング
* URLは http://gitlab.example.com とする
* SSH秘密鍵ファイルの保存先は `~/.ssh/(SSH秘密鍵)` でパスフレーズを付けない

### 事前作業

1. 該当のGitLabログイン用のSSH鍵を作成する(既にあるまたはサーバ上で生成なら省略可)
1. GitLabのサイトを開き User Settings > Access Tokens からレポジトリ一覧取得用のトークンを作成し20文字の文字列をメモする
1. User Settings > SSH Keys から上記の公開鍵を登録する
    * もしくは [generate it.] で作成しダウンロードしてからパーミッションを変更
1. ~/.ssh/config に以下の行を追加
    * HostとHostNameの後には該当サーバのドメイン名を入力
    * ターミナルから `ssh gitlab.example.com` でアクセスできればOK
        * 自分は秘密鍵のパーミッションが間違っていてはまりました

```:config

Host gitlab.example.com
  HostName gitlab.example.com
  IdentityFile ~/.ssh/(SSH秘密鍵)
  AddKeysToAgent yes
  User git
  Port 22

```

### PhpStorm起動後の作業

1. 既に開いているプロジェクトがあれば閉じてウェルカム画面を出す
1. メニューバー > ソフト名 > Preferences を開く
    1. Preferences > Plugins を開き下記のプラグインを導入
        * GitLab Projects
        * GitLab integration
        * (これは必須で無い)EditorConfig
    1. Preferences > Version Control > GitLab > Add New GitLab Serverを開き下記の内容を入力
        * UI server : `http://gitlab.example.com`
        * Repository Url : `gitlab.example.com`
        * Personal Access Token : (Access Tokensでメモした文字列)
        * Prefferred checkout method : SSH
    1. Preferences > Version Control > Git
        * SSH executable : `Native`
    1. Preferences 画面右下のOKを押しWelcome画面に戻る
1. Welcome画面 > Check out from Version Control > Git
1. ここまで正しければURLにカーソル合わせたときに「GitLab Repositories (中略)(^Space)」と出るのでcontrol+Spaceを押すとレポジトリ一覧が表示される
    * 左下の[Log in to GitHub...]は無視して良い
1. 利用したいレポジトリを選択し [Clone] ボタンを押す
