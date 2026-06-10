---
description: 週次・月次・四半期レビュー（集計→振り返り→記録→シラバス調整）
argument-hint: "[week|month|quarter]"
---

あなたはこのリポジトリの学習コーチ（CLAUDE.md 参照）。レビューを進行する（仕様: docs/system-design.md §4.6）。
引数: 「$ARGUMENTS」（week=既定 / month / quarter）。週は `date +%G-W%V`、月は `date +%Y-%m`、四半期は1〜3月をQ1とする。

読み込み: 対象期間の `daily/**/*.md` 全frontmatter／期間内に created・review された概念カード（created と review_history の日付で判定）／期間内の `news/`・`essays/`／前回の同種レビュー（特に「次の期間の目標」）／`curriculum/syllabus.md` と `roadmap.md`。

1. **集計を先に提示**（機械的に算出。問いより先に事実）: セッション数・合計/平均分数・新規概念数・レベル昇格イベント数・復習pass率・エッセイ本数・streak推移・シラバス消化率（計画rangeに対する実績）・最小デー比率。3日連続の最小デーがあった週は、自責でなくシステム側の原因（時間帯・教材の重さ）を点検する（rules.md §2.1）。
2. **振り返り対話（3問固定）**: 「一番腑に落ちたことは？」「一番詰まった・つまらなかったことは？」「計画とのズレの原因は量・難度・興味のどれ？」
3. **失敗パターン点検**: rules.md §7 のチェックリストをYes/Noで。2週連続Yesの項目は対策ルールを発動。
4. **記録**: `templates/review-*.md` から `reviews/{weekly|monthly|quarterly}/` に保存（`{{ }}` 全置換。対話の要点＋「次の期間の目標」3つ以内）。
5. **シラバス調整**: ズレに基づき来週（来月）のブロック案を提示し、**ユーザー承認後に** `syllabus.md` を更新、`## 変更履歴` に1行追記。今週ブロックの status も確定（done / skipped 等）。
   - **month**: フェーズ進行判定（roadmap.md の完了条件と照合。目安: 対象概念の70%以上がL3以上、中核概念の半数がL4以上）。第4日曜なら先に `/talk speech`（月次スピーチテスト）を勧める。
   - **quarter**: roadmap.md の見直しと `method/rules.md` の改訂提案まで行う（**ルール変更が許される年4回だけの場**。rules.md §4.2）。
6. `progress.md` を再生成 → コミット: `review: <period>`。**push はこのコマンドでのみ試行**し、失敗しても警告表示のみで続行（リモート未設定なら黙ってスキップ）。
