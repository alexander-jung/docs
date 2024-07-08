{{site.data.alerts.callout_info}}
When running under the default [`SERIALIZABLE`]({% link {{ page.version.version }}/demo-serializable.md %}) isolation level, your application should [use a retry loop to handle transaction errors]({% link {{ page.version.version }}/query-behavior-troubleshooting.md %}#transaction-retry-errors) that can occur under [contention]({{ link_prefix }}performance-best-practices-overview.html#understanding-and-avoiding-transaction-contention). Client-side retry handling is **not** necessary under [`READ COMMITTED`]({% link {{ page.version.version }}/read-committed.md %}) isolation.
{{site.data.alerts.end}}