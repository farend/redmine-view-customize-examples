# チケットの「履歴」「プロパティ更新履歴」に表示されるチケットの値の更新履歴を非表示にする

「履歴」「プロパティ更新履歴」に表示されるチケットの値の変更履歴を非表示にします。

対応バージョン：RedMica3.0.4


## 設定

パスのパターン: `/issues/[0-9]+`

挿入位置: チケット入力欄の下

種別: JavaScript

コード:
``` javascript
$(function(){
  $('div[id^="change-"]').each(function(){
    if ($(this).hasClass('has-notes')){
      $('ul.details').remove();
    }else{
      $(this).remove();
    }
  });
});
```

コメント: 「履歴」「プロパティ更新履歴」に表示されるチケットの値の変更履歴を非表示にする