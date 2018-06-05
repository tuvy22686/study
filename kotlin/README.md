# Kotlin

## セットアップ
Kotlinを使えるように環境を設定する(java入ってる前提)
- めんどくさい人は[こちら](https://try.kotlinlang.org/)
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
    3. ``kotlin``をインストール
    ```
    $ brew install kotlin
    ```
    4. 確認
    ```
    $ kotlin -version
    Kotlin version 1.2.41-release-74 (JRE 1.8.0_171-b11)
    ```
- Windowsの人
    1. bashがいいよねってことで、[``WSL(Windows Subsystem for Linux)``を入れる](http://www.atmarkit.co.jp/ait/articles/1608/08/news039.html)  
    旧: ``Bash on Ubuntu``ベータ版が正式にリリースされたっぽい。すばら
    2. コマンドプロンプトを開く
    3. ``bash``コマンドを叩く
    4. アップデート
    ```
    $ sudo apt-get update && sudo apt-get upgrade
    ```
    5. ``kotlin``のインストール
    ```
    $ sudo apt-get install kotlin
    ```
    6. 確認
    ```
    $ kotlin -version
    Kotlin version 1.2.41-release-74 (JRE 1.8.0_171-b11)
    ```

## Kotlinの書き方
- HelloWorldをコンソール上に表示する
```
fun main(args: Array<String>) {
    println("Hello world.")
}
```

## コンパイルと実行
- コンパイル
```
$ kotlinc Hello.kt
```
- 実行
```
$ kotlin HelloKt
```

## KotlinとJavaを比較して見る
- [こちら](https://github.com/tuvy22686/KotlinandJava)
