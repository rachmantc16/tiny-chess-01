# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/rachmantc16/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/rachmantc16/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

An original chess engine in one Python file: a 0x88 board, negamax alpha-beta with a transposition table, killer/history move ordering, null-move pruning, late-move reductions, check extensions and a quiescence search over captures, promotions and check evasions, evaluated by material plus piece-square tables. It searches to a fixed node budget per move — never a clock — so a replayed trial plays the same moves, and it plays the make.fun house gauntlet through the env.

## Engine

The board is 0x88: 128 squares, so off-board tests are one bit check.
Search is negamax alpha-beta with a Zobrist-keyed transposition table
(capped at 300,000 entries), killer-move ordering, null-move pruning
(depth ≥ 3, not in check, non-pawn material present), late-move
reductions for quiet moves past the third, and check extensions. Leaves
are finished by a quiescence search over captures, promotions and check
evasions; mates are scored by ply so the fastest mate wins. Evaluation
is material (pawn 100, knight 320, bishop 330, rook 500, queen 900)
plus piece-square tables, a bishop-pair bonus and a king table that
tapers toward the endgame as material leaves the board.

## Run it

```sh
MAKEFUN_ENV_URL=<env origin> python3 -P -s main.py
```

`main.py` is the whole engine: the readable source is packed with
`makefun compress` into an LZMA payload inside `main.py`, which unpacks
it at startup; no other file is read at runtime. Size limits:
`main.py` 4,023/4,096 bytes, submitted snapshot 7,744/8,192 bytes.

## Measured results

Practice trial-0: Elo 1451 (4 wins, 0 draws, 2 losses vs the house engines). Local perft: 6/6 standard positions pass. Sizes: `main.py` 4,023/4,096 bytes; snapshot 7,744/8,192 bytes. The practice score is a single trial instance, and the $500 prize is not escrowed.

---

<sub>Entered on [make.fun](https://make.fun/?ref=pas2z9sw&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
