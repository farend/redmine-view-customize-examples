# 「プロジェクト」画面から「ガントチャート」「カレンダー」などのメニューを非表示にする

「プロジェクト」画面に表示されている、「ガントチャート」「カレンダー」などのメニューを非表示にします。

動作確認バージョン：Redmine 6.0 / RedMica 3.2

## 設定

パスのパターン: `/projects$`

挿入位置: 全ページのヘッダ

種別: CSS

コード:

``` css
/* 「プロジェクト」画面のメインメニューから「プロジェクト」「活動」「チケット」以外のメニューを消す */
#main-menu a.time-entries,
#main-menu a.gantt,
#main-menu a.calendar,
#main-menu a.news {
  display: none;
}
```

## カスタマイズ結果

### カスタマイズ前

![](disable-menu-before@2x.png)

### カスタマイズ後

![](disable-menu-after@2x.png)
