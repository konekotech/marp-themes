---
marp: true
size: 4:3
theme: microsoft-test
paginate: true
footer: "@konekotech All rights reserved."
---

<!--
_class: top
-->

# $\LaTeX$ install challange !

## Mac 編

## @konekotech

---

- macOS Sonoma 14.4.1 で動作確認済み

---

# $\LaTeX$ 、**組み版ソフトの一種です**

- _組み版システム_ の一種**となる**
- 数式や図表を含む文書を作成するための言語

---

# _Word_ との違い

## Word: WYSIWYG (What You See Is What You Get)

みたままが出力される（文書をそのままいじってる感じ）

## $\LaTeX$: WYSIWYM (What You See Is What You Mean)

コードを書くことによって文書を作成する

---

# $\LaTeX$のいいところ

- 数式が綺麗に書ける
- 誰が書いても同じになる（Word は Windows か Mac かで画面が変わったり...）
- 壊れにくい
  （Word はバージョンが異なることによるファイル破損が起こったり、数式がぶっ壊れたり......）
- `label`や`ref`を使って、数式や図表の参照番号を自動で振れる
- わからないことがあったときに`ChatGPT`に聞きやすい
  （Word はバージョンによって操作が変わるので変なことを言ってくることがあるが、$\LaTeX$はただのテキストなので的確に教えてくれる）
- `Git`（バージョン管理システム）で管理できる

---

# $\LaTeX$の悪いところ

- 使い方が難しい
  （少し凝ったことをしようと思うと、ちょっと頑張らなきゃいけない）
- エラーが出ると怖い
  （エラーがちょっと不親切なので、あまり的確じゃないこともある）
- 図表の挿入が面倒
  （表も全部コードなので......）
- `jpeg`などの特定の画像形式に対応していないことがある
  （`png`や`pdf`などの画像形式に変換する必要がある）

---

# $\LaTeX$の種類

## $\TeX$の種類

- `TeX`（テフ）
  - $\LaTeX$の元になったもの
- `LaTeX`（ラテフ）
  - `TeX`を拡張してもう少し使いやすくしたもの
  - `LaTeX2e`（ラテフツーイー）が最新

## $\LaTeX$の種類

- `pLaTeX`（コンリテで使うやつ。基礎科学実験のテンプレートもこれ。近々日本語が使えなくなるかも）
- `upLaTeX`（`Unicode`に対応した`pLaTeX`。近々日本語が使えなくなるかも）
- `LuaLaTeX`（フォント周りとかがさらに使いやすくなったやつ。現在の推奨。）

---

# $\LaTeX$のインストール

## 今回動作を確認するのは`pLaTeX`です

- 本学の授業で広く使われている
- 使い古されているので、情報が多い

## こだわる人は`LuaLaTeX`を使うといいかも？

- 最新の機能が使える
- `Lua`というプログラミング言語が使えるので、自動化がさらに簡単に

## Google 検索における注意

- Google で「LaTeX インストール」と検索すると一番上に出てくる記事では`LuaLaTeX`が使われているが、本学の授業で使われているのは`pLaTeX`

---

# Homebrew のインストール

`command` + `space`を押して、「terminal」と入力
黒い画面が出てくるので、以下のコマンドを入力

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

（https://brew.sh/ja/ からコピペできる）

---

# スキームについて

## Full スキーム

TexLive のすべての機能をインストール出来るが、容量が 5GB 以上ある。インストールに 30 分以上かかる。
日本語や英語以外の言語もすべて一括でインストールされるので、必要ないものもインストールされる。

## Basic スキーム（推奨）

最低限の機能がインストールされる。容量は 1GB 程度。インストールに 10 分程度かかる。
必要な機能は後から追加でインストール可能。

## その他

他にもいくつかのスキームがある。基本的には Full か Basic を選択することが多い。

---

# TexLive のインストール

## Basic スキームの場合（推奨）

```bash
brew install basictex
```

## Full スキームの場合

```bash
brew install mactex
```

$\LaTeX$のインストールはこれで終わり。

---

# パッケージとは

- $\LaTeX$では、いくつかの機能を「パッケージ」という形で分割している
- 例えば、数式を書くためのパッケージや図を挿入するためのパッケージなどがある
- 標準でインストールされているパッケージもあるが、使いたい機能に応じてパッケージを追加することができる

---

# パッケージ管理ツール `tlmgr`

- $\LaTeX$のパッケージを管理するためのツール
- terminal から使う
- `tlmgr`を使ってパッケージをインストールしたりアップデートしたりすることができる
- `tlmgr`は`TexLive`に含まれている

パッケージのインストール

```bash
sudo tlmgr install <パッケージ名>
```

パッケージの一括アップデート

```bash
sudo tlmgr update --self --all
```

パッケージの削除

```bash
sudo tlmgr remove <パッケージ名>
```

---

# $\LaTeX$の初期設定（Basic スキームのみ）

再度 terminal を開き、tlmgr のアップデートを行う

```bash
sudo tlmgr update --self --all
```

よく使うパッケージをインストールしておく

```bash
tlmgr install collection-langjapanese comment here threeparttable multirow \
physics tcolorbox environ moreverb keystroke titlesec collection-fontsrecommended \
float jknapltx rsfs mathtools booktabs pdfpages pdflscape listings latexindent jsclasses
```

（https://note.com/konekophysics/n/nfc36c925041d からコピペできる）

---

# VS Code の設定

VS Code で`LaTeX`を使うためには、拡張機能をインストールする必要がある

---

# 拡張機能のインストール

VS Code を開いて、左のメニューから「拡張機能」を選択

↓ このアイコン

![](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2601747/681e5b5a-14e4-ca25-1253-4e69f2e42df3.png)

---

# 拡張機能のインストール

「LaTeX Workshop」を拡張機能検索欄から検索し、次のような拡張機能をインストール

![ScreenShot 2023-06-21 at 0.22.21.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2601747/f4de1410-d3cd-e815-9831-52b44a99856b.png)

---

# 拡張機能のインストール

次に，`⌘`キーと`,`キーを同時に押し，Settings 画面を開く
📄 のアイコンをクリック

![ScreenShot 2023-06-21 at 0.27.06.png](https://qiita-image-store.s3.ap-northeast-1.amazonaws.com/0/2601747/1e243671-a91a-6bc0-0ffd-c4b149d20a22.png)

---

# 拡張機能のインストール

以下のサイトに行く
https://note.com/konekophysics/n/nfc36c925041d
下の図のコードをそのままコピー（右上にコピーボタンがある）

<div style="text-align: center;">
  <img src="img/code1.png" width="60%">
</div>

---

# 終了！

これでセットアップは終了です。

$\LaTeX$の動作確認に移ります。

---

# 動作確認

以下のサイトを開く

https://github.com/konekotech/latex_for_beginner

右上の「Code」から「Local」で「Download ZIP」をクリック
（わかる人向け: `git clone`を使っても OK）

<div style="text-align: center;">
  <img src="img/test1.png" width="50%">
</div>

---

# 動作確認

ダウンロードしたファイルを解凍し、VS Code で開く。

`Alt` + `Ctrl` + `b` を押すと、コンパイルが始まる。
画面下にこのチェックマークが表示されたらコンパイル成功。

![](https://assets.st-note.com/img/1647680078475-5f309y3YWm.png)

`Alt` + `Ctrl` + `v` を押すと、PDF を開くことができる。
`tex`ファイルを少しいじりながら、コンパイル結果がきちんと PDF に反映されるか確認してみよう。
