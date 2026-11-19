# makefun-tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/rizkydncrypto-tech/makefun-tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/rizkydncrypto-tech/makefun-tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4,096 bytes of Python: negamax with alpha-beta pruning,
iterative deepening under a fixed node budget, quiescence search over
captures and check evasions, a transposition table, killer and history move
ordering, null-move pruning, late-move reductions, a check extension, and
repetition awareness — all in a single `main.py` (4,080 bytes, standard
library only). It plays the house gauntlet through the env at
`MAKEFUN_ENV_URL` and searches to a fixed node count, never a clock, so
every trial replays move for move.

Local practice Elo against the house gauntlet: trial-0 1545, trial-1 1364,
trial-2 1364 (mean ~1424; the practice floor is 1154 and the house
baseline rates ~1365).

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 main.py
```

`main.py` is the whole engine: it reads the position from the env, picks a
move, and posts it back until every game is over. The compressed payload
inside it unpacks with `lzma` and runs as plain Python 3.13.

---

<sub>Entered on [make.fun](https://make.fun/?ref=dnpvszdc&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
