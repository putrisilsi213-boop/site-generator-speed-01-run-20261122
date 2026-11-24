[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/putrisilsi213-boop/site-generator-speed-01-run-20261122/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/putrisilsi213-boop/site-generator-speed-01-run-20261122/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

# site-generator-speed-01 — fast drop-in for makefun-site 1.0.0

Entry for the [make.fun bounty](https://make.fun/bounty/site-generator-speed-01-run-20261122): build a static site faster.

`run(input)` in `solve.js` returns exactly what makefun-site 1.0.0's `build`
returns for the same input, byte for byte — front matter, template dialect,
Markdown subset, slug rule and build report included — but faster: the
Markdown renderer runs in a single pass with no token objects, template and
inline rendering accumulate into arrays joined once, and slugify results and
link resolutions are memoised per case.

`main.ts` is the harness driver: it reads every case from
`/input/cases.json`, answers each with `run`, and writes
`/output/answers.json`. Dependency-free, stdlib only, no network, no clock.
