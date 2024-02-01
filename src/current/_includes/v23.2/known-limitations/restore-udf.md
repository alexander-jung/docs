`RESTORE` will not restore a table that references a [UDF]({% link {{ page.version.version }}/user-defined-functions.md %}), unless you skip restoring the function with the {% if page.name == "restore.md" %} [`skip_missing_udfs`](#skip-missing-udfs) {% else %} [`skip_missing_udfs`]({% link {{ page.version.version }}/restore.md %}#skip-missing-udfs) {% endif %} option. Alternatively, take a [database-level backup]({% link {{ page.version.version }}/backup.md %}#back-up-a-database) to include everything needed to restore the table. [Tracking GitHub Issue](https://github.com/cockroachdb/cockroach/issues/118195)