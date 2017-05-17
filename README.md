Overview
========

This is a set of Munin plugins for monitoring ClickHouse.
They are implemented as shell scripts, so there are no dependencies
except for curl.

The following plugins are included:

- clickhouse_database_size: Shows the amount of disk space taken by the data
- clickhouse_ingestion: Shows the number of inserted rows
- clickhouse_merges: Shows the number of merged rows
- clickhouse_queries: Shows the number of inserted and select queries

Installation
============

- Download or clone the project
- Run `src/install`
