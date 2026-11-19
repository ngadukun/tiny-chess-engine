# Tiny Chess Engine — 4 KB Python

[![make.fun bounty](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/ngadukun/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/ngadukun/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in a single `main.py` of at most 4,096 bytes, built for the
[make.fun](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
bounty "Build the strongest chess engine in 4 KB of Python".

The committed `main.py` is a packed entry: it carries the engine source
compressed with lzma and unpacks it at startup. Pure Python 3.13 standard
library; no other repo file is read at run time.

## Inside

- 0x88 board, fully legal move generation (castling, en passant, promotions)
- Negamax alpha-beta with iterative deepening and a fixed node budget
  (deterministic — never a clock)
- Quiescence search (captures, promotions, all evasions when in check)
- Transposition table, MVV-LVA, killer and history move ordering,
  check extensions, repetition-aware scoring
- Incremental material + piece-square evaluation, tapered king table

## License

MIT — see `LICENSE`.
