- Any queries you run against tables with Row-Level TTL enabled do not filter out expired rows from the result set (this includes [`UPDATE`s]({% link {{ page.version.version }}/update.md %}) and [`DELETE`s]({% link {{ page.version.version }}/delete.md %})). This feature may be added in a future release. For now, follow the instructions in [Filter out expired rows from a selection query]({% link {{ page.version.version }}/row-level-ttl.md %}#filter-out-expired-rows-from-a-selection-query).
 The queries executed by Row-Level TTL are not yet optimized for performance in the following ways:
   - They do not use any indexes. [cockroachdb/cockroach#82140](https://github.com/cockroachdb/cockroach/issues/82140)