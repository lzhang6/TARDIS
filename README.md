# 1. Setting for runing environment 
* * *
## 1.1 Requirements
Our Cluster install Apache Spark 2.1.1. and Hadoop-2.7.3.  If you need to run it in other Spark version, just update the spark version in build.sbt file of source code and recompile it.

## 1.2 Building
The code has been writen in Scala and compiled in SBT.

## 1.3 Configuration & Usage
### 1.3.1 Application Configure 

Make a directory: mkdir ./etc and put the config.conf file under it.
Change the configure in config.conf file. 
* rw**  : parameters generate raw time series;
* idx** : parameters generate TARDIS index;
* cl**  : parameters create ground truth for KNN query;
* eq**  : parameters control the exact match query and KNN query;

### 1.3.2 Run code:

Before running promgram:
1. create etc directory and put config.conf file under etc.
2. create log directory.
3. put spark-defaults.conf under the directory or use the default spark program configuration.

~/spark/bin/spark-submit --class org.apache.spark.edu.wpi.dsrg.tardis.TARDIS --properties-file ./spark-defaults.conf  tardis_2.11-1.0.jar -h
* -h : display help information;
* -g : generage raw time series;
* -b : build index;
* -c knn : create ground truth for knn query;
* -q : run time series similiary query;

eqQueryType = exact: exact matching query, knn: kNN-Aproximate query
eqKnnType = 0: target node access, 1: one partition access, 2: multi partitions access

### 1.3.3 Cluster Configure

Change cluster application configure in the spark-defaults.conf   
For whole cluster environment, consult your cluster administor. The configure file should be stored under hadoop/etc/hadoop/ and spark/conf directories.

### 1.3.4 Download

The **source code** and **jar file**  would be avaiable after the acceptance of paper.

# 2. Technical Report
* * *
This technical report is the complement of the paper. 

[Technical Report](fig/report.pdf)