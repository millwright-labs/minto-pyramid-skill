# Checkout outage — 14 March

02:14 — Pager fires. Checkout 500s at ~40% of requests.
02:20 — Priya acks. Confirms error rate climbing, not flat.
02:31 — Rolled back the 02:00 deploy. No improvement.
02:48 — Found connection pool exhausted on payments-db. Pool size 20, normally
        plenty.
03:05 — Raised pool to 60. Error rate drops to ~4% within two minutes.
03:20 — Traced the leak to the new refund handler: it opens a connection per
        retry and never closes on the timeout path.
03:41 — Shipped hotfix disabling the retry loop. Errors to zero.
04:10 — Pool returned to 20. Stable.
04:30 — Stood down.

Customer impact: roughly 2h15m of degraded checkout, ~11,400 failed attempts.
Refund handler had shipped six days earlier; the leak only bit once retry
volume crossed a threshold, which is why it took a week to show up.
