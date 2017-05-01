# scala-eclipse-spark-hortonwork-project-setup
Tutorial 101: How to setup &amp; run a Spark Example on Hortonwork 2.5 Sandbox and build the project using Scala IDE for Eclipse.

The Apache Spark Examples give a quick overview of the Spark API. They are a hidden treasure for someone seeking to learn about Apache Spark and its various components. You can download the whole set of examples from Spark’s Github Repository.

Lately, I have started building some of these sample mini applications in order to understand Spark’s capabilities and API command even better. Although the Maven approach works, I decided to try using the community edition of Scala IDE for Eclipse release version 4.5. to build the examples. The 64 bit package includes ( Eclipse Neon 4.6.1, Scala IDE 4.5.0, and Scala 2.11.8 & Scala 2.10.6). Installation is straight forward but one thing to keep in mind that you shall be using JDK 8 and when the you unzip the file downloaded you only need to create a shortcut to “eclipse.exe” to run the IDE.

For Hadoop & Spark I downloaded the 64 bits Hortonworks Sandbox v2.5 running on VirtualBox. Installation of the sandbox was straight forward on my Windows 7 laptop running Dell E6540 with Intel i&4810 Quad CPU 2.8 GHz and 16 GB RAM. One thing to keep in mind is to configure the sandbox to run with 11.5 GB Memory and 3 processors. The remaining one CPU and 4.5 GB memory would be enough to run your IDE and browser if you are not running anything else. To conncet to the sandbox via SSH I am using Putty.

!New Project (images/img-1.jpg?raw=true "New Project")
