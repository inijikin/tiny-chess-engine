# Trials (practice, local env server, kit gauntlet)

Engine: 0x88 board, negamax alpha-beta + transposition table, killer moves,
MVV-LVA ordering, quiescence (captures/promotions + check evasions),
material + piece-square eval. Fixed node budget 200,000/move, deterministic
(no clock, no unseeded randomness). Max think ~5 s/move, trial wall ~1,520 s.

| Trial | Result | Score | Elo |
|---|---|---|---|
| trial-0 | 3W 1D 4L (G4 draw, threefold repetition) | 3.5/8 | 1,326 |
| trial-1 | 4W 2D 2L (G4 win vs nodes-100k; G6 draw vs nodes-500k; G7 draw vs nodes-1M) | 5/8 | 1,530 |
| trial-2 | 3W 2D 3L (G4 draw vs nodes-100k; G5 draw vs nodes-250k) | 4/8 | 1,396 |

Mean Elo: **1,417** over 3 practice trials.
House baseline sunfish 4 KB: mean 1,325 (1,326 / 1,396 / 1,253). Lead: **+92**.

Wins vs depth-2, depth-3, depth-4 in every trial. Losses only vs nodes-250k
and above (except trial-1 G4 win and trial-2 G4/G5 draws).
