#### Cloudera Manager
$sudo ./cloudera-manager --express --force 
*This would required atleast 8 GB of RAM & 2 Cores/CPU to be allocated to VM

$sudo ./cloudera-manager --enterprise --force 
*This would required 16 GB of RAM & 2 Cores/CPU to be allocated to VM

#### Important unix commands
$uname -a
$hostname
$ping quickstart.cloudera

$jps
*This would list all processes started by current logged in user i.e. cloudera in our case

$sudo -u hdfs jps
*This would list all java processes started by hdfs user

$ps -fu hdfs
*This would list all processes started by hdfs user

$sudo -u yarn jps
*This would list all java processes started by yarn user

$ps -fu yarn
*This would list all processes started by yarn user

$ps -aef | grep manager
*This would list all processes by grepping 'manager'

#### MySQL
$mysql -u root -p -h quickstart.cloudera -p3306

mysql>show databases;

mysql>exit;

$mysql -u retail_dba -p -h quickstart.cloudera -P3306

mysql>show databases;

mysql>use retail_dba;

mysql>show tables; 

mysql>exit; 

#### HDFS
$hadoop version

$hadoop fs -ls /user

$hadoop fs -ls -R /user/hive 

$touch test.txt

$hadoop fs -put test.txt /user/cloudera

$hadoop fs -ls /user/cloudera/test.txt

#### Sqoop
$sqoop help

$sqoop version

$sqoop import --help

$sqoop list-databases \
 --connect jdbc:mysql://quickstart.cloudera:3306 \
 --username retail_dba \
 --password cloudera

$sqoop list-tables \
 --connect jdbc:mysql://quickstart.cloudera:3306/retail_db \
 --username retail_dba \
 --password cloudera

#### Flume
$flume-ng version

$flume-ng help

$ls -ltr /opt/examples/flume

#### Hive
$hive
hive>show databases;
hive>show tables;
hive>create database db_test;
hive>use db_test;
hive>exit;

#### Impala
$impala-shell
quickstart.cloudera:21000>show databases;
quickstart.cloudera:21000>invalidate metadata;
quickstart.cloudera:21000>use db_test;
quickstart.cloudera:21000>show tables;

#### Spark - Scala shell
$spark-shell --version

$spark-shell --help

$spark-shell
scala>exit;

#### Spark - Python shell
$pyspark --version

$pyspark --help
exit()

#### Avro tools
$avro-tools

$avro-tools getschema

$avro-tools fromjson


