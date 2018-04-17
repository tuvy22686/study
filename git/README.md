# Git
- 2018/4/17
- WestKazuki24
- oybn
- TakuyaNiimura
- Niimura
- tuvy
- mia

## セットアップ
gitをインストールしよう
- Macの人
    1. ``homebrew``のインストール  
    パッケージ管理ツール。入れとくと色々と便利  
    python入れてる人はいろいろとめんどくさくなるので、ぐぐるとよい。今回は省略
    ```
    $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    ```
    2. ``homebrew``がちゃんと入ってるか確認
    ```
    $ brew doctor
    Your system is ready to brew.
    ```
    3. ``git``のインストール
    ```
    $ brew install git
    ```
    4. アップデート
    ```
    $ brew update && brew upgrade
    ```
    5. ``git``がインストールされているか確認する
    ```
    6 git --version
    ```

- Windowsの人
    1. bashがいいよねってことで、[``WSL(Windows Subsystem for Linux)``を入れる](http://www.atmarkit.co.jp/ait/articles/1608/08/news039.html)  
    旧: ``Bash on Ubuntu``ベータ版が正式にリリースされたっぽい。すばら
    2. アップデート
    ```
    $ sudo apt-get update && sudo apt-get upgrade
    ```
    3. ``git``がインストールされているか確認する
    ```
    $ git --version
    ```

## 設定
こっからはおそらく、windowsもmacも同じ
- 参考資料
    - [Gitをインストールしたら真っ先にやっておくべき初期設定](https://qiita.com/wnoguchi/items/f7358a227dfe2640cce3)

- ユーザ情報の設定  
gitにはコードを書いた人の情報が保存される機能がある。たしかここで設定した名前、メールアドレスが参照される
```
$ git config --global user.name "{名前}"
$ git config --global user.email "{メアド}"

/** 例えば **/
$ git config --global user.name "hoge fuga"
$ git config --global user.email "doremi@me.ac.jp"
```

- エディタの設定
```
$ git config --global core.editor '{エディタ} -c "set fenc=utf-8"'

/** 例えば **/
$ git config --global core.editor 'vim -c "set fenc=utf-8"'
```

- 設定の確認
```
$ git config --list
```

## Git用語
- repository
- commit
- branch
- push
- pull
- merge
- HEAD

## Gitを使ってみよう
1. 適当なディレクトリを作りましょう
```
$ mkdir Workspace
```
2. 適当なファイルを作りましょう
```
$ echo "# hoge" >> README.md
```
3. git管理下においてみましょう
```
$ git add Workprace/README.md
```
4. 変更の履歴を残しましょう
```
$ git commit -m 'first commit'
```

## Gitのここが便利
- 歴史を遡ることができる
```
$ git log
commit 93fa8802d2d24ddbacac73398ba33cec8f50cebe (HEAD -> master, origin/master)
Author: Tomosugi Tasaka <tuvy.ano@gmail.com>
Date:   Sun Apr 15 18:59:25 2018 +0900

    fix

commit 777dff92285ca81e994c8ab3daacbffb93243389
Author: Tomosugi Tasaka <tuvy.ano@gmail.com>
Date:   Sun Apr 15 18:55:54 2018 +0900

    first commit
```
コミットにはそれぞれチェックIDが振られていて、指定したコミットに戻ることができる
```
$ git checkout 777dff92285ca81e994c8ab3daacbffb93243389
```

- やっぱ元に戻したい(コミットする前)
```
$ git checkout {ファイル名}
```

- やっぱ元に戻した(コミットした後)
```
$ git reset --hard HEAD^
```

- 前ってどう書いてあったっけ？差分をみたい
```
$ git diff
```

## Git事故例
- コミットメッセージ間違えた！
```
$ git commit --amend
```

- コンフリクトした
    1. どこでコンフリクトしたかを確認
    ```
    $ git status
    ```
    2. ファイルの修正
    3. コンフリクトが解消したかを確認
    ```
    $ git status
    ```
    4. コンフリクトが解消していなかったら2へ、解消していたら
    ```
    $ git add {ファイル名}
    $ git commit
    ```

- 間違えてマージしちゃった
下記のコマンドで一つ前のコミットに戻ることができる
```
$ git reset --hard HEAD^
```

- 間違えてマージしたのをPUSHしちゃった
方針としてリモートとローカルレポジトリで作業を行わなければならない
    1. リモートレポジトリのマージコミットコミット取り消し
    ```
    $ git push -f origin {ブランチ統合前のコミットID}:{プッシュを取り消したいブランチ名}
    ```
    2. ローカルレポジトリのマージコミット取り消し
    ```
    $ git rebase -i {マージする前の戻りたいコミットのID}
    ```

## よく使うコマンド一覧
- ``git init``
- ``git status``
- ``git add``
- ``git commit``
- ``git push``
- ``git pull``
- ``git branch``
- ``git log``
