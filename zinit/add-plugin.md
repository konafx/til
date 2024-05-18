# Add plugin

## my rule
- 記法を統一
  - ダブルクオーテーションを使う `modifiers"argument"`
    - IMO: shift押さなくて済むから`'`が楽。zinitのREADMEが`"`なのでそれに合わせる
    - `$`が即時評価されてしまう。plugconfs/に退避するのもあり
  - `zinit`を略さず書く

## References
- [zdharma-continuum/zinit](https://github.com/zdharma-continuum/zinit)
- [Zinit Wiki](https://zdharma-continuum.github.io/zinit/wiki/)
- annexes
  - [zdharma-continuum/zinit-annex-bin-gem-node](https://github.com/zdharma-continuum/zinit-annex-bin-gem-node)
    - `sbin`など
  - [zdharma-continuum/zinit-annex-binary-symlink](https://github.com/zdharma-continuum/zinit-annex-binary-symlink)
    - `lbin`
- [zinit をしっかりと理解する](https://zenn.dev/xeres/articles/2021-05-05-understanding-zinit-syntax)

## syntax
```zsh
	zinit wait lucid \
		from"gh-r" mv"ripgrep* -> rg" \
		sbin"rg/rg" \
		for @BurntSushi/ripgrep
```

- `\`を使って改行できる。`\`以降の改行、空白は無視される

### wait
Turbo mode
- `wait`=`wait"0"`
- `wait"1"`: wait a second
- `wait"2"`: wait two seconds

#### wait exclamation
`wait"!"`: re-rendering prompt [^wait-exclamation]

#### lucid
quiet option
> Turbo mode is verbose, so you need an option for quiet.

<!--
動くが動作が不安定、zinitはTurboでまずは書く
### zsh-defer
[romkatv/zsh-defer](https://github.com/romkatv/zsh-defer)

[`wait`](#wait)の互換

デフォルトで`12dmshpr`のオプションがONになっている

- [`wait"!"`](#wait-exclamation)=`zsh-defer +p -`
- [`lucid`](#lucid)=`zsh-defer +1`(stdout) or `zsh-defer +2`(stderr)
- `wait"1"`=`zsh-defer -t 1`
- `wait"2"`=`zsh-defer -t 2`

以下２つのコマンドはほぼ同じ（`lucid`のstderrまわりが分からない）
```zsh
zinit wait"!2" lucid from"gh-r" as"program" sbin"**/gh" for @cli/cli
zsh-defer -a +1p -t 2 zinit from"gh-r" as"program" sbin"**/gh" for @cli/cli
```
-->

### mv
[sharkdp/fd](https://github.com/sharkdp/fd)を`from"gh-r"`で引っ張ってみると以下のようにディレクトリ名が`fd-{version}-{distro}`と煩雑になる
```
.zinit/plugins/sharkdp---fd
└── fd-v10.1.0-x86_64-unknown-linux-gnu
   ├── autocomplete
   │  ├── _fd
   │  ├── fd.bash
   │  ├── fd.fish
   │  └── fd.ps1
   ├── CHANGELOG.md
   ├── fd
   ├── fd.1
   ├── LICENSE-APACHE
   ├── LICENSE-MIT
   └── README.md
```
`mv"fd-* -> fd"`で簡潔にできる

```zsh
zinit from"gh-r" mv"fd* -> fd" sbin"fd/fd" for @sharkdp/fd
```



---

[^wait-exclamation]: questionable
