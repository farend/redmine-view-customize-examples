# 「担当者」ドロップダウンでグループをユーザーより前に表示する

「グループへのチケット割り当てを許可」（「管理」→「設定」→「チケットトラッキング」）をONにすると、チケットの担当者にユーザーだけではなくグループも設定できます。

このカスタマイズでは、担当者のドロップダウンリストボックスでユーザーよりもグループを先に表示するようにします。

動作確認バージョン：Redmine 6.1 / RedMica 3.2

> [!important] 
> ユーザーインターフェイスが日本語の場合に動作します。他の言語で使用されている場合、動作しません。

## 設定

パスのパターン: `/`

挿入位置: チケット入力欄の下

種別: JavaScript

コード:

~~~ javascript
$(function () {
  const $select = $("#issue_assigned_to_id");
  if (!$select.length) return;

  const selectedVal = $select.val();
  const $options = $select.children("option");
  const $optgroups = $select.children("optgroup");

  const $groupOptgroup = $optgroups.filter((_, el) => $(el).attr("label") === "グループ");
  if (!$groupOptgroup.length) return; 

  const $blank = $options.filter((_, el) => el.value === "").first().detach();
  const $myself = $options.filter((_, el) => /自分/.test($(el).text())).first().detach();

  const $otherOptgroups = $optgroups.not($groupOptgroup).detach();

  const $separator = $('<option value="" disabled="disabled">─────</option>');
  $groupOptgroup.detach();

  $select.empty();
  if ($blank) $select.append($blank);
  $select.append($groupOptgroup);
  $select.append($separator);
  if ($myself) $select.append($myself);
  $select.append($otherOptgroups);

  $select.val(selectedVal); 
});
~~~

## カスタマイズ結果

### カスタマイズ前

![](assigned-to-before@2x.png)

### カスタマイズ後

![](assigned-to-after@2x.png)