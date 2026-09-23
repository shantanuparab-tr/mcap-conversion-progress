# MCAP conversion progress

`progress.csv` is written every 15 minutes by `progress_watch.py` on the
conversion host. It counts episodes under the NAS raw tree against the staging
tree, so it reports what is actually on disk rather than what a job claims.

Columns:

| column | meaning |
|---|---|
| Episodes | raw `.mcap` files under that dataset on the NAS |
| Raw GB | their size on the NAS, shrinking as episodes are replaced |
| Compressed on NAS | episodes that have a compressed copy, staged or in place |
| Complete | raw in S3, compressed in S3, and the compressed file sitting at the raw's path on the NAS |
| Done % | Complete over Episodes |
| Status | done, running, partial or pending, with a colour glyph |
| Running on | which machine is encoding that dataset right now |

The footer carries the timestamp, NAS free space, live encoder counts and any
watchdog warnings.
