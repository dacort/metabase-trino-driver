--------

⚠️ An official driver is now available at https://github.com/starburstdata/metabase-driver

--------



# Metabase Trino Driver

An example for how to implement a Trino driver based off existing Presto JDBC support in Metabase.

_Please note this only supports `v0.42.0-preview1` version of Metabase until v0.42 is released_

_This is also just an example of how to implement this - I DO NOT plan on supporting a Trino driver. :)_

## Prerequisites

- Docker

## Run Metabase

If you just want to run the 0.42 preview release of Metabase with this driver, just do a `docker build` and `run`.

```shell
docker build -t metabase/trino .
docker run --rm --name metabase-trino -p 3000:3000 metabase/trino
```

This will load up Metabase on port 3000 with the Trino driver loaded up.

### Build Jars

If you want the Trino jar to copy to your own Metabase intallation, you can use the `--output` flag with `docker build`.

```shell
docker build --output jars --target stg_export .
```

If successful, you should have a `jars/trino.metabase-driver.jar` file.
