> **Experimental. We are just trying this.** [Disclaimer](../../DISCLAIMER.md) · Kaspa Testnet-10 only; tKAS has no value. Counts only.

> **Our own testing.** What this page shows is what our probe read on our own desk node in this run; it is not a claim of how TN10 behaves in general.

# Mempool and template timeline, pre-run 32

Read by the probe on the desk's private TN10 node every 20 s, read-only; each cell is the median of that minute's samples. Pre-run 17: ready count and ready mass come from the full mempool read up to 10,000 entries and from the node's own figures (getFeeEstimateExperimental, verbose) above that, where the per-class columns stay blank (the node's wRPC replies are capped at 128 MiB, about 12,500 entries). Ready means no parent in the mempool: in rusty-kaspa v2.1.0 only those are in the selector's frontier. Ready mass is compared with one block's mass limit (500,000): at or under 1 the selector takes all ready transactions best-first; over 1 it samples at random weighted by (fee/mass)^3 (over 4, sample_inplace). Mass is the larger of compute and storage mass, as the v2.1.0 selector normalises it (transient mass is not in the RPC). Other traffic is every mempool entry not in our sender logs (our heavy lane is its own class, our heavy); its fee rate is the node's fee over that mass. Template transactions carry no id in the RPC, so each is matched to a mempool entry by its first input. The template is the desk node's own getBlockTemplate (never submitted): what this node would put in a block at that moment, not a miner's template. The fee estimate is the node's getFeeEstimate, read only; no sender reads it. Public mempool is getInfo's mempool size on each kept public kaspad.

## The run

Step is the runner's step at the minute's start (see TIMELINE.md).

| Minute (UTC) | Step | Samples | Mempool | Ready (no parent in mempool) | Ready mass, blocks of 500k | Other traffic in mempool | Other ready | Other at 100, n | Other at 100, mean mass | Our payments in mempool | Our heavy in mempool / ready | Floor in mempool / ready | Kcc in mempool / ready | Template txs | Template storage mass | Template txs over 100k storage mass | Template: payments | Template: our heavy | Template: floor | Template: kcc | Template: other | Fee estimate priority / normal / low | Public 1 mempool | Public 5 mempool |
|---|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|---|---:|---:|
| 2026-11-14T11:31 | families | 1 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 0 |
| 2026-11-14T11:32 | families | 1 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:33 | BASE | 3 | 12 | 12 | 0.99 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 496,950 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 12 | 2 |
| 2026-11-14T11:34 | BASE | 3 | 12 | 12 | 1.00 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 463,907 | 0 | 0 | 0 | 11 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:35 | BASE | 3 | 12 | 14 | 1.20 | 2 | 2 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 456,192 | 0 | 0 | 0 | 11 | 0 | 1 | 100.0 / 100.0 / 100.0 | 13 | 1 |
| 2026-11-14T11:36 | BASE | 3 | 13 | 13 | 1.01 | 1 | 1 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 454,085 | 0 | 0 | 0 | 11 | 0 | 1 | 100.0 / 100.0 / 100.0 | 14 | 8 |
| 2026-11-14T11:37 | HOLD-1 | 3 | 11 | 11 | 0.91 | 0 | 0 | 1 | 10,000 | 0 | 0 / 0 | 11 / 11 | 0 / 0 | 11 | 456,075 | 0 | 0 | 0 | 11 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 |
| 2026-11-14T11:38 | HOLD-1 | 3 | 12 | 12 | 0.99 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 412,094 | 0 | 0 | 0 | 10 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 |
| 2026-11-14T11:39 | HOLD-1 | 3 | 3 | 13 | 1.01 | 1 | 1 | - | - | 0 | 0 / 0 | 8 / 8 | 0 / 0 | 12 | 334,094 | 0 | 0 | 0 | 8 | 0 | 1 | 100.0 / 100.0 / 100.0 | 2 | 1 |
| 2026-11-14T11:40 | HOLD-2 | 3 | 10 | 12 | 1.00 | 0 | 0 | - | - | 0 | 0 / 0 | 11 / 11 | 0 / 0 | 12 | 497,599 | 0 | 0 | 0 | 11 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 |
| 2026-11-14T11:41 | HOLD-2 | 3 | 12 | 12 | 1.00 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 11 | 459,466 | 0 | 0 | 0 | 11 | 0 | 0 | 100.0 / 100.0 / 100.0 | 1 | 1 |
| 2026-11-14T11:42 | HOLD-2 | 3 | 12 | 12 | 0.99 | 0 | 0 | 1 | 3,362 | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 456,519 | 0 | 0 | 0 | 11 | 0 | 0 | 100.0 / 100.0 / 100.0 | 13 | 13 |
| 2026-11-14T11:43 | HOLD-3 | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 2 | 2 |
| 2026-11-14T11:44 | HOLD-3 | 3 | 12 | 12 | 0.99 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 497,289 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:45 | HOLD-3 | 3 | 10 | 10 | 0.83 | 0 | 0 | - | - | 0 | 0 / 0 | 10 / 10 | 0 / 0 | 10 | 414,919 | 0 | 0 | 0 | 10 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:46 | HOLD-4 | 3 | 12 | 12 | 0.99 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 494,579 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 12 | 0 |
| 2026-11-14T11:47 | HOLD-4 | 3 | 2 | 2 | 0.16 | 0 | 0 | - | - | 0 | 0 / 0 | 2 / 2 | 0 / 0 | 2 | 82,497 | 0 | 0 | 0 | 2 | 0 | 0 | 100.0 / 100.0 / 100.0 | 2 | 0 |
| 2026-11-14T11:48 | HOLD-4 | 3 | 0 | 12 | 0.99 | 0 | 0 | 3 | 41,080 | 0 | 0 / 0 | 9 / 9 | 0 / 0 | 11 | 452,228 | 0 | 0 | 0 | 9 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:49 | HOLD-4 | 3 | 9 | 11 | 0.91 | 0 | 0 | - | - | 0 | 0 / 0 | 11 / 11 | 0 / 0 | 11 | 453,574 | 0 | 0 | 0 | 11 | 0 | 0 | 100.0 / 100.0 / 100.0 | 2 | 0 |
| 2026-11-14T11:50 | HOLD-4 | 3 | 12 | 12 | 0.99 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 493,728 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 11 | 0 |
| 2026-11-14T11:51 | RETURN | 3 | 12 | 12 | 0.98 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 491,680 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:52 | RETURN | 3 | 10 | 10 | 0.66 | 0 | 0 | - | - | 0 | 0 / 0 | 8 / 8 | 0 / 0 | 10 | 327,581 | 0 | 0 | 0 | 8 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:53 | RETURN | 3 | 12 | 12 | 0.99 | 0 | 0 | - | - | 0 | 0 / 0 | 12 / 12 | 0 / 0 | 12 | 492,926 | 0 | 0 | 0 | 12 | 0 | 0 | 100.0 / 100.0 / 100.0 | 12 | 0 |
| 2026-11-14T11:54 | RETURN | 3 | 10 | 12 | 0.95 | 0 | 0 | - | - | 0 | 0 / 0 | 10 / 10 | 0 / 0 | 12 | 415,189 | 0 | 0 | 0 | 10 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:55 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:56 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:57 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:58 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T11:59 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
| 2026-11-14T12:00 | tail | 3 | 0 | 0 | 0.00 | 0 | 0 | - | - | 0 | 0 / 0 | 0 / 0 | 0 / 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 | 100.0 / 100.0 / 100.0 | 0 | 0 |
