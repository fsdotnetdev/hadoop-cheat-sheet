# Table of Content
* Big Data
    - Definition
    - Characteristic
    - What is Data
    - Data Type
    - Data Product
    - Data Engineer vs Data Scientist
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
เราเก็บข้อมูลไปทำไม ในสมัยก่อนเราจะนำข้อมูลที่ได้ ไปเข้าระบบ Decision Support System แต่ในปัจจุบันเราจะนำไปเข้าระบบ Digital Nervous System โดยใช้องค์ประกอบของ act, sense, interpret และ decide

#### Data Type
ข้อมูลจะถูกแบ่งออกเป็น 3 ประเภท
* Structure
ข้อมูลโครงสร้าง เช่น Traditional Database เก็บข้อมูลเป็นตารางที่ประกอบไปด้วย Field Record

* Semi-structure
ข้อมูลกึ่งโครงสร้าง เช่น XML (Entensible Markup Language)
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
HDFS (Hadoop Distributed File System) เป็นระบบจัดเก็บไฟล์ของ Hadoop ถูกพัฒนามาจาก GFS (Google File System) ซึ่งสามารถจัดเก็บข้อมูลแบบกระจาย Distribution ได้ เพื่อช่วยในเรื่องของการทำ Replication จะมี Concept คล้ายกับการทำ RAID ของ Storage โดยมี Name Node ทำหน้าที่เหมือนเป็น Data Table ของข้อมูล และ Data Node ที่ใช้ในการเก็บข้อมูลเป็น Data Block

#### NameNode
จัดการชื่อไฟล์ในระบบ HDFS จะเก็บข้อมูล Metadata ของ File และ Directory ในรูปแบบ Binaries Tree โดยใช้การเปรียบเทียบค่ากับ Root ถ้าน้อยกว่าไปทางซ้าย มากกว่าไปทางขวา ข้อมูลจะถูกเก็บไว้ใน Disk 2 ไฟล์

#### DataNode
เป็นโหนดที่ใช้ทำงานในระบบ HDFS หรือเรียกว่า WorkerNode

## YARN
YARN (Yet Another Resource Negotiator) ถูกเพิ่มเข้ามาในเวอร์ชั่น 2.0 เพื่อใช้ในการจัดการ Resource แบบ Real Time เอามาต่อรองกันตัวไหนใช้ได้ ตัวไหนใช้ไม่ได้ มันจะวิ่งไปหาตัวอื่น เพื่อให้สามารถทำการ Processing ต่อไปได้

## MapReduce
MapReduce เป็นเครื่องมือที่ช่วยในการประมวลผล เวลาเราทำ Cluster จะมีหลาย Compute ช่วยกันประมวลผล ซึ่งจะช่วยป้องกันในเรื่องของ Fault Tolerant หรือทนต่อความเสียหายของระบบ เพราะฉะนั้น MapReduce จึงเป็น Computation Framework ที่ถูกออกแบบมาเพื่อให้สามารถทำงานข้าม Cluster รูปแบบการทำงานจะเป็น Fuctional Programming แบ่งการทำงานออกเป็นหลาย ๆ Task ซึ่งเป็นอิสระต่อกันในการประมวลผล

![](/Images/MapReduce.png)

* Working
การทำงานจะแบ่งออกเป็น Map + Reduce ตามชื่อของมัน โดยการ Map จะเป็นการนำ Input มาแปลงให้อยู่ในรูป Key / Value แล้วทำการจัดกลุ่ม Shuffle เป็นการนำ Value ที่มี Key เหมือนกันมารวมไว้ด้วยกัน หลังจากนั้นจึงทำการ Reduce เพื่อรวม Value ทั้งหมดของแต่ละ Key ดังนั้น Output ที่ได้จะเป็นการทำ Group และ Sort ให้โดย Default

http://stevekrenzel.com/finding-friends-with-mapreduce

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

## Credit
* [Big Data 101](https://cognitiveclass.ai/courses/what-is-big-data/)
* [Hadoop 101](https://cognitiveclass.ai/courses/introduction-to-hadoop/)
* [Big Data Thai MOOC](https://thaimooc.org/courses/course-v1:STOU-MOOC+stou005+2017_T2/info)
* [Big Data Udemy](https://www.udemy.com/big-data-and-hadoop-essentials-free-tutorial/learn/v4/questions/3713846)
* [Use Case](https://hortonworks.com/solutions/data-ingestion/)
* [HDFS](https://www.datadoghq.com/blog/hadoop-architecture-overview/)
* [Version](https://www.journaldev.com/8806/differences-between-hadoop1-and-hadoop2)
* [New](https://data-flair.training/blogs/hadoop-2-x-vs-hadoop-3-x-comparison/)
* [Parallel Processing](http://slideplayer.com/slide/6502632/)
* [Grid vs Cluster](http://slideplayer.com/slide/3638/)
* [In-Memory](http://gridgain.blogspot.com/2015/02/emergence-of-in-memory-data-fabric.html)
* [JBoss Data Grid](https://developers.redhat.com/blog/2017/02/20/unlock-your-red-hat-jboss-data-grid-data-with-red-hat-jboss-data-virtualization/)

https://www.gridgain.com/resources/blog/gridgain-hadoop-differences-synergies

https://courses.cognitiveclass.ai/dashboard
https://medium.com/swlh/what-is-big-data-af72e4f5771f
https://medium.com/@Guru99/free-hadoop-tutorial-924a8ac74f86
