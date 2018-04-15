# Git勉強会
- 2018/4/17

## はじめに
gitをインストールしましょう
- Macの人
    1. ``homebrew``のインストール  
    パッケージ管理ツール。入れとくと色々と便利  
    python入れてる人はいろいろとめんどくさくなるので、ぐぐるとよい。今回は省略
    ```
    $ ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
    ```
    1. ``homebrew``がちゃんと入ってるか確認
    ```
    $ brew doctor
    Your system is ready to brew.
    ```
    1. ``git``のインストール
    ```
    $ brew install git
    ```
    1. アップデート
    ```
    $ brew update && brew upgrade
    ```
    1. ``git``がインストールされているか確認する
    ```
    $ git --version
    ```

- Windowsの人
    1. bashがいいよねってことで、[``WSL(Windows Subsystem for Linux)``を入れる](http://www.atmarkit.co.jp/ait/articles/1608/08/news039.html)  
    旧: ``Bash on Ubuntu``ベータ版が正式にリリースされたっぽい。すばら
    1. アップデート
    ```
    $ sudo apt-get update && sudo apt-get upgrade
    ```
    1. ``git``がインストールされているか確認する
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
