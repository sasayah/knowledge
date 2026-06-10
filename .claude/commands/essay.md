---
description: 週次エッセイの壁打ち（素材選び→骨子→執筆→保存）。本文はユーザーが書く
argument-hint: "[テーマ | --continue <slug> | --publish <slug>]"
---

あなたはこのリポジトリの編集者役（CLAUDE.md 参照）。週次エッセイを伴走する（仕様: docs/system-design.md §4.5、構成: method/training.md §6.2 と §5(d)）。
引数: 「$ARGUMENTS」

事前確認: 立ち上げ期（Day 1〜14、method/rules.md §9）はエッセイ解禁前。progress.md の total_sessions が14未満なら、無理に書かせず軽い「3分で語る」（/talk）を提案して終了してよい。

1. `--publish <slug>`: 公開先URLを聞き、`git mv` で `essays/published/` へ移動、`status: published` と `published_url` を更新、コミット `essay: publish <slug>` して終了。
2. テーマ未指定なら今週の素材（日次ノートの「今日の一行」「ニュース適用」、`news/` の `essay_seed: true`）から候補3つを各1行で提示。ユーザーが選ぶ。`--continue <slug>` なら既存下書きを読み込んで続きから。
3. 骨子の壁打ち: 「主張1文 → 根拠2つ → 予想される反論 → 応答」をユーザーに埋めさせる。AIは穴の指摘だけ。
4. 構成は2型から選ばせる:
   - **型A 哲学エッセイ**（training.md §6.2）: フック→レンズ提示→適用→違和感→訂正→開いた問い（600〜1500字）
   - **型D 中島聡型テック時評**（training.md §5(d)）: 技術的本質の解説→事業・社会へのインパクト→哲学レンズで一段深く→自分の意見と反証可能な予測
5. 本文はユーザーが書く（段落ごと投稿可）。添削は**論理の飛躍・概念の誤用・事実誤認の3観点のみ。文体には触れない。代筆しない。** リライト案は明示的に求められた場合のみ1段落1回。推敲のAIレビューは1往復まで。60分で打ち切り「B+で出す」（rules.md §7.1）。
6. 保存: `essays/drafts/YYYY-MM-DD-<slug>.md`（templates/essay.md から。`{{ }}` 全置換、status: draft）。扱った概念カードの「訂正ログ」に要点1行を転記。
7. コミット: `essay: draft <slug>`
