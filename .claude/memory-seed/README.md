# memory-seed — AIコーチの背景文脈の種

Claude Code の「自動メモリ」は各PCのホーム配下（`~/.claude/projects/.../memory/`）にあり、GitHub では同期されない。このフォルダはその内容のスナップショット（種）で、**新しいPCでコーチに最初から背景を持たせたいとき**だけ一度コピーして使う。

```sh
# clone 先が ~/Dev/hobby/knowledge の場合
mkdir -p ~/.claude/projects/-Users-$USER-Dev-hobby-knowledge/memory
cp .claude/memory-seed/*.md ~/.claude/projects/-Users-$USER-Dev-hobby-knowledge/memory/
```

- パスは clone 先の絶対パスの `/` を `-` に置き換えたもの。`~/Dev/hobby/knowledge` 以外に置いたら読み替える。
- `README.md`（このファイル）はコピー対象外。`MEMORY.md` と各メモリ本体だけ入れる。
- コピーしなくても `CLAUDE.md` と `progress.md` からコーチは文脈をほぼ復元できる。必須ではない。
- これはスナップショット。母艦PCでメモリが育ったら、たまにここへ反映し直すと種が最新に保たれる。
