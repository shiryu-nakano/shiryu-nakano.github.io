<%*
const editor = app.workspace.activeEditor?.editor;
if (!editor) return;

const cursor = editor.getCursor();
const line = editor.getLine(cursor.line);

// パターン1: - [ ] テキスト → チェックする
const unchecked = line.match(/^(\s*[-*+]\s+)\[ \]\s+(.+)$/);
if (unchecked) {
  const [, prefix, text] = unchecked;
  const ts = window.moment().format("YYYY-MM-DD HH:mm");
  editor.setLine(cursor.line, `${prefix}[X] ~~*${text}*~~ [${ts}]`);
  return;
}

// パターン2: - [X] ~~*テキスト*~~ [日時] → アンチェックして元に戻す
const checked = line.match(/^(\s*[-*+]\s+)\[[Xx]\]\s+~~\*(.+?)\*~~\s*\[\d{4}-\d{2}-\d{2} \d{2}:\d{2}\]\s*$/);
if (checked) {
  const [, prefix, text] = checked;
  editor.setLine(cursor.line, `${prefix}[ ] ${text}`);
  return;
}

// パターン3: 普通の - [X] あああ もアンチェックできるように（保険）
const plainChecked = line.match(/^(\s*[-*+]\s+)\[[Xx]\]\s+(.+)$/);
if (plainChecked) {
  const [, prefix, text] = plainChecked;
  editor.setLine(cursor.line, `${prefix}[ ] ${text}`);
}
-%>