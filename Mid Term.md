# Table of Content
* Big Data
    - Definition
    - Characteristic
* Hadoop
* Data Engineer vs Data Scientist

## Big Data
#### Definition
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

#### Platform

#### Data
เราเก็บข้อมูลไปทำไม ในสมัยก่อนเราจะนำข้อมูลที่ได้ ไปเข้าระบบ Decision Support System แต่ในปัจจุบันเราจะนำไปเข้าระบบ Digital Nervous System โดยใช้องค์ประกอบของ act, sense, interpret และ decide

#### Data Type
ข้อมูลจะถูกแบ่งออกเป็น 3 ประเภท
* Structure
ข้อมูลโครงสร้าง เช่น Traditional Database เก็บข้อมูลเป็นตารางที่ประกอบไปด้วย Field Record

* Semi-structure
ข้อมูลกึ่งโครงสร้าง เช่น XML (Entensible Markup Language)

* Unstructure
ข้อมูลไร้โครงสร้าง เช่น Facebook, Youtube

## Hadoop
#### Definition
Hadoop เป็น Framework ที่ใช้ในการทำ parallel processing and storage

#### Hadoop Vendors
* Apache
เป็น Opensource โดย Ecosystem ทั้งหมดจะต้องติดตั้งเพิ่มเติมในภายหลัง

* Cloudera
เป็น Ecosystem ที่สำคัญเพราะ ได้รวมสิ่งที่จำเป็นต้องใช้มาให้แล้ว

* MapR
เขียนด้วยภาษา C และสามารถ Integrate กับ Hadoop Ecosystem

* Hortonworks
Support .NET Framework

* EMC2

## HDFS
HDFS (Hadoop File System) เป็นระบบจัดเก็บไฟล์ของ Hadoop ซึ่งสามารถจัดเก็บข้อมูลแบบกระจาย Distribution ได้ เพื่อช่วยในเรื่องของการทำ Replication

* ELO (Expect Learning Outcome)
- CLI
- HTTP Interface
- API

## MapReduce
MapReduce เป็นเครื่องมือที่ช่วยในการประมวลผล เวลาเราทำ Cluster จะมีหลาย Compute ช่วยกันประมวลผล ซึ่งจะช่วยป้องกันในเรื่องของ Fault Tolerant หรือทนต่อความเสียหายของระบบ เพราะฉะนั้น MapReduce จึงเป็น Computation Framework ที่ถูกออกแบบมาเพื่อให้สามารถทำงานข้าม Cluster รูปแบบการทำงานจะเป็น Fuctional Programming แบ่งการทำงานออกเป็นหลาย ๆ Task ซึ่งเป็นอิสระต่อกันในการประมวลผล

* Working
การทำงานจะแบ่งออกเป็น Map + Reduce ตามชื่อของมัน โดยการ Map จะเป็นการนำ Input มาแปลงให้อยู่ในรูป Key / Value แล้วทำการจัดกลุ่ม Shuffle เป็นการนำ Value ที่มี Key เหมือนกันมารวมไว้ด้วยกัน หลังจากนั้นจึงทำการ Reduce เพื่อรวม Value ทั้งหมดของแต่ละ Key ดังนั้น Output ที่ได้จะเป็นการทำ Group และ Sort ให้โดย Default

http://stevekrenzel.com/finding-friends-with-mapreduce

## Hive

## Hbase

## Credit
* [Big Data 101](https://cognitiveclass.ai/courses/what-is-big-data/)
* [Hadoop 101](https://cognitiveclass.ai/courses/introduction-to-hadoop/)
* [Big Data Thai MOOC](https://thaimooc.org/courses/course-v1:STOU-MOOC+stou005+2017_T2/info)
* [Big Data Udemy](https://www.udemy.com/big-data-and-hadoop-essentials-free-tutorial/learn/v4/questions/3713846)

https://courses.cognitiveclass.ai/dashboard
