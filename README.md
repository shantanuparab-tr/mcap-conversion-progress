# MCAP conversion progress

`progress.csv` is written every 15 minutes by `progress_watch.py` on the
conversion host. It counts episodes under the NAS raw tree against the staging
tree, so it reports what is actually on disk rather than what a job claims.

Columns: dataset, episodes, raw size in GB, episodes converted, episodes with
both copies in S3, percent complete. The footer carries the timestamp, NAS free
space, live encoder counts and any watchdog warnings.
