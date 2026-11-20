# tiny-chess-01

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Rain-123-png/tiny-chess-01/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Rain-123-png/tiny-chess-01/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in at most 4,096 bytes of Python 3.13, standard library only. It plays a gauntlet of house engines through the make.fun env over HTTP and chooses every move deterministically under a fixed search budget, never a clock.

## Engine notes

The entry is a negamax alpha-beta searcher with principal-variation search, a transposition table, null-move pruning, late-move reductions, check extensions and a capture quiescence search, over a 0x88 board with fully incremental material and piece-square evaluation. The node budget is fixed at 100,000 per move, so the same position always gets the same move. On the kit's three practice trials it scored Elo 1545, 1545 and 1279 against the anchored house ladder. The readable source is packed into the single-file entrypoint with the kit's official `makefun compress`.

## Run it

```sh
MAKEFUN_ENV_URL=<env-url> python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=ac9vjbzn&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
