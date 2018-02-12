# Bash Script
Bash Script this automatic run install
```bash

```

# Table of Content
#### Head
* 

# Hadoop.sh File
sudo su -
apt-get update

## install docker ubuntu 14.04 ++
apt-get install docker.io

## pull image from docker hub
docker pull cloudera/quickstart:latest

## docker show image
docker images -a

## docker remove image
# docker rmi [image_name]

## docker run container
docker run -v /root:/mnt --hostname=quickstart.cloudera --privileged=true -t -i -p 9092:9092 -p 2181:2181 -p 11122:11122 cloudera/quickstart /usr/bin/docker-quickstart

## docker show container
# docker ps
# docker ps -a

## docker stop container
# docker stop [container_id]

## docker restart container
# docker restart [container_id]

## docker remove container
# docker rm [container_id]

## docker exec container
# docker exec -it [container_id] bash

## hadoop
yum update -y
yum install vim -y
yum install wget -y
cd /mnt
vi test.txt
:wq
hadoop fs -help
hadoop fs -put test.txt /user/cloudera
hadoop fs -ls /user/cloudera
hadoop fs -cat /user/cloudera/test.txt
hadoop fs -get /user/cloudera/test.txt test1.txt
hadoop fs -mkdir -p /user/cloudera/temp
hadoop fs -cp /user/cloudera/test.txt /user/cloudera/temp/test.txt
hadoop fs -rm /user/cloudera/temp/test.txt
hadoop fs -rmdir /user/cloudera/temp
hadoop fs -ls /user/cloudera

## Lifecycle
docker create
docker rename
docker run

## mapper.py
======================
#!/usr/bin/env python

from operator import itemgetter
import sys

if __name__ == '__main__':
	for line in sys.stdin:
		for word in line.split():
			sys.stdout.write('{0}\t1\n'.format(word))
======================

## reducer.py
======================
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
======================

## hadoop count
hadoop jar /usr/lib/hadoop-mapreduce/hadoop-streaming.jar -input /user/cloudera/test.txt -output /user/cloudera/wc -mapper mapper.py -reducer reducer.py -file mapper.py -file reducer.py

## hive start
hive

## hive stop
exit

## hive
hive -e 'show database'
hive -f exec.hql
hive -h

create database [database_name] ;
show databases ;
use [database_name] ;
create table [table_name] ([column_name] [type], ...) row format delimited fields terminated by '\t' ;
drop table [table_name] ;

wget http://files.grouplens.org/datasets/movielens/ml-100k.zip
unzip ml-100k.zip
cd ml-100k
hadoop fs -mkdir /user/cloudera/movielens
hadoop fs -put u.user /user/cloudera/movielens
hive
create table users ( user_id int, age int, gender string, occupation string, zipcode string ) row format delimited fields terminated by '|' stored as textfile ;
show tables ;
describe users ;
load data inpath '/user/cloudera/movielens/u.user' overwrite into table users ;
select zipcode, count(1) as count, avg(age) as age from users group by zipcode order by count desc ;
create table weblongtest ( host string)

## Error Hive
```bash
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

## Credit
http://www.cs.carleton.edu/faculty/dmusican/cs348/hadoop/hadoopLab.html
https://hadoop.apache.org/docs/current/hadoop-project-dist/hadoop-common/FileSystemShell.html
https://www.cloudera.com/developers/cloudera-labs.html
https://www.cloudera.com/documentation.html
