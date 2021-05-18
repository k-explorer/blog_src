---
title: "Hive or Spark"
date: 2021-04-26T16:08:06-07:00
draft: false
tags:
  - Software
---


![Spark](/blog/images/spark.png)
{{< figure src="/blog/images/hive.png" height="200" >}}
Lots of data scientists wonder whether to use Apache Hive or Apache Spark. This article aims to condense the problem into a short comparison.

## Dependencies {#dependencies}

Apache Hive runs on Apache Hadoop, a complex data warehouse built in Java. To use Hive, Hadoop must be installed and configured as well. Spark, on the other hand, originally required Hadoop but does not currently. Hive is it&#8217;s own Java library, but Spark has a different distribution for each of it&#8217;s three supported languages:

  1. Spark: Scala
      * This is the most used Spark distribution
  2. PySpark: Python
      * Python distribution: not as commonly used
  3. SparkR: R
      * This distribution is an R package. Another R package used for Spark, "[sparklyr][1]", is much more popular, as this package has many problems. While SparkR was built by the original Apache Spark team, "sparklyr&" was built by RStudio, the developers of the popular R IDE.

## Installation {#installation}

Apache provides zips and .tar.gz files for both software. In addition, they can both be installed with the [Homebrew][2].

## Performance

Hadoop is great for **batch processing**, but is extremely slow with **iterative** or **stream processing** (see [Data Processing][3]). When researchers at University of California, Berkeley, who were using Hive, discovered this, they built Spark to fix the problem. They discovered that for iterative processing, Spark could be over **_100 times faster_** than Hive!

## Data Processing {#data-processing}

Apache Hive uses Hadoop MapReduce to process data, while Spark uses Resilient Distributed Databases (RDDs). While Hive uses batch processing, Spark uses stream processing. When batch processing, data is processed once all the data has been collected. Obviously, this is not a good option for real-time data processing. Stream processing processes small packets of data as they come in.

## Data Storage {#data-storage}

Spark does not provide a distributed file storage system, so it is mainly used for computation, on top of a Hadoop database, though Hadoop is not a Spark prerequisite (see [Dependencies][4]). Spark can connect to [SQL libraries][5], however, and these can be used to store data. Hadoop&#8217;s only option is to use HDFS (**H**adoop **D**istributed **F**ile **S**torage).

## Conclusion {#conclusion}

Overall, the choice of using Spark or Hive depends on what _you_ want to do with your data. It&#8217;s a matter of opinion, and neither is the better choice.

 [1]: https://spark.rstudio.com
 [2]: https://brew.sh
 [3]: #data-processing
 [4]: #dependencies
 [5]: blog/posts/what-is-sql-anyway#sql-libraries
