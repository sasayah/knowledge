# knowledge — 哲学を学び、語れるようになるための学習システム

**東浩紀**（思想・批評の深さ）×**中島聡**（エンジニアの一次知識で技術を語る力）を目標像に、毎日30〜45分 × 何年も かけて「哲学のレンズで世界とテクノロジーを語れる」自分を作る。Claude Code が AIコーチとして伴走する。

## 毎日やること

```sh
cd ~/Dev/hobby/knowledge && claude
> /today        # これだけ。30〜45分（疲れた日は /today min で10分）
```

## 週のリズム

| 曜日 | コマンド | 時間 |
|---|---|---|
| 月〜金 | `/today` | 30〜45分 |
| 土 | `/essay`（Week 3 から） | 45〜60分 |
| 日 | `/review week`（月末日曜は `/talk speech` → `/review month`） | 20〜60分 |

スキマ時間に `/quiz`（復習だけ）、気になるニュースがあったら `/news`、議論の練習は `/talk`。

## 地図

- いま何を学ぶか: [curriculum/syllabus.md](curriculum/syllabus.md)（週次）／[curriculum/first-8-weeks.md](curriculum/first-8-weeks.md)
- 数年の全体像: [curriculum/roadmap.md](curriculum/roadmap.md)／書籍リスト: [curriculum/books.md](curriculum/books.md)
- 目的地の思想地図: [curriculum/map.md](curriculum/map.md)（東浩紀の系譜・技術哲学への拡張・実務に効く20レンズ）
- どう続けるか: [method/rules.md](method/rules.md)（運用ルール）／[method/training.md](method/training.md)（語れるようになる訓練法）
- システム仕様: [docs/system-design.md](docs/system-design.md)
- 進捗: [progress.md](progress.md)（自動生成）

## 原則（method/rules.md より）

1. 続くことが最優先。1日の質より1年の継続。
2. 完了条件は「今日の一行」を書いてコミットすること、それだけ。
3. 最小デー（`/today min`・10分）は正規の運用モード。サボりではない。
4. 2日連続で休まない。切れたら10分で戻る。反省文は書かない。
5. ルール変更は四半期レビューでのみ（衝動的な改造を防ぐ）。
