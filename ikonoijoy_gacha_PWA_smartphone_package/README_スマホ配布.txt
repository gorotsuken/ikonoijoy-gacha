イコノイジョイ ガチャ PWA版
=============================

このフォルダ一式をHTTPS対応の静的Webサイトへ配置すると、
スマホでURLを開いてガチャ・動画演出を利用できます。

【フォルダ構成】
index.html
manifest.webmanifest
service-worker.js
icons/
assets/

重要:
- index.html だけをアップロードしないでください。
- assets / icons / manifest.webmanifest / service-worker.js も同じ構成のままアップロードしてください。
- PWAとして使うには基本的に HTTPS が必要です（PCのlocalhostは例外）。
- 「絶対アイドル辞めないで」がLRで出た場合、専用ライブカットインが自動で入ります。
- 音声はチケットをタップした操作を起点に再生する実装です。スマホの消音モードや音量も確認してください。

【いちばん簡単な公開手順の例: GitHub Pages】
1. GitHubで新しいリポジトリを作成します。
2. このZIPを展開し、「中身」を全部リポジトリのルートへアップロードします。
   ※ ZIPファイルそのものを置くのではありません。
3. GitHubのリポジトリで Settings → Pages を開きます。
4. Branch を main、Folder を /(root) にして公開します。
5. 表示された https://...github.io/.../ のURLをスマホで開きます。

【iPhoneでアプリ風に使う】
1. Safariで公開URLを開きます。
2. 共有ボタンを押します。
3. 「ホーム画面に追加」を選びます。
4. ホーム画面の「イコノイガチャ」から起動します。

【Androidでアプリ風に使う】
1. Chromeで公開URLを開きます。
2. Chromeのメニューから「アプリをインストール」または「ホーム画面に追加」を選びます。
3. ホーム画面から起動します。

【更新するとき】
index.html や assets を差し替えて再公開してください。
service-worker.js の CACHE 名（現在 ikonoijoy-gacha-pwa-v1）を v2, v3... と変更すると、
既存ユーザーにも新しいローカル素材をより確実に更新できます。

【YouTube APIについて】
YouTube APIキーや再生リスト設定は、今までどおり各端末のブラウザ/localStorage側に保存されます。
静的サイトへ公開しただけでは管理者が更新したMVデータが全ユーザーへ自動共有されるわけではありません。
全ユーザー共通のMVランキングを配布したい場合は、次の段階でサーバー側保存を追加する必要があります。
