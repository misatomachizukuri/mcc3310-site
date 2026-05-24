# 美里まちづくり公社 公式サイト静的化案

WordPressから、静的サイト + CMS管理のお知らせへ移行するための初期構成です。

## 構成

- `index.html`: 公式サイトトップ
- `news.html`: お知らせ一覧
- `content/news/news.json`: CMSで編集するお知らせデータ
- `admin/`: Decap CMS管理画面
- `assets/css/styles.css`: デザイン
- `assets/js/news.js`: お知らせ表示

## 公開先の想定

Cloudflare Pagesを推奨します。

1. GitHubにこのサイト用リポジトリを作成
2. `admin/config.yml` の `repo` を実際のリポジトリ名に変更
3. Cloudflare PagesでGitHubリポジトリを接続
4. ビルドコマンドなし、公開ディレクトリ `/` で配信
5. `mcc3310.com` のDNSをCloudflare Pagesへ向ける

## Cloudflare Pages設定

- Project name: `mcc3310-site`
- Build command: 空欄
- Build output directory: `/`
- Production branch: `main`
- Pages URL: `https://mcc3310-site.pages.dev`

Cloudflare Pagesのプロジェクトは作成済みです。GitHubリポジトリを接続すると、`main` ブランチへの更新で自動公開されます。

## CMS運用

`/admin/` にアクセスしてお知らせを編集します。

本番ではDecap CMSのGitHub認証設定が必要です。Cloudflare Pagesで運用する場合は、GitHub OAuth AppまたはDecap CMS向けの認証サービスを設定します。

## GitHub側で必要なもの

- リポジトリ名: `mcc3310-site` 推奨
- 公開範囲: public または private
- ブランチ: `main`
- CMS編集者には、リポジトリへの書き込み権限を付与

## ローカル確認

静的ファイルだけで構成しています。ローカル確認は簡易サーバーを立ち上げてブラウザで確認します。
