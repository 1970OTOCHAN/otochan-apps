# シンプルで簡単　役立つアプリ集（アプリ紹介ホームページ）

1970 OTOCHAN が作ったアプリを紹介するホームページ。Xの固定ポストからリンクする。

- GitHub Pages: https://1970otochan.github.io/otochan-apps/ （main に push すると自動で公開）
- 呼び方は「おとちゃん」ではなく「おとーちゃん」。説明は日本語で、画面の写真を見ながら1手順ずつ

公開用のファイル：index.html, manifest.webmanifest, sw.js, icon-192.png, icon-512.png, apple-touch-icon.png, ogp.png, fonts/ZenMaruGothic-Medium-sub.woff, fonts/ZenMaruGothic-Bold-sub.woff

## 変更するときのルール（必ず守る）

- 変更する前に、チャットで「このように変更します。よろしいですか」と聞く。見た目の変更は先にサンプル画像を見せる
- ユーザーにバージョン番号を聞かない。変更のたびに自動で上げる
  - 小さな直し（文字・色・配置・文言・アプリの追加・不具合修正）: Ver.1.0 → Ver.1.1
  - 大きな作り直し: Ver.1.5 → Ver.2.0
- バージョンを上げるときは、次の2か所を同じ番号にそろえる
  1. `index.html` のいちばん下 `<span class="ver">Ver.X.Y</span>`
  2. `sw.js` の `const CACHE="otochan-apps-verX.Y";`
- コミットメッセージは日本語で「Ver.X.Y: 変更内容」
- 書体は Zen Maru Gothic を、ページで使う文字だけに切り出して fonts/ に入れてある（ひらがな・カタカナ・英数字はすべて入っている）。新しい漢字を使う文言を足したら、元のTTF（ユーザーの引き継ぎZIPの 素材/書体）から pyftsubset で切り出し直す。入っていない文字は端末の丸ゴシック等で表示される

## 仕様メモ（Ver.1.0、2026-11-25）

- 題名「シンプルで簡単　役立つアプリ集」、副題「ツーリング・サイクリング・旅行・登山etc…　貴方の暮らしをサポートします」。題名に「おとーちゃん」は出さない
- 見た目：地図の紙（方眼）の背景、青い川、黄色いルート、ピン3つ＋黄色い丸の「無料」スタンプ（文字は赤 #d62828）
  - スマホ：題名2行、「無料」は右上
  - パソコン（760px以上）：題名1行で大きく、左から少し右に寄せ、「無料」は題名のすぐ右（少し離す）。ピンとルートは文字に重ならないよう少し下げてある
- 1ページで、スマホは1列、パソコンは自動で並ぶカード（最小350px、最大幅1800px）
- グループと順番
  1. 旅の計画・ルート動画：Route Animator Enkel™ ／ ツーリング行程表メーカー
  2. 走る・歩くときに：Moto Meter Samlet™ ／ 勾配メーター ／ 1970otochan™clock ／ 1970otochan™clock ALT
  3. 空と山を見る：Hinode Hunter!!™ ／ 富士山スコープ™ ／ やまスコープ™
  4. 巡る・訪ねる：名城マップ ／ 寺巡礼マップ ／ 五街道宿場町巡礼マップ
- 各カード右側におすすめ環境のチップ（Enkel=パソコン／行程表・clock・3つのマップ=パソコン+スマホ／ほか=スマホ）。冒頭に「パソコンはWindows 11で動作確認しています。」
- ™は Enkel、Samlet、clock、clock ALT、Hinode Hunter!!、富士山スコープ、やまスコープ のみ
- 英語名のアプリだけ、語ごとに真上にフリガナ（ALT＝オルト）。日本語名には付けない
- 説明文は1行。各カード右下に48pxの角丸アイコン（画像はindex.htmlに埋め込み）
- Enkel はスマホ・タブレットでは押せない（端末判定で「パソコンで開いてください」と表示）
- ホーム画面に追加できる（manifest・アイコンは案B：緑地にアプリが並んだ絵＋「アプリ集」）。名前「役立つアプリ集」
- 開くたびに最新版を確かめる：sw.js は cache:no-cache で取りに行き、updateViaCache:'none'。新しい版に切り替わったら1回だけ自動で読み込み直す（スクロール位置は戻す）
- Xカード用の画像 ogp.png（1200×630）、OGP/Twitterカードのタグあり
- アクセス数の計測：Cloudflare Web Analytics（ほかのアプリと同じ計測コード）を index.html の最後に入れた。sw.js はほかのサイトへの通信を保存しない
- 下に利用条件・免責の文と「© 2026 1970 OTOCHAN. All rights reserved.」

## アプリのアドレス

- Enkel https://1970otochan-route-animator-enkel.netlify.app
- 行程表 https://1970otochan-touring-koteihyo-maker.netlify.app
- Samlet https://1970otochan.github.io/moto-samlet/
- 勾配メーター https://1970otochan.github.io/koubai-meter/
- clock https://1970otochan.github.io/otochan-clock/
- clock ALT https://1970otochan.github.io/otochan-clock-alt/
- Hinode Hunter!! https://1970otochan.github.io/hinode-hunter/
- 富士山スコープ https://1970otochan.github.io/fuji-finder/
- やまスコープ https://1970otochan.github.io/kono-yama-naani/
- 名城マップ https://1970otochan.github.io/meijo100-map/ （続編 zoku.html）
- 寺巡礼マップ https://1970otochan.github.io/junrei-map/
- 五街道宿場町巡礼マップ https://1970otochan.github.io/shukuba-map/
