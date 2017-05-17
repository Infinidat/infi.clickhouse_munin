Overview
========

This is a set of Munin plugins for monitoring ClickHouse. They are implemented as shell scripts, so there are no dependencies except for curl.

The following plugins are included:

|Name|Description|
|----|-----------|
|clickhouse_database_size|Shows the amount of disk space taken by the data|
|clickhouse_ingestion|Shows the number of inserted rows|
|clickhouse_merges|Shows the number of merged rows|
|clickhouse_queries|Shows the number of insert and select queries|

Installation
============

- Download or clone the project
- Run `src/install`

Configuration
=============

The plugins use two environment variables:

- CLICKHOUSE_DATADIR (defaults to `/var/lib/clickhouse/data`)
- CLICKHOUSE_URL (defaults to `http://localhost:8123/?readonly=1`)

To customize their values, create a configuration file called `/etc/munin/plugin-conf.d/zzz-myconf` and set the custom values:

    [clickhouse_*]
    env.CLICKHOUSE_DATADIR /opt/clickhouse/data
    env.CLICKHOUSE_URL http://clickhouse:8123/?readonly=1
