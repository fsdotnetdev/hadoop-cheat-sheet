# Table of Content
* Big Data
    - Definition
    - Characteristic
    - What is Data
    - Data Type
    - Data Product
    - Data Science
* Hadoop
    - Definition
    - Hadoop Version
    - Hadoop Ecosystem
    - Vendors
* HDFS
* YARN
* MapReduce
* Pig
* Hive
* HBase
* Sqoop
* Oozie

## Big Data
Big Data คือ กลุ่มของข้อมูล หรือ Data Set ที่มีขนาดใหญ่และซับซ้อน ที่ไม่สามารถประมวลผลและการจัดเก็บข้อมูลได้ด้วย Traditional Data Management

#### Characteristic
ลักษณะของ Big Data จะประกอบไปด้วย 5V

![](/Images/5V.png)

* Volume
สามารถรองรับการขยายตัวของข้อมูลที่มีขนาดใหญ่ ซึ่งจะมีขนาดตั้งแต่ Exabyte, Zettabyte, Yottabyte ขึ้นไป

* Velocity
สามารถทำงานได้อย่างรวดเร็วและต่อเนื่อง ในเวลาที่มี Process เข้ามาจำนวนมากได้แบบ Real-Time หรือ Streaming

* Variety
สามารถรองรับข้อมูลได้หลากหลายรูปแบบ ทั้ง Structure, Unstructure, Text, Multimedia รวมถึงสามารถรับข้อมูลได้จากหลายอุปกรณ์ IoT

* Veracity
สามารถเก็บข้อมูลได้อย่างถูกต้องครบถ้วน ไม่สูญหายหรือรั่วไหลออกไป และไม่เกิดความซ้ำซ้อนของข้อมูล CIA

* Value
เป็นการนำข้อมูลของ Big Data มาทำให้เกิดมูลค่าหรือมีกำไร

#### What is Data
เราเก็บข้อมูลไปทำไม ในสมัยก่อนเราจะนำข้อมูลที่ได้ ไปเข้าระบบ Decision Support System แต่ในปัจจุบันเราจะนำไปเข้าระบบ Digital Nervous System โดยใช้องค์ประกอบของ act, sense, interpret และ decide ปัจจุบันข้อมูลที่มีขนาดใหญ่ที่สุดได้แก่ Google Facebook Youtube ซึ่งมีขนาด PB ถึง EB มีการคาดการณ์ว่าในปี 2020 จะมีข้อมูลถึง ZB (Zettabyte)

#### Data Type
ข้อมูลจะถูกแบ่งออกเป็น 3 ประเภท
* Structure
ข้อมูลโครงสร้าง เช่น Traditional Database เก็บข้อมูลเป็นตารางที่ประกอบไปด้วย Field Record

* Semi-structure
ข้อมูลกึ่งโครงสร้าง เช่น XML (Entensible Markup Language) และ JSON
```bash
<rec><name>Prashant Rao</name><sex>Male</sex><age>35</age></rec>
<rec><name>Seema R.</name><sex>Female</sex><age>41</age></rec>
<rec><name>Satish Mane</name><sex>Male</sex><age>29</age></rec>
<rec><name>Subrato Roy</name><sex>Male</sex><age>26</age></rec>
<rec><name>Jeremiah J.</name><sex>Male</sex><age>35</age></rec>
```

* Unstructure
ข้อมูลไร้โครงสร้าง เช่น Facebook, Youtube

## Data Product
หากข้อมูลในเชิงการเขียนโปรแกรม เปรียบเสมือนเงินตราที่มีมูลค่า Data Product คือการรวมกันระหว่างข้อมูลและกระบวนการทางสถิติ โดยใช้การอ้างอิงหรือคาดการณ์

## Data Science
องค์ประกอบของ Data Science โดยหลักแล้วจะต้องประกอบไปด้วย Skill ทางด้าน BI (Business Intelligence) จะเป็นการเจาะลึกลงไปในธุรกิจนั้น Business Insight ถึงโครงสร้างขององค์กร เป้าหมาย วัฒนธรรม กลุ่มลูกค้า สินทรัพย์ขององค์กร รวมถึงรายงานทางบัญชี ตั้งแต่อดีตจนถึงปัจจุบัน มาทำเป็น Report ซึ่งจะใช้โปรแกรมยอดนิยมอย่าง PowerBI และ Skill ทางด้าน Predictive Analytic เป็นการวิเคราะห์ทำนายเหตุการณ์ในอนาคต โดยใช้แบบจำลองทางสถิติ นอกจากนั้นยังจะประกอบไปด้วย Skill ทางด้านเทคโนโลยีที่เข้ามาช่วยในการทำงานได้แก่
* Cloud Computing
* Big Data
* Machine Learning
* Data Mining
* Statistic
* IoT

#### Use Case
การประยุกต์ใช้ Big Data ในภาคธุรกิจ
* Airline
ปัญหาของสายการบินที่พบ เช่น กระเป๋าสูญหาย ผู้โดยสารหยิบกระเป๋าผิด สายการบินล่าช้า การขอเปลี่ยนเที่ยวบิน จึงได้มีการนำ Big Data มาใช้ในการจัดการเพื่อให้เป็นสายการบินแบบ Low Cost สายการบินต้นทุนต่ำ

* Hospital
ข้อมูลที่สำคัญของโรงพยาบาล คือทะเบียนประวัติการรักษาของคนไข้ ซึ่งในแต่ละสถานพยาบาลไม่ได้ทำการอัพเดทข้อมูลซึ่งกันและกัน หรือ ไม่มีแหล่งเก็บข้อมูลกลาง รวมถึงข้อมูลอื่น ๆ เช่น ข้อมูลของตัวยา ประวัติของหมอ

* Banking

## Hadoop
Hadoop เป็นซอฟต์แวร์ Open Source Framework ที่ใช้ในการทำ Parallel Processing and Storage โดยมีลักษณะการทำงานแบบ Distributed Computing ซึ่งจะแบ่งเป็น Master กับ Slave เป็นเหมือนเครื่องแม่ข่ายในการกระจายข้อมูลไปยังเครื่องลูกข่ายเพื่อช่วยกันประมวลผล Concept เดียวกับการทำงานแบบ Cluster เพื่อกระจายโหลดหรือทำ Load Balance

#### Hadoop Version
Hadoop ได้ออกเวอร์ชั่น 1.0 และ 2.0 โดยเวอร์ชั่นล่าสุด 2.0 ที่ออกมาเพื่อแก้ข้อจำกัดของเวอร์ชั่น 1.0 ทำให้สถาปัตยกรรมของ Hadoop เปลี่ยนไป

![](/Images/Hadoop-Version.png)

Version 1.0
* Master Node มีได้แค่ 1 Node ต่อ Cluster
* Slave Node มีได้ไม่เกิน 4,000 Node ต่อ Cluster
* Batch Processing เป็นการนำข้อมูลมาเก็บรวมกันแล้วนำมา Processing ทีเดียว
* ไม่รองรับการทำงานแบบ Real Time
* มีแค่ Component เดียวคือ Job Tracker จะแบ่งเป็น Component ย่อยได้แก่ Resource Manager ใช้จัดการ Resource ภายใน Cluser และ Application Manager ใช้จัดการพวก MapReduce

Version 2.0
* รองรับภาษา Java ตั้งแต่ JDK 7 ขึ้นไป
* รองรับการทำงานบน Windows Azure
* เพิ่ม YARN Component เข้ามาช่วยในการจัดการ Resource

#### Vendors
* Apache
เป็น Opensource โดย Ecosystem ทั้งหมดจะต้องติดตั้งเพิ่มเติมในภายหลัง

* Cloudera
เป็น Ecosystem ที่สำคัญเพราะ ได้รวมสิ่งที่จำเป็นต้องใช้มาให้แล้ว

* MapR
เขียนด้วยภาษา C และสามารถ Integrate กับ Hadoop Ecosystem

* Hortonworks
Support .NET Framework

* EMC2

#### Hadoop Ecosystem
Ecosystem หมายถึงระบบนิเวศ Hadoop Ecosystem จะหมายความว่าระบบย่อยต่างๆ ที่มีความสัมพันธ์กันและเกี่ยวข้อง Hadoop เปรียบเหมือนห่วงโซ่ของ Hadoop ที่เรียกว่า System Chain เพราะ Hadoop ไม่สามารถทำงานด้วยตัวมันเองเพียงอย่างเดียวได้

![](/Images/Hadoop-Ecosystem-Full.png)

## HDFS
HDFS (Hadoop Distributed File System) เป็นระบบจัดเก็บไฟล์ของ Hadoop ถูกพัฒนามาจาก GFS (Google File System) ซึ่งสามารถจัดเก็บข้อมูลแบบกระจาย Distribution ได้ เพื่อช่วยในเรื่องของการทำ Replication จะมี Concept คล้ายกับการทำ RAID ของ Storage โดยมี NameNode ทำหน้าที่เหมือนเป็น Data Table ของข้อมูล และ DataNode ที่ใช้ในการเก็บข้อมูลเป็น Data Block

#### NameNode
เป็น HDFS Component ช่วยในการจัดการชื่อไฟล์ในระบบ HDFS จะเก็บข้อมูล Metadata ของ File และ Directory เพื่อใช้ใน Mapping ข้อมูลที่ถูกเก็บเป็น Block บน DataNode ในรูปแบบ B-Tree โดยใช้การเปรียบเทียบค่ากับ Root ถ้าน้อยกว่าไปทางซ้าย มากกว่าไปทางขวา ในแต่ละ Node จะทำการระบุ Path ของ Directory และจะมีการทำ Replication ข้อมูลจะถูกเก็บไว้บน Disk โดย Default 3 ไฟล์

#### Secondary NameNode
เป็น NameNode สำรอง ตรวจสอบสถานะการทำงานของ NameNode Checkpoint ของ NameNode หาก NameNode ตายจะไม่สามารถส่งต่อไปยัง DataNode ได้

#### JournalNode
เป็นตัวตัดสินใจเลือก Active NameNode

#### DataNode
เป็น HDFS Component หรือเรียกว่า WorkerNode จะทำการรับคำสั่งจาก NameNode ในการอ่านเขียนหรือจัดเก็บข้อมูล โดยจะทำการแบ่ง File ที่ได้รับออกเป็น Block ซึ่งแต่ละ Block จะถูกเก็บอยู่ใน DataNode

#### Data Block
ในแต่ละ Block จะมีขนาด Default Size 128 MB หาก Block Size มีขนาดมากกว่า Data Size เช่นมีข้อมูลขนาด 129 MB จะถูกแบ่งออกเป็น 2 Block คือ 128 MB และ 1 MB ซึ่งตัวของ Hadoop ฉลาดพอที่จะไม่เสียพื้นที่ 127 MB

#### JobTracker
เป็น MapReduce Component ช่วยในการติดตามภาระงานและกระจายงานส่งไปยัง TaskTracker หลังจากทำการ Execute ไฟล์ โดยจะทำการตรวจสอบการทำงานของ MapReduce บน TaskTracker 

#### TaskTracker
เป็น MapReduce Component ช่วยในการติดตามการดำเนินงานหลังจากที่ได้รับจาก JobTracker หลังจากทำการ Execute ไฟล์ โดยจะรัน MapReduce อยู่บน JVM ทำการอ่าน Block จาก DataNode และส่งสถานะการทำงานเป็น Heartbeat Message ไปยัง JobTracker

![](/Images/JobTracker.png)

## YARN
YARN (Yet Another Resource Negotiator) ถูกเพิ่มเข้ามาในเวอร์ชั่น 2.0 เพื่อใช้ในการจัดการ Resource แบบ Real Time เอามาต่อรองกันตัวไหนใช้ได้ ตัวไหนใช้ไม่ได้ มันจะวิ่งไปหาตัวอื่น เพื่อให้สามารถทำการ Processing ต่อไปได้

## MapReduce
MapReduce เป็นเครื่องมือที่ช่วยในการประมวลผล เวลาเราทำ Cluster จะมีหลาย Compute ช่วยกันประมวลผล ซึ่งจะช่วยป้องกันในเรื่องของ Fault Tolerant หรือทนต่อความเสียหายของระบบ เพราะฉะนั้น MapReduce จึงเป็น Computation Framework ที่ถูกออกแบบมาเพื่อให้สามารถทำงานข้าม Cluster รูปแบบการทำงานจะเป็น Fuctional Programming แบ่งการทำงานออกเป็นหลาย ๆ Task ซึ่งเป็นอิสระต่อกันในการประมวลผล

![](/Images/MapReduce.png)

* Working
การทำงานจะแบ่งออกเป็น Map + Reduce ตามชื่อของมัน โดยการ Map จะเป็นการนำ Input มาแปลงให้อยู่ในรูป Key / Value Pair เป็นคู่ ๆ แล้วทำการจัดกลุ่ม Shuffle เป็นการนำ Value ที่มี Key เหมือนกันมารวมไว้ด้วยกันเป็น List หลังจากนั้นจึงทำการ Reduce เพื่อรวม Value ทั้งหมดของแต่ละ Key ดังนั้น Output ที่ได้จะเป็นการทำ Group และ Sort ให้โดย Default

![](/Images/MapReduce-Example.png)

## Pig
ใช้ในการเขียนภาษา Script จะมีตัวดำเนินการหรือ Operator โดยปกติจะต้องรู้โครงสร้างของภาษาในการเขียน ซึ่งจะมีลักษณะที่ยาวทำให้ไม่สะดวกในการจำ เช่น Source, Group, Filter, Print การใช้งานจะนำไปใช้ในการทำ ETL (Extract Transform Load) เป็นการดึงข้อมูลจาก Data Warehouse ซึ่งสามารถเก็บข้อมูลได้หลากหลายรูปแบบ ไปแปลงให้เป็นรูปแบบเดียวกัน แล้วนำข้อมูลที่ได้แสดงออกมาเป็น Report เพื่อนำข้อมูลไปวิเคราะห์ต่อไป ในการ Implement จะใช้ในการวิเคราะห์ Log ต่าง ๆ จะใช้คู่กับ Hive

## Hive
ใช้ในการจัดเก็บข้อมูล Data Warehouse จะใช้กับงานที่ต้องมีการเรียกข้อมูลมาแสดง โดยใช้ภาษา HIVEQL ซึ่งเหมือนกับภาษา SQL (Structure Query Language) ดึงข้อมูลด้วยการ Query ออกมาแสดง ในการ Implement จริงที่ธุรกิจที่น่าจะต้องใช้ก็พวกธนาคาร ซึ่งจะมีการเรียกข้อมูลไม่ว่าจะเป็นประวัติการทำธุรกรรม Transaction หรือการสอบถามยอดเงินต่าง ๆ ซึ่งจะมีการเรียกข้อมูลออกมาแสดงบ่อย

## HBase
ใช้ในการอ่านและเขียนข้อมูลแบบ Real Time เก็บข้อมูลแบบ Unstructure โดยจะมี Column Oriented ซึ่งจะต้องกำหนด Column Family ทุกครั้งเพื่อแก้ปัญหาของ Hive ที่มีลักษณะเหมือนฐานข้อมูล RDBMS ทั่ว ๆ ไป ที่จะต้องระบุ Schema โครงสร้างของตารางให้เรียบร้อยก่อน ดังนั้น HBase จึงเหมาะกับข้อมูลที่มี Schema ไม่แน่นอน เพื่อรองรับการเพิ่ม Column ได้ในภายหลัง คล้าย ๆ กับฐานข้อมูลจำพวก NoSQL แต่สามารถทำงานได้แบบ Distributed Computing 

## Sqoop
ใช้ในการจัดการแปลงข้อมูลจาก RDBMS ที่มีลักษณะแบบ Structure แปลงให้เป็นแบบ Unstructure เพื่อให้สามารถจัดเก็บได้ใน HDFS

## Mahount
ใช้ในการจัดการข้อมูลจำพวก Data Science นำไปวิเคราะห์และทำนายเหตุการณ์ โดยอาศัยอัลกอริธึมช่วยในการจัดการ เช่น Collaborative Filtering, Classification, Data Clustering, Cyber-Crime ในการ Implement จะใช้ในการทำนายพฤติกรรมของลูกค้า เพื่อนำเสนอขายสินค้าแล้วลูกค้าจะซื้อ เช่น Amazon ก็จะมีสินค้าแนะนำขึ้นมาให้เราเลือก, การคัดลอกวรรณกรรม งานวิจัยต่าง ๆ, การคัดกรองอีเมล, การพยากรณ์อากาศ

## Zookeeper
ใช้ในการจัดการ Application ต่าง ๆ ให้สามารถทำงานสอดคล้องกัน และช่วยลบขยะที่ไม่ใช้แล้วจากการทำ Data Replication

## Flume
move data

## Oozie
การต้ังเวลาการทำงาน Job Execution

## Run Service
ลำดับการรัน Service ต่าง ๆ บน Hadoop
1. zookeeper
2. datanode
3. journalnode
4. namenode
5. secondarynamenode
6. hadoop-httpfs
7. historyserver
8. nodemanager
9. resourcemanager
10. hbase-master
11. hive-metastore
12. hive-server2
13. sqoop
14. spark-history-server
15. regionserver
16. hue
17. statestored
18. solr
19. catalogd
20. impalad

## Configuration
* hadoop-env.sh
* core-site.xml
* hdfs.site.xml
* mapred-site.xml
* masters
* slaves
* hadoop-metrcs.properties
* log4j.properties

## Credit
* [Big Data 101](https://cognitiveclass.ai/courses/what-is-big-data/)
* [Hadoop 101](https://cognitiveclass.ai/courses/introduction-to-hadoop/)
* [Thai MOOC](https://thaimooc.org/courses/course-v1:STOU-MOOC+stou005+2017_T2/info)
* [Use Case](https://hortonworks.com/solutions/data-ingestion/)
* [HDFS](https://www.datadoghq.com/blog/hadoop-architecture-overview/)
* [Version](https://www.journaldev.com/8806/differences-between-hadoop1-and-hadoop2)
* [New](https://data-flair.training/blogs/hadoop-2-x-vs-hadoop-3-x-comparison/)
* [Parallel Processing](http://slideplayer.com/slide/6502632/)
* [Grid vs Cluster](http://slideplayer.com/slide/3638/)
* [In-Memory](http://gridgain.blogspot.com/2015/02/emergence-of-in-memory-data-fabric.html)
* [JBoss Data Grid](https://developers.redhat.com/blog/2017/02/20/unlock-your-red-hat-jboss-data-grid-data-with-red-hat-jboss-data-virtualization/)
* [Hadoop All Component](https://github.com/youngwookim/awesome-hadoop)
* [Hadoop Monitoring](https://blog.pandorafms.org/hadoop-monitoring/)
* [MapReduce Full](https://0x0fff.com/hadoop-mapreduce-comprehensive-description/)
* [HDFS Architecture](https://data-flair.training/blogs/hadoop-hdfs-architecture/)
* [DFS](https://www.cs.rutgers.edu/~pxk/417/notes/16-dfs.html)
* [Social Sentiment](https://hortonworks.com/tutorial/analyzing-social-media-and-customer-sentiment-with-apache-nifi-and-hdp-search/)
* [Hadoop.org](https://hadoop.apache.org/docs/stable/index.html)
* [Architecture](http://hadooper.blogspot.com/)

## LAB
* [IBM](https://my.imdemocloud.com/)
* [POISX Compliant System](https://en.wikipedia.org/wiki/POSIX)

During the replication process, a block of data is written to all specified DataNodes in parallel. True or false?
- False

When loading data into HDFS, data is held at the NameNode until the block is filled and then the data is sent to a DataNode. True or false?
- False


## Preruquisite
* IBM
```bash
username: root
password: password

hosts file
ip  rvm.svl.ibm.com

http://rvm.svl.ibm.com:8080/
username: admin
password: admin

https://www.cloudera.com/downloads/quickstart_vms/5-13.html
```

* Cloudera
```bash
https://www.cloudera.com/developers/get-started-with-hadoop-tutorial.html

RAM 4

username: cloudera
password: cloudera
```


https://www.wellform.cc/big-data/%E0%B8%81%E0%B8%B2%E0%B8%A3%E0%B8%95%E0%B8%B4%E0%B8%94%E0%B8%95%E0%B8%B1%E0%B9%89%E0%B8%87-hadoop-%E0%B9%81%E0%B8%9A%E0%B8%9A-step-by-step-%E0%B8%AA%E0%B8%B3%E0%B8%AB%E0%B8%A3%E0%B8%B1%E0%B8%9A/
http://www.michael-noll.com/tutorials/running-hadoop-on-ubuntu-linux-single-node-cluster/

https://www.edureka.co/blog/apache-hadoop-hdfs-architecture/
https://www.gridgain.com/resources/blog/gridgain-hadoop-differences-synergies

https://courses.cognitiveclass.ai/dashboard
https://medium.com/swlh/what-is-big-data-af72e4f5771f
https://medium.com/@Guru99/free-hadoop-tutorial-924a8ac74f86
