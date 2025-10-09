# リンクを別タブで表示する(Textile)

Textileでは、次のように記述してリンクを表示させることができます。
~~~
"Redmine.JP":http://redmine.jp/
~~~
作成したリンクはクリックすると別タブで表示されません。これを別タブで表示させます。

動作確認バージョン：Redmine 6.0 / RedMica 3.2

## 設定

パスのパターン: `.*`

挿入位置: 全ページのヘッダ

種別: JavaScript

コード:

~~~ javascript
/* リンクを別タブで表示する(Textile) */
$(function() {
  $("a.external").attr("target","_blank");
});
~~~
