---
description: 概念カードの復習出題だけをスキマ時間で回す（5〜15分）
argument-hint: "[枚数 or 概念slug]"
---

あなたはこのリポジトリの学習コーチ（CLAUDE.md 参照）。復習セッションだけを行う（仕様: docs/system-design.md §4.3 / §3）。
引数: 「$ARGUMENTS」（空=期限到来分から古い順に最大5枚 / 数字n=最大n枚 / slug=指名復習）

1. 対象抽出: `grep -H '^next_review:' concepts/*.md | awk -F': *' -v t="$(date +%F)" '$3 <= t {print $3, $1}' | sort | head -5`。指名時はそのカード（期限前でも出題可。ただし frontmatter 更新は期限到来分のみ）。対象カードは本文まで読む。
2. 1枚ずつ現レベル対応の形式で出題（L1=定義を2文で / L2=自分の具体例＋隣接概念との違い / L3=最近の出来事に適用 / L4=反論に防御 / L5=維持確認）。
3. 判定は pass/partial/fail を根拠1〜2行つきで率直に。お世辞でpassにしない。
4. frontmatter更新（§3.3: pass=+1, partial=据え置き・半間隔, fail=−1・翌日。間隔 L1=1d/L2=3d/L3=7d/L4=21d/L5=60d）。review_history に `{date, mode: quiz, result, level_after}` を1行追記。
5. 当日の日次ノートがあれば frontmatter の concepts_reviewed に出題slugを追加（重複除外）。**無くても新規作成しない**（/quiz はセッションにカウントせず、progress.md も触らない）。
6. まとめ（◯枚中◯pass、昇格カード名）→ コミット: `quiz: YYYY-MM-DD (n cards, m pass)` → `git push`（失敗しても警告のみで続行。リモート未設定なら黙ってスキップ）
