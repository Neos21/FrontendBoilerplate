# Frontend Boilerplate

オレオレフロントエンドボイラープレートです。

- HTML・CSS・SASS・SCSS・JS・ES2015 に対応しています。
- ESLint と Atom エディタの Linter シリーズを利用して、エディタ上での Lint を行います。
- EditorConfig と AtomBeautify を利用して、スタイル整形を行います。

<table>
  <tr>
    <th>Genre</th>
    <th>Package</th>
    <th>Name</th>
    <th>Setting File<br></th>
    <th>HTML<br></th>
    <th>CSS</th>
    <th>SASS</th>
    <th>SCSS</th>
    <th>JS</th>
    <th>ES2015</th>
  </tr>
  <tr>
    <td rowspan="6">Linter</td>
    <td>apm</td>
    <td>linter<br></td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
    <td>-</td>
  </tr>
  <tr>
    <td>apm</td>
    <td>linter-htmlhint</td>
    <td>.htmlhintrc</td>
    <td>○<br></td>
    <td><br></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>apm</td>
    <td>atom-csslint<br></td>
    <td>.csslintrc</td>
    <td></td>
    <td>○</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>apm</td>
    <td>linter-sass-lint</td>
    <td>.sass-lint.yml</td>
    <td></td>
    <td></td>
    <td>○</td>
    <td>○</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>apm</td>
    <td>linter-eslint</td>
    <td rowspan="2">.eslintrc</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>○</td>
    <td>○</td>
  </tr>
  <tr>
    <td>npm</td>
    <td>eslint<br></td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>○</td>
    <td>○</td>
  </tr>
  <tr>
    <td rowspan="5">Beautify</td>
    <td>apm</td>
    <td>EditorConfig</td>
    <td>.editorconfig</td>
    <td>○</td>
    <td>○</td>
    <td>○</td>
    <td>○</td>
    <td>○</td>
    <td>○</td>
  </tr>
  <tr>
    <td>apm</td>
    <td>atom-beautify : JSBeautify<br></td>
    <td>.jsbeautifyrc</td>
    <td>○</td>
    <td>○</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>apm</td>
    <td>atom-beautify : SassConvert<br></td>
    <td>-<br></td>
    <td></td>
    <td></td>
    <td>○</td>
    <td><br></td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>apm</td>
    <td>atom-beautify : Pretty Diff</td>
    <td>-<br></td>
    <td></td>
    <td></td>
    <td></td>
    <td>○</td>
    <td></td>
    <td></td>
  </tr>
  <tr>
    <td>apm</td>
    <td>atom-beautify : ESLint Fixer<br></td>
    <td>.eslintrc</td>
    <td></td>
    <td></td>
    <td></td>
    <td></td>
    <td>○</td>
    <td>○</td>
  </tr>
</table>


## apm (Atom)

```sh
# Atom エディタに Lint 系のパッケージをインストールする
# エディタ上でインストールしても OK
$ apm install linter
$ apm install linter-eslint linter-htmlhint linter-sass-lint atom-csslint
$ apm install editorconfig atom-beautify
```

- linter に合わせて intentions・busy-signal もインストールされるかも。


## JavaScript・ES2015 : eslint・linter-eslint

```sh
# package.json を作る
$ npm init

# eslint をインストールする
$ npm i eslint -D

# 初期設定
$ ./node_modules/eslint/bin/eslint.js --init
# プロンプトに従って設定する。設定によっては ESLint プラグインがインストールされ、devDependencies に自動追記される
# .eslintrc (.json や .js) が生成される

# 無視したいファイルやフォルダは .eslintignore で指定する
$ touch .eslintignore
```

- [ESLint Rules](http://eslint.org/docs/rules/)
- npm install 後に「No repository field」エラーが出る場合は、`package.json` に `"private": true` と追記する。
- 「ESLint not found, please ensure the global Node path is set correctly.」というエラーが出る場合は linter-eslint の Settings で「Use global ESLint installation」のチェックを外す。
- atom-beautify の Beautifier を「ESLint Fixer」にしておくと `.eslintrc` の設定を使って整形してくれる。linter-eslint の「Fix errors on save」は機能が重複するので切っておいて良い。


## HTML : linter-htmlhint

```sh
# .htmlhintrc を作る
$ touch .htmlhintrc
```

- [HTMLHint Rules](https://github.com/yaniswang/HTMLHint/wiki/Rules)
- atom-beautify の Beautifier を「JSBeautify」にしておくと `.jsbeautifyrc` の設定を使って整形してくれる。


## CSS : atom-csslint

```sh
# .csslintrc を作る
$ touch .csslintrc
```

- [CSSLint Rules](https://github.com/CSSLint/csslint/wiki/rules)
- [CSSLint の Rules の超訳](https://gist.github.com/hail2u/1303613)
- 同様のパッケージに「linter-csslint」というパッケージがあり、こちらも動作はするが、`.csslintrc` による設定変更が効かないため、atom-csslint を使用する。
- atom-beautify の Beautifier を「JSBeautify」にしておくと `.jsbeautifyrc` の設定を使って整形してくれる。


## SASS・SCSS : linter-sass-lint

```sh
# .sass-lint.yml を作る
$ touch .sass-lint.yml
```

- [.sass-lint.yml Example](https://github.com/sasstools/sass-lint/blob/master/lib/config/sass-lint.yml)
- atom-beautify で SASS・SCSS の Beautifier に「SassConvert」を選ぶと、整形時に改行コードが CR+LF に変換されてしまう。SASS は「SassConvert」以外の Beautifier が選べないため、「Beautify On Save」のチェックは外しておき、手動で Beautify 後、line-ending-selector で改行コードを LF にし直すと良いだろう。SCSS は Beautifier に「Pretty Diff」を選択すれば CR が付与されずに整形される。
- language-sass のバグのせいか、SCSS の Tab Length が 2 に変更できない。ファイル → 個人設定 で `config.cson` を開き、以下の部分を修正すると反映できる。

```json
".css.source":
  editor:
    tabLength: 4  ← ココを 2 にする
```


## EditorConfig : editorconfig

```sh
# .editorconfig を作る
$ touch .editorconfig
```

- [EditorConfig Example](http://editorconfig.org/#example-file)
- Atom エディタの設定と重複する設定項目があるとエラー扱いになる。


## AtomBeautify : atom-beautify

- 保存時に Beautify を行うなどの設定は Package の Settings より行う。設定情報は `config.cson` に記載される


## TODO

- 各コードのビルド前に Lint を行う Gulp タスクを作成する。
- HTML・CSS : 空行のインデントが保持されない。`.jsbeautifyrc` に空行のインデントを保持する設定がなさそう？
- SASS : 空行のインデントが保持されない。コメントに日本語を含んでいると Beautify 時にエラー扱いになる。「SassConvert」(と内部で使用していると思われる SassBeautify) の仕様によるものかも？
- SCSS : 空行のインデントが保持されない。「Pretty Diff」で設定する方法があるかな？


## Author

[Neo](http://neo.s21.xrea.com/) ([@Neos21](https://twitter.com/neos21))


## Links

- [Neo's World](http://neo.s21.xrea.com/)
- [Corredor](http://neos21.hatenablog.com/)
- [Murga](http://neos21.hatenablog.jp/)
- [El Mylar](http://neos21.hateblo.jp/)
- [Bit-Archer](http://bit-archer.hatenablog.com/)
- [GitHub - Neos21](https://github.com/Neos21/)
