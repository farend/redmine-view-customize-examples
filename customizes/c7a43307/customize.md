# チケット作成・編集画面で優先度の項目を減らす

Redmine全体で設定されているトラッカーの優先度の項目を任意に消して表示します。

動作確認バージョン：Redmine 6.1 / RedMica 4.0

## 設定

パスのパターン: `/issues/`

プロジェクトのパターン: 設定したいプロジェクトを指定します

挿入位置: 全ページのヘッダ

種別: JavaScript

コード:


``` javascript
(function($) {
  function removeSpecificPriorities() {
    // 消したい優先度名を指定（例として「低め」と「今すぐ」）
    const targetPriorities = ["低め", "今すぐ"]; 

    $("#issue_priority_id option").each(function() {
      const text = $(this).text().trim();
      if (targetPriorities.includes(text)) {
        $(this).remove();
      }
    });
  }

  // 初回読み込み時
  $(function() {
    removeSpecificPriorities();
  });

  // トラッカー変更などのAjax時
  $(document).ajaxComplete(function(event, xhr, settings) {
    if (settings.url.indexOf('issues') !== -1) {
      removeSpecificPriorities();
    }
  });

})(jQuery);

```

**※Redmineの設定に合わせてコード内にある次の値を変更してカスタマイズを作成してください。**

* targetPrioritiesの値  
「targetPriorities」の"低め", "今すぐ"は消したい優先度の項目に合わせて変えてください。  
