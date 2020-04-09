# ヘッダの背景色を変更する

複数のRedmineを運用しているとき、それぞれのヘッダの色を別のものに変更して識別しやすくすれば、各Redmineの取り違えやそれによる誤操作を防ぐことができます。

対応バージョン：Redmine 3.4.11, 4.0.4, 4.1.0

## 設定

パスのパターン: `/`

挿入位置: 全ページのヘッダ

種別: CSS

コード:

``` css
/* ヘッダの背景色を変更する */

/* ヘッダの背景色 */
#header {
  background: #59b36b;
}
/* +ボタンとホバーしているタブの背景色 */
#main-menu li a.new-object, #main-menu li a:hover {
  background: #8fcc9b;
}
```

## カスタマイズ結果

### カスタマイズ前

![](change-header-color-before@2x.png)

### カスタマイズ後

![](change-header-color-after@2x.png)

