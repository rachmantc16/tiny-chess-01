# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/rachmantc16/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/rachmantc16/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original chess engine in one Python file: a 0x88 board, negamax alpha-beta with a transposition table, killer/history move ordering, null-move pruning, late-move reductions, check extensions and a quiescence search over captures, promotions and check evasions, evaluated by material plus piece-square tables. It searches to a fixed node budget per move — never a clock — so a replayed trial plays the same moves, and it plays the make.fun house gauntlet through the env.

## Run it

```sh
MAKEFUN_ENV_URL=<env origin> python3 -P -s main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=pas2z9sw&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
