# shellscript

## test
`[ ... ]`より`[[ ... ]]`を使ったほうがいいらしい

> bashには`[[ ... ]]`という文法もあり、testコマンドとほぼ同じ使い方ができます。こちらはクォートが不要・追加のオプションや文字列のパターンマッチングが行えます。
> https://sc.megabank.tohoku.ac.jp/ph3-doc/howto/linux/script.html#index-10

## コマンドの判定
`command -v $target >/dev/null`を使う
反転したいときは`! command -v $target >/dev/null`

ref: https://qiita.com/kawaz/items/1b61ee2dd4d1acc7cc94
