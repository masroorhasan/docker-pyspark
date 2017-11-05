# PySpark Dockerfile
Dockerfile for running [PySpark](https://spark.apache.org/docs/0.9.0/python-programming-guide.html) on Ubuntu base image. Available @ [masroorhasan/pyspark](https://hub.docker.com/r/masroorhasan/pyspark/).

## Base image
* [ubuntu:latest](https://github.com/dockerfile/ubuntu) 

## Installation
1. Install Docker.
2. Pull [masroorhasan/pyspark](https://hub.docker.com/r/masroorhasan/pyspark/).

## Build
Build and tag the image.
```
docker build -t pyspark --no-cache .
```

## Usage
**Run container** 
Run `pyspark` container instance in interactive mode to access cmd shell.
```
docker run -it --rm pyspark
```

**Run pyspark** 
Pyspark installed in working directory `/data`.
```
root@b06dec38c2ea:/data# pyspark
Python 2.7.12 (default, Nov 19 2016, 06:48:10) 
[GCC 5.4.0 20160609] on linux2
Type "help", "copyright", "credits" or "license" for more information.
Using Spark's default log4j profile: org/apache/spark/log4j-defaults.properties
Setting default log level to "WARN".
To adjust logging level use sc.setLogLevel(newLevel). For SparkR, use setLogLevel(newLevel).
17/11/04 20:29:16 WARN NativeCodeLoader: Unable to load native-hadoop library for your platform... using builtin-java classes where applicable
17/11/04 20:29:24 WARN ObjectStore: Version information not found in metastore. hive.metastore.schema.verification is not enabled so recording the schema version 1.2.0
17/11/04 20:29:24 WARN ObjectStore: Failed to get database default, returning NoSuchObjectException
17/11/04 20:29:26 WARN ObjectStore: Failed to get database global_temp, returning NoSuchObjectException
Welcome to
      ____              __
     / __/__  ___ _____/ /__
    _\ \/ _ \/ _ `/ __/  '_/
   /__ / .__/\_,_/_/ /_/\_\   version 2.2.0
      /_/

Using Python version 2.7.12 (default, Nov 19 2016 06:48:10)
SparkSession available as 'spark'.
>>> 
```

**Create RDDs**
Create a sample RDD from spark context.
```
>>> rdd = spark.sparkContext.parallelize([("a",["x","y","z"]), ("b",["p", "r"])])
>>> rdd.first()
```

Output:
```
('a', ['x', 'y', 'z'])
```
