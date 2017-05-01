# scala-eclipse-spark-hortonwork-project-setup

## Tutorial 101: How to setup &amp; run a Spark Example on Hortonwork 2.5 Sandbox and build the project using Scala IDE for Eclipse.

The [Apache Spark Examples] (http://spark.apache.org/examples.html) give a quick overview of the Spark API. They are a hidden treasure for someone seeking to learn about Apache Spark and its various components. You can download the whole set of examples from Spark’s Github Repository.

Lately, I have started building some of these sample mini applications in order to understand Spark’s capabilities and API command even better. Although the Maven approach works, I decided to try using the community edition of Scala IDE for Eclipse release version 4.5. to build the examples. The 64 bit package includes ( Eclipse Neon 4.6.1, Scala IDE 4.5.0, and Scala 2.11.8 & Scala 2.10.6). Installation is straight forward but one thing to keep in mind that you shall be using JDK 8 and when the you unzip the file downloaded you only need to create a shortcut to “eclipse.exe” to run the IDE.

For Hadoop & Spark I downloaded the 64 bits Hortonworks Sandbox v2.5 running on VirtualBox. Installation of the sandbox was straight forward on my Windows 7 laptop running Dell E6540 with Intel i&4810 Quad CPU 2.8 GHz and 16 GB RAM. One thing to keep in mind is to configure the sandbox to run with 11.5 GB Memory and 3 processors. The remaining one CPU and 4.5 GB memory would be enough to run your IDE and browser if you are not running anything else. To conncet to the sandbox via SSH I am using Putty.

## Contents:
- Download Apache Spark & Sample Examples
- Create a New Project in Eclipse IDE for Scala
- Set Libraries Paths & Generate Jar
- Coping Jar & input data to sandbox
- Running the sample application & examining the results

## Download Apache Spark and Sample Examples

If you don’t have it already, you need to Download Apache Spark and select the right version that works with Hortonworks v2.5 Sandbox. Here is a direct link to the correct release: Spark v 2.1.0 Dec 28, 2016 Prebuilt for Hadoop v 2.7 and later: spark-2.1.0-bin-hadoop2.7.tgz

Once downloaded and unzipped (I choose "c:\hd-proj\spark210" on my laptop) you can find the sample Examples as follows:  c:\hd-proj\spark210\examples\src\main\scala\org\apache\spark\examples. You can also find the Apache Spark Jars pre-built under the directory: c:\hd-proj\spark210\jars. These jar files will be used in Eclipse to build our mini applications.

## Create a New Project in Eclipse IDE for Scala
    First you need to open the IDE and create a new Project which we shall name it "page-rank" by selecting: File -> New -> Scala Project -> Project name: page-rank then click Finish. See image below.
    Then select the page-rank project and select: File -> New -> Package -> Name: com.scala-proj then click Finish.
    Then select the page-rank project and select: File -> New -> Scala Object -> Name: SparkPageRank then click Finish.
    Now delete the Object class that was created by the IDE.
    From the Examples directory copy and paste the whole content of SparkPageRank.scala code into your newly created Object.
    Then delete the line "package org.apache.spark.examples" because you already created your own package com.scala-proj.



![New Project](/images/img-1.jpg?raw=true "New Project")
