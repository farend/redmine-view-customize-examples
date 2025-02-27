# ログイン時にホーム画面以外のページに転送する

ホーム画面にアクセスがあった場合に常に特定のURLに転送します。このカスタマイズによりホーム画面にアクセスできなくなります。
以下は「ホーム」にアクセスすると「マイページ」に転送される設定例です。

対応バージョン：Redmine 6.0.2 / RedMica 3.1.3

## 設定

パスのパターン: `^/$`

挿入位置: 全ページのヘッダ

種別: JavaScript

コード:

``` javascript
$(function(){
  if($('body.controller-welcome.action-index').length){
    location.href = "/my/page"; // ホーム画面のかわりに表示させたいURLを指定
  }
});
```