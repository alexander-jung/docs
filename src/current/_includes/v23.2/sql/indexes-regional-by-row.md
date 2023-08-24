 In [multi-region deployments]({% link {{ page.version.version }}/multiregion-overview.md %}), most users should use [`REGIONAL BY ROW` tables]({% link {{ page.version.version }}/table-localities.md %}#regional-by-row-tables) instead of explicit index [partitioning]({% link {{ page.version.version }}/partitioning.md %}). When you add an index to a `REGIONAL BY ROW` table, it is automatically partitioned on the [`crdb_region` column](alter-table.html#crdb_region). Explicit index partitioning is not required.

 While CockroachDB process an [`ADD REGION`]({% link {{ page.version.version }}/alter-database.md %}#add-region) or [`DROP REGION`]({% link {{ page.version.version }}/alter-database.md %}#drop-region) statement on a particular database, creating or modifying an index will throw an error. Similarly, all [`ADD REGION`]({% link {{ page.version.version }}/alter-database.md %}#add-region) and [`DROP REGION`]({% link {{ page.version.version }}/alter-database.md %}#drop-region) statements will be blocked while an index is being modified on a `REGIONAL BY ROW` table within the same database.