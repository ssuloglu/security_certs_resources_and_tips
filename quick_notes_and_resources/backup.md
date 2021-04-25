## Backup

| Strategy | Time to Backup/Restore | # of tapes | data | bits |  
|----- | ---------------------- | ---------- | ---- | ---- |
| Full | High/Low | 1 | all selected data | + |
| Differential | Medium/Medium | n th diff (1 item) + 1 full | data changed since last full backup | - |
| Incremental | Low/High | n incremental (n items) + 1 full | all data changed since the last full or incremental backup  | + |

* Smapshots: captures data at a point in time (image backup). Most commonly used with virtual machines, can be referred to checkpoints as well.
Note: Every backup strategy starts with a full backup!
