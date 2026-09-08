# 意思決定ログ

各判断は「何を選んだか」ではなく「なぜ選んだか」を書く。

## 2026-09-08: ルール強制の方式(CLAUDE.md のみ / ハーネスhooks)

**決定:** 5日間の開発インターンという短い期間・少人数の前提では、
Claude Code の hooks/settings.json による物理的な強制は導入せず、
CLAUDE.md による運用ルールのみで進める。

**理由:**
- hooksを設計・検証するコストが、5日間の開発期間に対して見合わない
- CLAUDE.mdが効くのはClaude Code経由の操作のみ。人間が直接 `git push` する
  ケースを塞ぎたいなら、効くのはClaude Code側のhooksではなく
  GitHub側のbranch protection(mainへの直push禁止・PR必須)である
- 現時点ではチーム規模・期間から、そこまでの強制力は不要と判断

**再検討する条件:**
- メンバーが増える、または開発期間が延長される場合
- `main` への意図しない直pushが実際に発生した場合
  → その場合はGitHub branch protectionの有効化を優先的に検討する
