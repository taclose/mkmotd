指定された画像をsshログイン時にコンソールで表示できるドット絵に変換するコマンドを作りました。

オプション指定でサイズや背景色も変更可能です。

![military_ssh](https://user-images.githubusercontent.com/112845363/207766376-f46856e3-1c9c-4fc7-b260-ca991cda2a47.gif)

# 使い方

```sh
// 一番ミニマムな例　画像パスだけ指定
$ mkmotd.sh -p "logo.png"

// 一番ミニマムな例　画像URLだけ指定
$ mkmotd.sh -p "https://www.rakus.co.jp/images/common/favicon.png"

// フルで指定（デフォルト値）
$ mkmotd.sh --path "logo.png" --size 32 --trans-position 0,0 --background "0;0;0"

// サイズは48px、左上から5,5の座標の色が背景色、この背景色を赤にする
$ mkmotd.sh --path "logo.png" --size 48 --trans-position 5,5 --background "255;0;0"
```

# 必要なツール

```
$ yum install -y ImageMagick
```

# コマンドのオプション

|option|default|説明|
|---|---|---|
|-p, --path|無し（必須指定）|ファイルパスかhttpから始まるURLを指定してください。http指定の場合はwgetコマンドも必要です。|
|-s, --size|32|画像サイズを変更します。コンソール表示を考えると16～64辺りが妥当です。|
|-t, --trans-position|0,0|左上からの座標を指定。指定された座標にある色を背景色として変更対象とします。|
|-b, --background|0;0;0|背景色と指定された色をRGBで指定された色に変換します。0～255でRGBを指定してください。ex：赤なら"255;0;0"です。|






