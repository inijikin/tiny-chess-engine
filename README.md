# tiny-chess-engine

A 4 KB Python chess engine for the make.fun tiny-chess-01 bounty: beat the
house gauntlet, not just play it.

## Engine

`main.py` is the whole engine (at most 4,096 bytes as committed, Python 3.13
standard library only, reads/imports/execs no other file):

- 0x88 board, incremental material + piece-square evaluation (Michniewski
  tables) with a bishop-pair bonus.
- Negamax alpha-beta with a Zobrist transposition table, killer moves,
  MVV-LVA capture ordering and quiescence (captures and promotions, all
  evasions when in check).
- Iterative deepening to a fixed node budget — deterministic, no clock, no
  unseeded randomness, so a replay plays the same moves.
- Draw-aware: repetition (search line and game history) and insufficient
  material score 0; mate scores prefer the faster mate.

## Results

Practice trials against the house gauntlet (local env server, kit's
practice trials) are recorded in the repo's commit history; see
`TRIALS.md` for the per-trial scores and Elo.

## Licence

MIT. Written from scratch for this bounty; the sunfish engine was used
only as a local test opponent and is not part of this repository.
