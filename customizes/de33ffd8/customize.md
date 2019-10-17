# 「プロジェクト」画面から「ガントチャート」「カレンダー」などのメニューを非表示にする

「プロジェクト」画面に表示されている、「ガントチャート」「カレンダー」などのメニューを非表示にします。

対応バージョン：Redmine 3.4.11, 4.0.4

## 設定

Path Pattern: `/projects$`

Type: StyleSheet

Code:

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
