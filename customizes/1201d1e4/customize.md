# チケット一覧で期日が過ぎたチケットの背景色を変更する

期日が過ぎたチケットの背景色を変えて目立つようにするカスタマイズです。

> [!TIP]
> **カスタマイズ不要（テーマの利用）**：[farend_basic](https://github.com/farend/redmine_theme_farend_basic), [farend_fancy](https://github.com/farend/redmine_theme_farend_fancy)などのテーマを利用すると、カスタマイズを追加しなくても、テーマ標準のスタイルにより、期日が過ぎたチケットはオレンジで表示されます。

---

テーマを利用せず、独自の色に変更したい場合は、以下のカスタマイズで対応できます。

動作確認バージョン：Redmine 6.0 / RedMica 3.2

## 設定

パスのパターン: `/issues$`

挿入位置: 全ページのヘッダ

種別: CSS

コード:

``` css
table.list > tbody > tr.overdue:not(:hover) { background-color: pink; }
```

background-colorは任意の色に変更ください。

## カスタマイズ結果

### カスタマイズ前

![](before@2x.png)

### カスタマイズ後

![](after@2x.png)

