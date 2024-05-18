# Zsh

存在しないディレクトリを追加しないために`(N-/)`をつける
```
path=(
  $GOPATH/bin(N-/)
  $path
)
```

> /: directories
> -: plain files
> N: sets the NULL_GLOB option for the current pattern

ref:
- https://zsh.sourceforge.io/Doc/Release/Expansion.html#Glob-Qualifiers
- [zsh で path にディレクトリを追加するときは (N-/) を付けよう #Zsh - Qiita](https://qiita.com/mollifier/items/42ae46ff4140251290a7)
