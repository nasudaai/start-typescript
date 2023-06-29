# start typescript

typescriptを始める。
まずは、typescriptをインストールする。

`npm install --save-dev typescript`

公式サイトのガイドに従って、適当なコードを書く。わざと間違えたりする。

コンパイルして、errorを出してもらう。

## tscの実行

兎も角、コンパイルしてもらわないといけない。

しかし、typescriptのインストールはグローバルにしていない。そのため、pathは通っていない。

手段は２つ。多分２つ。

`npx` コマンドを使う。

`npx tsc [filename].ts`

もしくは、node_modules内の`tsc` コマンドのpathを指定して`npm run `する。

結局同じことなのらしいのだが。

一旦、最も簡単な選択肢を選ぶ。

`npx tsc [filename].ts`。

はい。

一応、もう一つの手段を実行する。今回は、`package.json`に、`npm scripts` として登録して実効する。

```
  ~~~
  
  "scripts": {
    ~~,
    "tsc": "./node_modules/typescript/bin/tsc"
  },
  
  ~~~
```

なんとも不毛である。

## 型指定を間違えてみる

`const a: string` と型を指定しておきながら、

`const a: string = 3;` とかしてみる。

そして、`npm run tsc` とかすると、しっかりerrorを出してくれる。

//** すべて、ターミナル上で行っている。 **//

*typescriptを書いてみる*  という目標ならこれで実現できた。

しかし、開発のための**typescript** なのだから、やはり環境構築をもう少し頑張る必要はある。

しかし、typescriptを書くという目的自体は達成した。

そして、やはり、`npx tsc ~~~` とするのが良い。

## ネクスト...