# Hadoop-Wordcount

# JAR file creation process.
step by step instructions:
 1. open eclipse IDE
 2. create a new java project. 
 3. right click the project folder select "Build Path" -> "Configure Path".
 4. include Hadoop jar files from $HADOOP_HOME/share/hadoop/mapreduce
 5. create java file the following file name, WCDriver(having the main function), WCMapper, WCReducer.
 6. Now insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCDriver.java">code</a> into WCDriver file.
 7. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCMapper.java">code</a>  into WCMapper file.
 8. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCReducer.java">code</a>  into WCReducer file.
 9. right click the project folder. and click "export" option.
 10. under java select JAR then click next. select the location to store JAR fie and specify the Name of the JAR file (eg. wordcount.jar).
 11. open terminal where your JAR file is stored. 
 
 ## Hadoop commands
 1. type start-all.sh to start all hadoop daemon. 
 2. check JPS stauts.
 3. create Dirctor in hadoop by using the following command.<br>
 <code>hdfs dfs -mkdir -p /YOURDIRECTORYNAME</code>
 4. Command to Copy your localfile to HDFS. <br>
 <code>SYNTAX: hdfs dfs -put /LOCALPATH /HADOOPPATH</code> <br>
 <code> hdfs dfs -put /root/eclipse-workspace/WCFile.txt /wordcount/WCFile.txt</code>
 5. Now go to Hadoop Dashboard to view your files.URL: http://localhost:50070.
 6.Here click utilise path. you can check your file stored location.
 7. To run wordcount program type the following command. <br>
 
 <code> SYNTAX: hadoop jar YOURJARFILE YOUR_JAVA_FILE_CLASS_NAME(which has the main function)  TEXT_FILE_PATH(stored in hdfs folder) OUTPUT_FILE_NAME</code> <br>
 <code> hadoop jar WordCount.jar WCDriver hdfs://localhost:9000/wordcount/WCFile.txt WCOutput</code>
 
 8. To view the result of the WordCountFile. <br>
 <code> hadoop fs -cat WCOutput/part-00000 </code>
