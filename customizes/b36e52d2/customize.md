# プロジェクトの概要画面でメンバーを非表示にする

プロジェクトの概要画面にあるメンバーの表示欄を非表示にします。  
※操作している限りメンバーの表示は見えませんが、**HTMLのソースコードには残っています**。

対応バージョン：Redmica 2.2

## 設定

パスのパターン: `/`

挿入位置: 全ページのヘッダ

種別: CSS

コード:

~~~ css
.controller-users.action-show .splitcontentright {
  display: none;
}

.controller-projects.action-show .members.box {
  display: none;
}
~~~

## カスタマイズ結果

### カスタマイズ前

![](overview_before@2x.png)

### カスタマイズ後

![](overview_after@2x.png)
