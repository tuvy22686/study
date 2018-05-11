# Android

## Debug編

- PCからAndroidにコピペしたい
    - コマンド
        - `adb shell input text '打ちたい文字列'`
    - 注意点
        - PCに複数の実機やエミュレータが接続しない
        - 文字入力エリアにカーソルを合わせ、例えば英字を入力したいなら英字が入力できるキーボードを表示する

- アプリで現在表示しているActivity名を知りたい
    - コマンド
        - `adb shell dumpsys activity`
    - 注意点
        - PCに複数の実機やエミュレータが接続しない