# プロジェクトを横断した自分が担当者の未完了チケット一覧へのリンクを表示する  

プロジェクトを横断して自分が担当者のチケットを確認するには、最上部のアプリケーションメニュー内の「プロジェクト」をクリックした後、「チケット」をクリックしてさらに自分が担当者であるチケットを絞り込んで表示する必要があります。  
これをアプリケーションメニュー内に自分が担当者の未完了チケット一覧へのリンクを追加して、ワンクリックで表示できます。

動作確認バージョン：Redmine 6.0 / RedMica 3.2

## 設定

パスのパターン: `.*`

挿入位置: 全ページのヘッダ

種別: JavaScript

コード:

``` javascript
$(function() {
  $('#top-menu>ul')
    .append('<li><a href="/issues?set_filter=1&sort=id%3Adesc&f[]=status_id&op[status_id]=o&f[]=assigned_to_id&op[assigned_to_id]=%3D&v[assigned_to_id][]=me&f[]=&c[]=project&c[]=tracker&c[]=status&c[]=priority&c[]=subject&c[]=assigned_to&c[]=updated_on&group_by=&t[]=">自分の未完了</a></li>');
})();
```

## カスタマイズ結果

![](image.png)

