# テーマ「こどもれっどまいん」を使用中に完了チケットの右下で表示される Great Job を非表示にする

対応バージョン: RedMica 3.1

## 設定

パスのパターン: `/issues/[0-9]+`

挿入位置: チケット詳細の下

種別: CSS

コード:

``` css
.ribbon-content {
  display: none;
}
```

## カスタマイズ結果

### カスタマイズ前

![](before@2x.png)


### カスタマイズ後

![](after@2x.png)
