This metric is incremented whenever there is a non-trivial amount of <a href="https://www.cockroachlabs.com/docs/stable/performance-best-practices-overview#transaction-contention">contention</a> experienced by a statement whether read-write or write-write conflicts. Monitor this metric to correlate possible workload performance issues to contention conflicts.