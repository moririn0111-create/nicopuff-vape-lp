# tools/sales-sheet.html — VAPE MAFIA 売上台帳

Claude Artifact として公開している売上・経費管理シートのソースです。
LP（`index.html`）からはリンクしていません。売上や領収書は非公開データのため、
GitHub Pages では配信せず、Artifact 側（サインインした本人だけが開けるページ）で運用します。

## できること
- 月ごとの売上／原価／手数料等／経費／営業利益の集計と前月比、月次推移・日別グラフ
- Stripe・WooCommerce の CSV 取り込み（列の自動判定、完了ステータスだけを抽出、重複除外）
- 経費の記録（スマホのカメラでレシート撮影 → 自動圧縮して保存）
- CSV／JSON の書き出しと復元

## データの持ち方
Artifact の `db` capability（`sales` / `expenses` / `settings` コレクション）に保存します。
`db` が使えない環境では localStorage にフォールバックし、同じ画面がそのまま動きます。

## 更新方法
このファイルを編集し、同じパスで Artifact を再公開すると同じ URL が更新されます。
先頭に `<!doctype>` / `<html>` / `<head>` / `<body>` を書かないこと（公開時に付与されます）。
