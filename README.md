## Tutorial 101: How to build &amp; run Spark example: SparkPageRank.scala 
### Building project using Scala IDE for Eclipse and running on Hortonwork 2.5 Sandbox

The [Apache Spark Examples](http://spark.apache.org/examples.html) give a quick overview of the Spark API. They are a hidden treasure for someone seeking to learn about Apache Spark and its various components. You can download the whole set of examples from [Spark’s Github Repository](https://github.com/apache/spark/tree/master/examples/src/main/scala/org/apache/spark/examples). We shall be using SparkPageRank.scala from the example set in this tutorial

Lately, I have started building some of these sample mini applications in order to understand Spark’s capabilities and API even better. Although the Maven approach works, I decided to try using the community edition of [Scala IDE for Eclipse](http://scala-ide.org/download/sdk.html) release version 4.5. to build the examples. The 64 bit package includes (Eclipse Neon 4.6.1, Scala IDE 4.5.0, and Scala 2.11.8 & Scala 2.10.6). Installation is straight forward but one thing to keep in mind that when you unzip the Eclipse downloaded eclipse file you only need to create a shortcut to “eclipse.exe” to run the IDE. Scala 2.11 require JDK 8. 

For Hadoop & Spark I downloaded the 64 bits [Hortonworks Sandbox v2.5](https://hortonworks.com/downloads/?_bt=104841503598&_bk=hortonworks%20sandbox&_bm=e&_bn=g&gclid=CNH105LOu9MCFcK4wAodSZMFxw#) running on VirtualBox. Installation of the sandbox was straight forward on my Windows 7 laptop running Dell E6540 with Intel i&4810 Quad CPU 2.8 GHz and 16 GB RAM. One thing to keep in mind is to configure the sandbox to run with 11.5 GB Memory and 3 processors. The remaining one CPU and 4.5 GB memory would be enough to run your IDE and browser if you are not running anything else. To conncet to the sandbox via SSH I am using Putty.

## Contents:
- Download Apache Spark & Sample Examples
- Create a New Project in Eclipse IDE for Scala
- Set Libraries Paths & Generate Jar
- Copy Jar & input data to sandbox
- Run SparkPageRank Scala application & examin the results

## Download Apache Spark and Sample Examples

If you don’t have it already, you need to download [Apache Spark 2.1.0](http://spark.apache.org/downloads.html) and select the right version that works with Hortonworks v2.5 Sandbox. Here is a direct link to the correct release: Spark v 2.1.0 Dec 28, 2016 Prebuilt for Hadoop v 2.7 and later: spark-2.1.0-bin-hadoop2.7.tgz

Once downloaded and unzipped (I choose "c:\hd-proj\spark210" as destination directory) you can find the **Spark Examples** in:  c:\hd-proj\spark210\examples\src\main\scala\org\apache\spark\examples. You can also find the pre-built **Spark Jars** under the directory: c:\hd-proj\spark210\jars. These jar files need to be included in the Libraries Path of our project in Eclipse and they will be used to build our mini applications as we shall see in this tutorial.

## Create a New Project in Eclipse IDE for Scala
We are going to be using the sample SparkPageRank.scala example that comes with Apache Spark. Here are the steps to create your project.

 1- You need to open the IDE and create a new Project (see image below) which we shall name it "page-rank" by selecting: File -> New -> Scala Project -> Project name: page-rank then click Finish. See image below.
 
 2- Then select the page-rank project and select: File -> New -> Package -> Name: com.scalaproj then click Finish.
 
 3- Then select the page-rank project and select: File -> New -> Scala Object -> Name: SparkPageRank then click Finish.
 
 4- Now delete the Object class that was created by the IDE.
 
 5- From the Spark Examples directory copy and paste the whole content of SparkPageRank.scala code into your newly created Object.
 
 6- Then delete the line "package org.apache.spark.examples" because you already created your own package com.scala-proj.

![New Project](/images/img-1.jpg?raw=true "New Project")

## Set Libraries Paths & Generate Jar

Now you are ready to setup your libraries and compile/build your project:

1- You need to select the page-rank Project and then go to main menu: Project-> Properties and you will get to the Properties Window for the page-rank.

2- Delete the "Scala Library Container [2.11.8] which is shown in the diagram below.

![Setup Libraries Path](/images/img-2.jpg?raw=true "Setup Libraries Path")

 3- Press the "Add External JARS" button to the right and go to where you downloaded and unzipped Apache Spark (in my case "c:\hd-proj\spark210\jars" and select all the jars in the directory and press "Apply" (see image below).
 
 4- To compile/build your project go to Project-Build Project -> and the SparkPageRank program will be compiled by Eclipse and the error messages will be displayed in the window. 
 
![Setup Spark Libraries Path](/images/img-3.jpg?raw=true "Setup Spark Libraries Path")

Once the project compiles you are ready to generate the page-rank.jar for the project. Here are the steps needed:

 1- Open select the project then by selecting: File -> Export you go to the JAR Export screen (see image below).
 
 2- Click on the check box near the project name "page-rank".
 
 3- Click on the check box for two of the Export options as shown in the image below
 
 4- Enter the Jar destination directory. I usually create a "target" directory within the the project directory.
 
 5- Press the "Finish" button and the page-rank.jar is generated by Eclipse in the ... \page-rank\targe directory.
 
 ## Copy Jar & input data files to Hortonwork Sandbox
 
 1- Open Ambari and select File View which will take you to the main HDFS directory.
 
 2- Create two directories "jars" and "input" in the main directory.
 
 3- Upload the page-rank.jar file and the data file urldata.txt into hdfs via Ambari.
 
 4- Connect via Putty to your Sandbox
 
 5- Create the directory & subdirectory ~/testing/jars on the local Linux system which is running the sandbox.
 
 6- Copy the page-rank.jar file from HDFS to your local Linux directory using the command:
      $ hdfs dfs -get /jars/page-rank.jar ~/testing/jars 
 
 
 ## Run SparkPageRank Scala application & examining the results
 
 Now you are ready to run the application using your Puttly terminal connection.
 
 1- Change to the directory where all Spark files are located on Hortonwork Sandbox
 cd /etc/current/Spark2-client
 
 2- Run the following command
 
 3- You can check the results 
 
 
