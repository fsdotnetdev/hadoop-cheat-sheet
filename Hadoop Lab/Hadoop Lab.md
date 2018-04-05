# Hadoop Lab
Documentation for hadoop lab

# Table of Content
* Install Docker on Ubuntu 14.04 ++
* Docker Command
* Hadoop Command
* Create File mapper.py
* Create File reducer.py
* Hadoop Count
* Hive Command

## Install Docker on Ubuntu 14.04 ++
```bash
$ sudo su -
# apt-get update
# apt-get install docker.io
```

## Docker
* Docker Pull Image
```bash
$ docker pull cloudera/quickstart:latest
```

* Docker Run Container
```bash
$ docker run -v /root:/mnt --hostname=quickstart.cloudera --privileged=true -t -i -p 9092:9092 -p 2181:2181 -p 11122:11122 cloudera/quickstart /usr/bin/docker-quickstart
$ docker run -v /root:/mnt -e HOST_HOSTNAME=quickstart.cloudera --hostname=quickstart.cloudera --privileged=true -it -p 9092:9092 -p 2181:2181 -p 11122:11122 -p 8080:8080 -p 8440:8440 -p 8441:8441 fsdotnet/hadoop /usr/bin/docker-quickstart
```

* Docker Exec Container
```bash
$ docker exec -it [container_id] bash
```

## Hadoop Command
```bash
# yum install vim wget -y
# vi /mnt/test.txt
# service hadoop-hdfs-datanode start
# service hadoop-hdfs-namenode start
# hive --service metastore 
# service hive-server2 start
$ hadoop fs -put /mnt/test.txt /user/cloudera
$ hadoop fs -ls /user/cloudera
$ hadoop fs -cat /user/cloudera/test.txt
$ hadoop fs -get /user/cloudera/test.txt test1.txt
$ hadoop fs -mkdir -p /user/cloudera/temp
$ hadoop fs -cp /user/cloudera/test.txt /user/cloudera/temp/test.txt
$ hadoop fs -rm /user/cloudera/temp/test.txt
$ hadoop fs -rmdir /user/cloudera/temp
$ hadoop fs -ls /user/cloudera
```

## Fix NameNode is in Safe Mode
```bash
$ sudo -u hdfs hadoop dfsadmin -safemode leave
```

## Create File mapper.py in /mnt
```bash
#!/usr/bin/env python

from operator import itemgetter
import sys

if __name__ == '__main__':
	for line in sys.stdin:
		for word in line.split():
			sys.stdout.write('{0}\t1\n'.format(word))
```

## Create File reducer.py in /mnt
```bash
#!usr/bin/env python

from operator import itemgetter
import sys

if __name__ == '__main__':
	curkey = None
	total = 0
	for line in sys.stdin:
		key, val = line.split('\t', 1)
		val = int(val)

		if key == curkey:
			total += val
		else:
			if curkey is not None:
				sys.stdout.write('{0}\t{1}\n'.format(curkey, total))
			curkey = key
			total = val

	sys.stdout.write('{0}\t{1}\n'.format(curkey, total))
```

## Hadoop Count
```bash
$ hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar -input /user/cloudera/test.txt -output /user/cloudera/wc -mapper mapper.py -reducer reducer.py -file mapper.py -file reducer.py
```

* Hive 
```bash
$ hive -e 'show database'
$ hive -f exec.hql
$ hive -h
```

## Hive Command
* Hive Start
```bash
$ hive
```

* Hive Stop
```bash
hive> exit ;
```

* Hive Create Database
```bash
hive> create database [database_name] ;
```

* Hive Show Database
```bash
hive> show databases ;
```

* Hive Use Database
```bash
hive> use [database_name] ;
```

* Hive Create Table
```bash
hive> create table [table_name] ([column_name] [type], ...) row format delimited fields terminated by '\t' ;
```

* Hive Drop Table
```bash
hive> drop table [table_name] ;
```

* Hive Create Users Table
```bash
$ wget http://files.grouplens.org/datasets/movielens/ml-100k.zip
$ unzip ml-100k.zip
$ cd ml-100k
$ hadoop fs -mkdir /user/cloudera/movielens
$ hadoop fs -put u.user /user/cloudera/movielens
$ hadoop fs -ls /user/cloudera/movielens
hive> create table users ( user_id int, age int, gender string, occupation string, zipcode string ) row format delimited fields terminated by '|' stored as textfile ;
hive> show tables ;
hive> describe users ;
hive> load data inpath '/user/cloudera/movielens/u.user' overwrite into table users ;
hive> select zipcode, count(1) as count, avg(age) as age from users group by zipcode order by count desc ;
```

## Hive Create Weblogtest Table
```bash
$ wget https://s3.amazonaws.com/imcbucket/data/nasa.dat
$ hadoop fs -mkdir /user/cloudera/weblog
$ hadoop fs -put nasa.dat /user/cloudera/weblog
$ hadoop fs -ls /user/cloudera/weblog
hive> create table weblogtest (host string, time string, method string, object string, replycode string, size string) row format serde 'org.apache.hadoop.hive.serde2.RegexSerDe' with serdeproperties ("input.regex" = "([^\\s]+) - - \\[(.+)\\] \"([^\\s]+) (/[^\\s]*) HTTP/[^\\s]+\" ([^\\s]+) ([0-9]+)" ) stored as textfile ;
hive> describe weblogtest ;
hive> load data inpath '/user/cloudera/weblog/nasa.dat' overwrite into table weblogtest ;
hive> select count(1) from weblogtest ;
hive> select count(1) from weblogtest group by object order by count(1) as count from desc limit 10 ;
hive> select month, count(1) as count from ( select split(time,'/')[1] as month from weblogtest ) group by month order by count desc ; )
```

## Error Hive
```bash
FAILED: Execution Error, return code 1 from org.apache.hadoop.hive.ql.exec.DDLTask. java.util.regex.PatternSyntaxException: Unclosed character class near index 110
([^]*) ([^]*) ([^]*) (-|\[^\]*\]) ([^ "]*|"[^"]*") (-|[0-9]*) (-|[0-9]*)(?: ([^ "]*|"[^"]*") ([^ "]*|"[^"]*"))?
```

## Error Add jar File
```bash
hive> add jar ../build/contrib/hive_contrib.jar ;
../build/contrib/hive_contrib.jar does not exist
Query returned non-zero code: 1, cause: ../build/contrib/hive_contrib.jar does not exist
```

## Hbase Start Service
```bash
# service hadoop-hbase-regionserver start
# service hbase-master start
https://www.cloudera.com/documentation/enterprise/5-5-x/topics/cdh_admin_hbase_start_stop.html
```

## Hbase Command
* Hbase Start
```bash
$ hbase shell
```

* Hbase Stop
```bash
hbase> quit
```

* Hbase Create Linkshare
```bash
hbase> create 'linkshare','link'
```

* Hbase Show Linkshare
```bash
hbase> list
```

## Hbase Lab
* Create Table
```bash
hbase> create 'linkshare','link'
hbase> list
```

* Add Column Family
```bash
hbase> disable 'linkshare'
hbase> alter 'linkshare','statistics'
hbase> enable 'linkshare'
hbase> describe 'linkshare'
```

* Insert Data
```bash
hbase> put 'linkshare', 'org.hbase.www', 'link:title', 'Apache Hbase'
hbsae> put 'linkshare', 'org.hadoop.www', 'link:title', 'Apache Hadoop'
hbase> put 'linkshare', 'org.hive.www', 'link:title', 'Apache Hive'
```

* Incremental Column
```bash
hbase> incr 'linkshare', 'org.hbase.www', 'statistics:share', 1
hbase> incr 'linkshare', 'org.hbase.www', 'statistics:share', 2
```

* Get counter
```bash
hbase> get_counter 'linkshare', 'org.hbase.www', 'statistics:share'
```

* Get Row
```bash
hbase> get 'linkshare', 'org.hbase.www', 'link:title'
hbase> get 'linkshare', 'org.hbase.www', 'link:title', 'statistics:share'
```

* Change Max Number Column
```bash
hbase> alter 'linkshare', { name => 'link:title', version => 4 }
hbsae> put 'linkshare', 'org.test.www', 'link:title', 'Apache Test1'
hbsae> put 'linkshare', 'org.test.www', 'link:title', 'Apache Test2'
hbsae> get 'linkshare', 'org.test.www', { column => 'link:title', version => 2 }
```

* Scan Table
```bash
hbase> scan 'linkshare'
hbase> scan 'linkshare', { COLUMN => 'link:title', STARTROW => 'org.hbase.www' }
hbase> scan 'linkshare', { COLUMN => 'link:title', STARTROW => 'org.hadoop.www', ENDROW => 'org.hive.www' }
```

* Filter Scan Table
```bash
hbase> scan 'linkshare', { COLUMN => 'link:title', FILTER => "ValueFilter ( <=, 'binary:Apache Hbase' )" }
hbase> scan 'linkshare', { COLUMN => 'link:title', FILTER => "ValueFilter ( >, 'binary:Apache Hbase' )" }
```

* Delete Cell
```bash
hbase> delete 'linkshare', 'org.hbase.www', 'link:title'
```

* Update Cell
```bash
hbase> put 'linkshare', 'org.hbase.www', 'link:title', 'new value'
hbase> scan 'linkshare'
```

* Delete Table
```bash
hbase> create 'test', 'cf'
hbase> list
hbase> disable 'test'
hbase> drop 'test'
hbase> list
```

## Ambari Server
* Get Repo
```bash
$ wget -nv http://public-repo-1.hortonworks.com/ambari/centos7/2.x/updates/2.2.2.0/ambari.repo -O /etc/yum.repos.d/ambari.repo
```
* Show Repo
```bash
yum repolist
```

* Install
```bash
# yum install ambari-server
```

* Setup
```bash
# ambari-server setup
```

* SSH Key
```bash
# ssh-keygen cd home/damstream/.ssh cat id_rsa.pub > authorized_keys chmod 700 ~/.ssh chmod 600 ~/.ssh/authorized_keys
```

* Start Service
```bash
# service postgresql start
# service ambari-server start
```

* Error
```bash
Native memory allocation (mmap) failed to map 402653184 bytes for committing reserved memory
```

* Fix
```bash
# sysctl -w vm.max_map_count=262144
```

* Port
```bash
Ambari Server : 8080 http  (Web Interface & REST API)
Ambari Server : 8440 https (Handshake Port)
Ambari Server : 8441 https (Heartbeat Port)
```

## MySQL
* Create Database
```bash
# mysql -uroot -pcloudera
mysql> create database energydata ;
mysql> use energydata ;
mysql> create table avgprice_by_state (
	year INT NOT NULL,
	state VARCHAR(5) NOT NULL,
	sector VARCHAR(255),
	residential DECIMAL(10,2),
	industrial DECIMAL(10,2),
	transportation DECIMAL(10,2),
	other DECIMAL(10,2),
	total DECIMAL(10,2)
) ;
mysql> quit ;
```

* MySQL Import
```bash
# cd /mnt
# wget https://github.com/bbengfort/hadoop-fundamentals/raw/master/data/avgprice_kwh_state.zip
# unzip avgprice_kwh_state.zip
# mysql -h localhost -uroot -pcloudera --local-infile=1
mysql> use energydata ;
mysql> load data local infile '/mnt/avgprice_kwh_state.csv' into table avgprice_by_state fields terminated by ',' lines terminated by '\n' ignore 1 lines ;
mysql> quit ;
```

* Sqoop Import
```bash
# sqoop import --connect jdbc:mysql://localhost:3306/energydata --username root --password cloudera --table avgprice_by_state --target-dir /user/cloudera/energydata -m 1
# hadoop fs -cat /user/cloudera/energydata/part-m-00000
```

* Hive Import
```bash
# hadoop fs -rm -r /user/root/avgprice_by_state
# sqoop import --connect jdbc:mysql://localhost:3306/energydata --username root --password cloudera --table avgprice_by_state --hive-table avgprice --hive-import -m 1
# hive
hive> select * from avgprice ;
```

* Hbase Import
```bash
# mysql -uroot -pcloudera
mysql> create database country_db ;
mysql> use country_db ;
mysql> create table country_tbl (
	id int not null,
	country varchar(50),
	primary key (id)
) ;
mysql> insert into country_tbl values (1, 'USA') ;
mysql> insert into country_tbl values (2, 'CANADA') ;
mysql> insert into country_tbl values (3, 'JAPAN') ;
mysql> insert into country_tbl values (4, 'ENGLAND') ;
mysql> insert into country_tbl values (5, 'THAILAND') ;
mysql> select * from country_tbl ;
mysql> quit ;
```

* Sqoop Import
```bash
# sqoop import --connect jdbc:mysql://localhost:3306/country_db --username root --password cloudera --table country_tbl --hbase-table country --column-family country-cf --hbase-row-key id --hbase-create-table -m 1
# hbase shell
hbase> scan 'country'
```

* Ingestion Product Impression Data
```bash
# cd /mnt
# wget https://raw.githubusercontent.com/bbengfort/hadoop-fundamentals/master/flume/setup.sh
```

* Edit setup.sh
```bash
#!/bin/bash
hadoop fs -mkdir -p /user/cloudera/impressions/
hadoop fs -chmod 1777 /user/cloudera/impressions/

mkdir /tmp/impressions
chmod 777 /tmp/impressions
mkdir /tmp/flume
chmod 1777 /tmp/flume
```

* Run setup.sh
```bash
# sh setup.sh
```

* Download Python
```bash
# cd /mnt
# wget https://raw.githubusercontent.com/bbengfort/hadoop-fundamentals/master/flume/impression_tracker.py
```

* Edit impression_tracker.py
```bash
#!/usr/bin/env python
```

* Change Permission impression_tracker.py
```bash
# chmod +x impression_tracker.py
```

* Download Examples Configuration Files
```bash
# cd /mnt
# wget https://raw.githubusercontent.com/bbengfort/hadoop-fundamentals/master/flume/client.conf
# wget https://raw.githubusercontent.com/bbengfort/hadoop-fundamentals/master/flume/collector.conf
```

* Running
```bash
# flume-ng agent --name collector --conf . --conf-file ./collector.conf
# flume-ng agent --name client --conf . --conf-file ./client.conf
# hadoop fs -ls /user/cloudera/impressions
# hadoop fs -cat /user/cloudera/impressions
```

----------------------------------------------------------------------



## Credit
http://www.cs.carleton.edu/faculty/dmusican/cs348/hadoop/hadoopLab.html
https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-common/FileSystemShell.html
https://www.cloudera.com/developers/cloudera-labs.html
https://www.cloudera.com/documentation.html

https://www.slideshare.net/justiceform/manage-hadoop-cluster-with-ambari
https://github.com/ekhtiar/DamStream/wiki/Installing-Ambari-on-Centos-7
https://cwiki.apache.org/confluence/display/AMBARI/Installation+Guide+for+Ambari+2.6.1

Tool
https://streamsets.com/products/sdc
