# Metabase Trino Driver

An example for how to implement a Trino driver based off existing Presto JDBC support in Metabase.

_Please note this only supports the latest unstable version of Metabase until v0.41 is released_

_This is also just an example of how to implement this - I DO NOT plan on supporting a Trino driver. :)_

## Prerequisites

The next version of Metabase [changes how plugins](https://github.com/metabase/metabase/pull/17606) are built. You'll need to use the latest branch.

```shell
git clone https://github.com/metabase/metabase.git
```

## Compiling

- Update `deps.cdn`

For some reason, absolute paths are necessary in this file, so you'll have to update it with the path as necessary.

- Build the plugin

```shell
clojure -X:dev:build
```

- Copy the resulting drive to wherever you have Metabase checked out

```shell
cp target/trino.metabase-driver.jar ../metabase/plugins/
```

## Running

- Spin up the latest development branch of Metabase:

```
clojure -M:run:drivers
```