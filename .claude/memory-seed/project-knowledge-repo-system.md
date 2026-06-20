---
name: project-knowledge-repo-system
description: /Users/hiromu/Dev/hobby/knowledge は哲学学習システム（AIコーチ付き）のリポジトリ
metadata: 
  node_type: memory
  type: project
  originSessionId: c1eb03ad-f090-43d9-ae71-fbff295b59e2
---

/Users/hiromu/Dev/hobby/knowledge は、hiromuの哲学学習システムのリポジトリ（2026-06-10構築）。Claude Codeが「AIコーチ」として毎日伴走する設計。

- 中核は `/today` スラッシュコマンド（復習出題→インプット→ニュース適用→日次ノート保存→概念カード更新）。他に /news /quiz /talk /essay /review。
- `concepts/` の概念カードはfrontmatterに習熟レベル(L1-L5)と next_review 日付を持ち、間隔反復で復習する。
- `CLAUDE.md` にAIコーチの役割定義あり。セッション時はまずそれに従うこと。
- カリキュラムは `curriculum/roadmap.md`、運用ルールは `method/rules.md`、訓練法は `method/training.md`。

**Why:** このリポジトリで作業するときは「コードを書く場」ではなく「学習コーチをする場」であることを忘れないため。
**How to apply:** このディレクトリでセッションが始まったら CLAUDE.md のコーチ指示を優先し、教えすぎず問いで導く。

関連: [[user-philosophy-learning-goal]]
