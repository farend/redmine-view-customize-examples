# リンクを別ウィンドウで表示する(Textile)

Textileでは、次のように記述してリンクを表示させることができます。
~~~
"Redmine.JP":http://redmine.jp/
~~~
作成したリンクはクリックすると別ウィンドウで表示されません。これを別ウィンドウで表示させます。

対応バージョン：Redmine 3.4.11, 4.0.4

## 設定

Path pattern: `.*`

Type: JavaScript

Code:

~~~ javascript
/* リンクを別ウィンドウで表示する(Textile) */
$(function() {
  $("a.external").attr("target","_blank");
});
~~~
