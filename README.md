# Hadoop-Wordcount

# JAR file creation process.
step by step instructions:
 1. open eclipse IDE
 2. create a new java project. 
 3. right click the project folder select <b> "Build Path" -> "Configure Path"</b>.
 4. include Hadoop jar files from $HADOOP_HOME/share/hadoop/mapreduce <i>(Note:$HADOOP_HOME=YOUR HADOOP FILES LOCATION).</i>
 5. create the following java files, WCDriver(having the main function), WCMapper, WCReducer.
 6. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCDriver.java">code</a> into WCDriver file.
 7. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCMapper.java">code</a>  into WCMapper file.
 8. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCReducer.java">code</a>  into WCReducer file.
 9. right click the project folder. and click <b> "Export" </b> option.
 10. <b> Under java select JAR</b> then click next. select the location to store JAR fie and specify the Name of the JAR file (eg. wordcount.jar).
 11. open terminal where your JAR file is stored. 
 
 ## Hadoop commands
 1. type <i>start-all.sh</i> to start all hadoop daemons. 
 2. check JPS (Java Virtual Machine Process Status Tool) stauts.
 3. create Dirctory in hadoop by using the following command.<br>
 <code>hdfs dfs -mkdir -p /YOURDIRECTORYNAME</code>
 4. Command to Copy your localfiles to HDFS. <br>
 <code>SYNTAX: hdfs dfs -put /LOCALPATH /HADOOPPATH</code> <br>
 <code> hdfs dfs -put /root/eclipse-workspace/WCFile.txt /wordcount/WCFile.txt</code>
 5. Now go to Hadoop Dashboard.URL: http://localhost:50070.
 6. Here click utilise path. you can check your folder avaiable. then click the folder your text file stored in this location.
 7. To run wordcount program type the following command. <br>
 <code> SYNTAX: hadoop jar YOURJARFILE YOUR_JAVA_FILE_CLASS_NAME(which has the main function)  TEXT_FILE_PATH(stored in hdfs folder) OUTPUT_FILE_NAME</code> <br>
 <code> Example: hadoop jar WordCount.jar WCDriver hdfs://localhost:9000/wordcount/WCFile.txt WCOutput</code>
 8. To view the result of the WordCountFile. <br>
 <code>Example: hadoop fs -cat WCOutput/part-00000 </code>
 9. To stop all hadoop daemons, run <i>stop-all.sh</i>.
