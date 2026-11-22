# URL Shortener with Analytics
• Sustained 2,400 requests/second at 18 ms p95 latency to serve redirects at scale, using Spring Boot with
a Redis cache-aside layer (TTL 10 min) in front of PostgreSQL, load-tested with k6 at 1,000 virtual users.
• Cut redirect lookup time from 118 ms to 0.9 ms on a 1-million-row table, using a B-tree index on the shortcode column, verified with EXPLAIN ANALYZE.
• Blocked abusive traffic at 100 requests/minute per client to keep database CPU under 35%, using a Redis
token-bucket rate limiter.
• Reached 84% unit-test coverage and kept services easy to extend, using SOLID principles, layered
controller-service-repository design and dependency injection.
• Compared MySQL and PostgreSQL for the metadata store and chose PostgreSQL, which had 22% lower
p95 write latency under 500 concurrent inserts and supports partial indexes for expiring links.
