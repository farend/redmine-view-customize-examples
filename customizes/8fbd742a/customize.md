# カスタムクエリが反映されたプロジェクト一覧画面を表示する

> [!TIP]  
> Redmineの標準機能でプロジェクト一覧画面にカスタムクエリの適用が可能です。以下の2つの操作を行うことで、View Customize によるカスタマイズは不要です。
>
> **①プロジェクトクエリの保存**  
> Redmine 4.1から、プロジェクト一覧画面にフィルタとオプションが追加され、設定した表示条件をカスタムクエリとして保存できるようになりました。  
> 詳細:[http://blog.redmine.jp/articles/4_1/new-features-p3/#29482](http://blog.redmine.jp/articles/4_1/new-features-p3/#29482)
> 
> **②デフォルトのプロジェクトクエリ設定**  
> Redmine 5.0からは、デフォルトのプロジェクトクエリを設定できるようになりました。①で保存したクエリを、デフォルトのプロジェクトクエリとして設定します。  
> 設定後はプロジェクト一覧ページを開いた際に、あらかじめ設定したクエリが自動的に適用されます。  
> 詳細:[https://blog.redmine.jp/articles/5_0/new-features/#35795](https://blog.redmine.jp/articles/5_0/new-features/#35795)

画面上部のメニューに表示されるプロジェクト一覧へのリンク先を、カスタムクエリを適用したプロジェクト一覧のURLに設定して表示します。

対応バージョン: Redmine 4.1.0

## 設定

パスのパターン: `.*`

挿入位置: 全ページのヘッダ

種別: JavaScript

コード:

``` javascript
$(function(){
  $('div#top-menu a.projects').attr('href', '/projects?query_id=****');
});
```

「****」は表示したいカスタムクエリのIDに書き換えてください。IDはカスタムクエリを表示したURLから調べることができます。  

## カスタマイズ結果

![](projects_after@2x.png)


