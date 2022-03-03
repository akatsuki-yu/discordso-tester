# Discorddso-tester
![discorddso-tester](https://user-images.githubusercontent.com/44968693/156472286-79d3d548-7478-480d-999c-4e4a5e0b8651.png)

## このプロジェクトのデータについて
**[Discord Streamkit Overlay](https://streamkit.discord.com/overlay)** のテスト用HTMLやカスタム用cssのファイル群です。  
私自身がカスタムcssを書く時に、いちいちボイスチャットに入って確かめたりしなければならず、不便だなぁと思っていたことと、デフォルトのcssに何が書いてあるか調べるために、このファイル群を作成しました。  

__[https://albalunaweb.net/note/10296.html](https://albalunaweb.net/note/10296.html)__  
こちらはGitHubにアップする前にデータを配布していた記事です。  
引き続きこのページでも使い方を解説しています。  
内容はこのreadme.mdとほぼ同じこと＋αが書いてあります。

### HTML・cssファイルについて
HTML：Discord Streamkit Overlay（本家）のURLで発行されるソースをそのままコピーし、ソースを読みやすく整理したものです。タグなどは基本的にいじらず、そのままです。  
css：本家が読み込んでいるものをダウンロードし、同じく改行やインデントを入れて読みやすくしたものです。  
⇒[謝辞](#謝辞)

## テスト用HTMLの使い方
### 配信画面へ取り込んで確認する
- [OBS（Open Broadcaster Software）](https://obsproject.com/ja) や [SLOBS（Streamlabs OBS、Streamlabs Desktop）](https://streamlabs.com/)のソースを追加（＋ボタン）から、「__ブラウザソース__」を選択
- 「__新しいソースを追加__」を選択し、適当な名前を付ける
- 「__ブラウザソースの設定__」画面の「URL」に以下のURLをコピペ  
	`https://akatsuki-yu.github.io/discordso-tester/`
- 幅と高さは、配信画面のサイズや使用したいcssに応じて適宜変更。基本的に**幅1920、高さ1080**でいいと思います。
- 「カスタムcss」欄に、使いたいcssをコピペする。

### ブラウザで表示して確認する
このプロジェクトのファイルをローカル保存し、index.htmlをブラウザで表示してください。  
保存はファイル一覧が表示されている箇所の右上、緑色の「__Code__」ボタンを押し、「__Download ZIP__」をクリックすると、プロジェクト内のデータがまとめてダウンロード出来ます。

自作cssを読み込んで使う場合は、index.html内に読み込みタグを追加してください。  
__例）index.htmlと同階層にcustom.cssを置いた場合__  
`<link rel="stylesheet" href="./custom.css">`

なお、SLOBSでの表示は概ね[Google Chrome](https://www.google.com/intl/ja_jp/chrome/)と一致するようです。  
FireFoxでの表示とはズレがありました。（特にpx単位で調整する場合など）

### 表示する人数を変更する
配信画面へ取り込む場合もブラウザで表示する場合も共通です。  
URLの後ろに`?u=(数字)`を追加すると、人数が変わります。  
__例）15人表示したい場合__  
`https://akatsuki-yu.github.io/discordso-tester/?u=15`

デフォルトでは10人表示するようになっています。  
**最小は1、最大は20**です。それ以外の数値や数値以外を入力すると、10人で表示されるようになっています。  
表示が遅くなるおそれがあるので人数制限をかけています。  
（コラボ配信でも20人分あれば足りると思ったので）

### 現在判明している不具合
HTMLもcssも同じはずなのに、何故かアイコンの表示開始位置が本家と異なっているようです。  
margin:16px分上に表示されている？　原因が不明だがとりあえずそのまま。

## カスタムcssについて
このプロジェクト内に上げているカスタムcssは、Discord Streamkit Overlayに適用して使用することが出来ます。  
個別に使い方やカスタム方法を記載すると長くなるので、サイトに掲載しています。  
特に一部cssはカスタム必須であるため、取説を読んでからお使い下さい。  
__[https://albalunaweb.net/assets/stream](https://albalunaweb.net/stream)__

### 自分でカスタムcssを作る時
__css/custom_base.css__ をコピーしてお使い下さい。  
このファイルには、デフォルトcssの内容に加えて、html部分にベタ入力されているstyleの内容もメモしてあります。  
不要なソースは削除してください。

### デフォルトのcssについて
HTMLが読み込んでいるcssは __overlay/df54f6f003d712eb9bf4.css__ です。  
このデータはDiscord Streamkit Overlayが読み込んでいるcssファイルをダウンロードしたものです。
Discord Streamkitのサーバーから直接読み込むことも試みましたが、読み込むファイル名が変わることがある（もとのファイル名は削除される）ようなので、確実にcssを適用するためにダウンロードしたものを使用しています。

## 謝辞
一部cssでお借りしているデータについては、cssの取説ページに記載し、このページでは省略しています。  
__[https://albalunaweb.net/assets/stream](https://albalunaweb.net/stream)__

### Discord Streamkit Overlay
index.htmlとdefault.cssはDiscord Streamkit Overlayのボイスチャット用URLで生成されるHTML、およびその中で読み込まれているcssを抜き出し・整形したものです。  
**[Discord Streamkit Overlay](https://streamkit.discord.com/overlay)**

### ユーザーアイコン
商用利用無料、再配布可能なフリーアイコン「Default Icon」を色変更して使用しています。  
ライセンスはCC3.0です。  
**[http://www.defaulticon.com/](http://www.defaulticon.com/)**

## その他
### 使用許諾条件
本プロジェクト内のデータはThe MIT Licenseに準じてお使い下さい。
[The MIT License原文](https://opensource.org/licenses/mit-license.php)  
参考：[たくさんあるオープンソースライセンスのそれぞれの特徴のまとめ | コリス](https://coliss.com/articles/build-websites/operation/work/choose-a-license-by-github.html)

### 著作権表示
HTMLソース、およびHTMLが読み込んでいるデフォルトのcss  
__Copylight Discord Inc.__

カスタムcss  
__Copylight 2021-2022 Yu Akatsuki.__