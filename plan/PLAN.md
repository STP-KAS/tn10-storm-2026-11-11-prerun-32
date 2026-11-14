> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · This page does not start a machine. Pre-run 32. Not Wednesday. Not Tuesday. Not pre-runs 1 to 31.

# Targets

**Question.** Pre-run 25 landed everything with 8 covenant families, and the arithmetic then was that about 12 ready hops of this shape fill one block template. Do the hop line, the mint line and one tic-tac-toe match still land when the family count is 12, and does any component fall behind?

**Target.** All three still land on our desk node between `PRE-RUN-OPEN` and the end of RETURN: at least one covenant hop, one KCC-20 mint and one tic-tac-toe carrier. The run names the first component whose landings fall off, with the load at that minute. If nothing falls off, that is met too: "no component fell behind at this step." Retry count 0.

## The one knob, written before the arm

**The floor family count, 8 → 12.** Everything else is pre-run 25's: the floor rate (100 sompi per gram of node mass), the offer per family (1.2 hops a second, one family-sender process, one builder), the mint line (one at a time, accept then 15 s, cap 30), one guest match (one carrier at a time), the same step lengths. No heavy lane. No payment flood. No public send.

Two recorded facts that are not a second knob:

- The Mini is not reachable from this desk. This run has one counter, the desk node. [logs/MINI-NOT-REACHABLE.md](../logs/MINI-NOT-REACHABLE.md) is on origin before the arm. We do not write a Mini-armed file.
- The other keys have no coin of at least 15 tKAS for a genesis, so every family's genesis coin comes from the sender key. Keys 1 and 2 are not used. That key has 2,316 coins of at least 15 tKAS.

## Order

1. Disk floor written. Desk free space at 2026-11-14T11:18:39Z: 340.2 GB. Abort under 150 GB. The desk node is not restarted.
2. Free check, read-only, before the open. This run does not send to a public node.
3. Funding already on the sender key. No new move from the mining wallet. The runner's `BUDGET_CHECK` still runs before genesis and holds the run if the projected end is under 18,000 plus the 8,000 margin.
4. Hashes first. Thirteen rows in [hashes/SIXTEEN.md](../hashes/README.md) (the file keeps that name). The offline check builds them and does not submit.
5. `PRE-RUN-OPEN`, then genesis of the thirteen covenants, then the twelve families, the mint line and one guest match.

| Order | File | What runs | Length |
|---:|---|---|---|
| 1 | BASE | families 1–12 at 100, the mint line, one guest match | 3 whole minutes |
| 2 | HOLD-1 | the same | 3 whole minutes |
| 3 | HOLD-2 | the same | 3 whole minutes |
| 4 | HOLD-3 | the same | 3 whole minutes |
| 5 | HOLD-4 | the same. No bot send | the pinned minute |
| 6 | RETURN | the same (the mint line may have reached its cap) | 3 whole minutes |
| 7 | tail | families stopped, the counter reads on | 5 minutes |

The knob is turned once, before genesis, and not again.

## Cohorts

| Cohort | Families | Rate, sompi/gram of node mass | What |
|---|---|---:|---|
| floor | 1–12 | 100, fixed | covenant families, one hop per transaction |
| kcc | 13 | 100, fixed | the fresh KCC-20 launch; one mint at a time |

## Budget, read before this page

Sender key, our desk node, 2026-11-14: 3,373 coins over 3 tKAS, holding 95,872 tKAS. The runner's usable figure subtracts 3 tKAS on each of those coins, about 85,753 tKAS. Planned family time is 25 minutes at the runner's 760 tKAS a minute, about 19,000 tKAS. Projected end is about 66,000 tKAS, over the 18,000 line and the 8,000 margin. Coin count over 3 tKAS is 3,373, over the 2,500 line. No split.

## Guest

One match from the guest kit already on this desk, in a local container, sent to our own node. Counted only when the carrier id the kit logged is among the desk node's accepted ids.
