> **Experimental. We are just trying this.** [Disclaimer](../DISCLAIMER.md) · Kaspa Testnet-10 only. tKAS has no value.

# Lessons

The prediction page is not edited. A wrong row is the lesson.

- Hops were higher than the guess. The guess was about 800 a minute. From 11:33 through 11:54 UTC the chain counter read 829–985 floor hops a minute, and every one of those rows says kept pace. The open-window hop count on the coordinator is 20,377. The chain counter's whole-run floor is 20,401. Both numbers are published as read. We did not force them to match.
- The template guess held. It was the row we marked most likely to be wrong. In the three published HOLD-2 minutes, ready mass was 1.00, 1.00 and 0.99 blocks of 500,000, the template held 11 or 12 transactions (storage mass 497,599, 459,466 and 456,519), and the coordinator read 2,678 of 2,678 floor hops landed (median 611 ms, p95 1,190 ms).
- Mints were 30 of 30, rejected 0. The mint column goes to 0 after 11:40 because the cap was hit (15 in BASE, 12 in HOLD-1, 3 in HOLD-2), not because a mint failed. Fees on the mint line: 1.2465 tKAS.
- The guest line is 8 of 8, and the path to that count is our own. The issuer began with one coin. We split it into two in the same window (fee 0.002046 tKAS) and the match then passed its gate. The first guest tool would have saved a zero: it treated an older abort, still in the phase log, as the result of the new match. We stopped that tool, matched all 8 logged ids on the desk node's accepted set, and the runner published that file. The 8 is that confirm. We would rather the tool had done it alone.
- Nothing fell behind. The "none" guess held. The mint line stopping is the cap.
- Fees were lower than the guess of about 1,000 tKAS. The sender log sums to 844.7361 tKAS on 20,401 hops accepted by the sender as OK, plus 1.2465 tKAS of mints. The fund of the twelve family keys was 0.024552 tKAS. The issuer split was 0.002046 tKAS.
- Two published sentences say the family count was "raised from 4". The lock for this run says 8 → 12. Those sentences are leftover runner text. We do not rewrite the count files to hide them.
- This run is not a capacity step. About 900 hops a minute and ready mass near one block is far under 3,040 payments a second. It does not say what holds at one third, two thirds, three thirds or four thirds of that line.
- The public free check before the open kept 3 distinct nodes out of 9 names. The runner's own preflight, on a shorter list, kept 2. Those are different lists. We do not treat the 2 as a correction of the 3.
- Retry count 0. An earlier start held at genesis because the hash submit still asked for a Mini arm file, and it submitted nothing. That hold is not a retry.
- The desk node was not restarted. Nothing in this run was sent to a public node. A sample of 880 of our accepted ids, taken 60 seconds or more later, found 0 still listed in the mempool.
