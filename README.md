# how_to_use_jq

jq の使い方

- `jq "." <ファイル>` 全部表示
- `jq "keys" <ファイル>` 辞書のトップカテゴリーを表示
- `jq "type" <ファイル>` トップが辞書かリストか知る (object → 辞書、array → リスト)
- `jq 'path(..) | map(if type == "number" then "[" + tostring + "]" else tostring end) | join("/")' <ファイル>`階層構造を全部表示
- `jq ".キー | type" <ファイル>` キーの要素のタイプを知る。
- `jq "length" <ファイル>` 最上階層の数を調べる (辞書でもリストでも大丈夫)
- `jq -s "." <ndjson ファイル>` ndjson 形式のファイルを json にリストにして繋げて変換する
