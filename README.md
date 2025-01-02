# Tailwind CSSまとめ
## 導入 
1. `npm init -y`を実行する<br>➡`package.json`が生成される。
1. 以下公式の手順に従い、インストール・および初期設定[^1]
   1. コマンド実行
      ```bash
      npm install -D tailwindcss
      npx tailwindcss init
      ```
      ➡`tailwind.config.js`が生成される。
   1. `tailwind.config.js`を編集する。
      - contentを入力し、対象ファイルを指定する。
   1.  `postcss.config.js`を作成し、必要な内容を記載
   1. WEBページで使用するメインのcssにディレクティブを記入する
      ```css
      /* ./src/input.css内 */
      @tailwind base;
      @tailwind components;
      @tailwind utilities;
      ```
    1. `build`を実行する[^2]
        > `npx tailwindcss -i ./path/to/input.css -o ./path/to/output.css`でビルドを行う。<br>ホットリロードをする際は末尾に`--watch`オプションをつける。<br>
        > 本リポジトリでは下記のように`package.json`に追加しした。input/outputのパスは環境に合わせること。
        > ```json
        >  "scripts": {
        >    "dev": "npx tailwindcss -i ./src/input.css -o ./src/css/output.css --watch",
        >    "build": "npx tailwindcss -i ./src/input.css -o ./src/css/output.css "
        >   },
        > ```
        > これで開発中は`npm run dev`、リリース時に`npm run build`として使用することができる。
   1. html側では`output.css`を参照するように`linkタグ`を記載する。

[^1]:[Tailwind CLI(公式)](https://tailwindcss.com/docs/installation)
[^2]:[【入門】Tailwind.cssで学んだことをまとてみた【使い方】](https://jito-site.com/tailwind-css-use/)