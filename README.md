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

From Package
------------

Run `sudo dpkg -i infi.clickhouse-munin.deb`

From Source
-----------

Download or clone the project, then run:

    sudo ln -sf src/plugins/clickhouse_* /etc/munin/plugins/
    sudo restart munin-node


Configuration
=============

The plugins use two environment variables:

- CLICKHOUSE_DATADIR (defaults to `/var/lib/clickhouse/data`)
- CLICKHOUSE_URL (defaults to `http://localhost:8123/?readonly=1`)

To customize their values, create a configuration file called `/etc/munin/plugin-conf.d/zzz-myconf` and set the custom values:

    [clickhouse_*]
    env.CLICKHOUSE_DATADIR /opt/clickhouse/data
    env.CLICKHOUSE_URL http://clickhouse:8123/?readonly=1


Packaging
=========

To update the .deb file, run `src/build_deb`.
