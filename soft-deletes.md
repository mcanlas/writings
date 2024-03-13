---
updated: March 2024
---
# Soft deletes

In traditional data management, when you "delete" something, it ceases to exist completely, at least from the perspective of the user.

An alternative to this mechanism is to have a flag on each entity that specifies whether or not something is truly deleted. With this in place, a privileged user can continue to see all records, even after deletion.

## Pros

- Records are never truly deleted, allowing for easy recovery and un-deletion.

## Cons

- Readers of the data must use managed interfaces to take into account the deletion flag
  - "Total" counts of records will differ based on the inclusion of deleted records

## See also

- [March 13, 2024 Reddit thread](https://www.reddit.com/r/programming/comments/1bd3sdk/the_day_soft_deletes_caused_chaos/)
  - [Linked article, "The Day Soft Deletes Caused Chaos"](https://blog.bemi.io/soft-deleting-chaos/)
