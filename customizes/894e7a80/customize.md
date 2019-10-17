# 各画面に操作ガイダンスを表示する

Redmineの各画面に、操作方法や画面自体の説明を表示することで、Redmineにまだあまりなじんでいない方が操作に戸惑うのを防ぐことができます。

対応バージョン：Redmine 3.4.11, 4.0.4

## 設定

### 設定1: ガイダンス用スタイルを追加

Path Pattern: `/`<br>
※ `/` は全画面にマッチ

Type: StyleSheet

Code:

``` css
/* ガイダンス用スタイル定義 */
.guidance {
  background-color: #d9edf7;
  border: 1px solid #bce8f1;
  border-radius: 6px;
  color: #31708f;
  padding: 8px;
  margin: 10px 0;
}
```

### 設定2: チケット一覧画面でガイダンスを表示

Path Pattern: `/issues\??.*$`<br>
※ `*/issues` または `*/issues?*` にマッチ (いずれもチケット一覧画面のURL)

Type: JavaScript

Code:

``` javascript
/* チケット一覧画面 ガイダンス表示 */
$(function() {
  $("#content>h2:first-of-type").after(
    "<div class='guidance'>お問い合わせいただいた案件の一覧です。<br>" +
    "各案件の詳細を見るには題名をクリックしてください。" +
    "過去案件を表示するには、 <strong>ステータス</strong> で <strong>すべて</strong> を" +
    "選択してから <strong>適用</strong> をクリックしてください。</div>"
  );
});
```

## カスタマイズ結果

![](guidance-sample@2x.png)

