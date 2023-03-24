<!--
 Licensed to the Apache Software Foundation (ASF) under one
 or more contributor license agreements.  See the NOTICE file
 distributed with this work for additional information
 regarding copyright ownership.  The ASF licenses this file
 to you under the Apache License, Version 2.0 (the
 "License"); you may not use this file except in compliance
 with the License.  You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

 Unless required by applicable law or agreed to in writing,
 software distributed under the License is distributed on an
 "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
 KIND, either express or implied.  See the License for the
 specific language governing permissions and limitations
 under the License.
-->

# Spark + Iceberg + Delta Lake + Jupyter Notebook (Python, Scala)

This is a docker compose environment to quickly get up and running with a Spark environment and a external hive catalog using Postgre
, and MinIO as a storage backend.

**note**: If you don't have docker installed, you can head over to the [Get Docker](https://docs.docker.com/get-docker/)
page for installation instructions.

## Usage
Start up the notebook server by running the following.
```
docker-compose up
```

The notebook server will then be available at http://localhost:8888

While the notebook server is running, you can use any of the following commands if you prefer to use spark-shell, spark-sql, or pyspark.
```
docker exec -it spark-iceberg spark-shell
```
```
docker exec -it spark-iceberg spark-sql
```
```
docker exec -it spark-iceberg pyspark
```

The dellta lake support is enabled in spark default catalog `spark_default` while iceberg uses `iceberg` catalog.

To stop everything, just run `docker-compose down`. The data directories for metastore and the MinIO are mounted locally and changes will be persisted even after the shutdown.


## Cleanup

Use `cleanup.sh` to clean the directories for metastore and the storage.

---

For more information on getting started with using Iceberg, checkout
the [Getting Started](https://iceberg.apache.org/getting-started/) guide in the official docs.

The repository for the docker image is [located on dockerhub](https://hub.docker.com/r/tabulario/spark-iceberg).
