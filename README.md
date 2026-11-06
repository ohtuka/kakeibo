# かんたん家計簿（PWA）

スマホの中だけにデータを保存する家計簿Webアプリです。サーバー側の処理はなく、静的ファイルを置くだけで動きます。

## ファイル構成
- index.html … アプリ本体（HTML/CSS/JavaScriptを1ファイルに収録）
- manifest.webmanifest … ホーム画面に追加したときの名前・アイコン
- sw.js … Service Worker（オフライン動作）
- icons/ … アイコン

## GitHub Pagesで公開する手順
1. GitHubで新しいリポジトリを作る（例：kakeibo、Public）
2. このフォルダの中身をすべてpushする
3. リポジトリの Settings → Pages → Branch を「main / (root)」にして保存
4. 数分後に https://<ユーザー名>.github.io/kakeibo/ で開けます

## 更新するとき
index.html などを直したら、sw.js の先頭の VERSION を変更（v0.1 → v0.2 など）してからpushしてください。
利用者のスマホでは、次にアプリを開いたとき（ネットにつながっていれば）新しい版に切り替わります。
入力済みのデータ（IndexedDB）は更新しても消えません。

## データについて
- 記録は各自の端末のブラウザ内（IndexedDB）にのみ保存され、どこにも送信されません
- 設定タブからJSON（バックアップ用）とCSV（表計算用）で書き出し・読み込みができます
