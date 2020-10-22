# Hadoop-Wordcount

# JAR file creation process.
step by step instructions:
 1. open eclipse IDE
 2. create a new java project. 
 <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/create_java_project.png" height="400px" width="700px">
 
 3. right click the project folder select <b> "Build Path" -> "Configure Path"</b>.
 4. include Hadoop jar files from $HADOOP_HOME/share/hadoop/mapreduce <i>(Note:$HADOOP_HOME=YOUR HADOOP FILES LOCATION).</i>
  <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/add_Extranal_JAR_into_our_project.png" height="400px" width="700px">
 
 5. create the following java files, WCDriver(having the main function), WCMapper, WCReducer. directory structure would be like a below image.
  <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/dir_structure.png" height="400px" width="700px"> 
 
 6. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCDriver.java">code</a> into WCDriver file.
 7. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCMapper.java">code</a>  into WCMapper file.
 8. insert the <a href="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/WCReducer.java">code</a>  into WCReducer file.
 9. right click the project folder. and click <b> "Export" </b> option.
 10. <b> Under java select JAR</b> then click next. select the location to store JAR fie and specify the Name of the JAR file (eg. wordcount.jar).
 <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/select_Export%20option.png" height="400px" width="700px">
 <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/specify_ouput_filename_and_path.png" height="400px" width="700px"> 
 11. open terminal where your JAR file is stored. 
 
 ## Hadoop commands
 1. type <i>start-all.sh</i> to start all hadoop daemons. 
 2. check JPS (Java Virtual Machine Process Status Tool) stauts.
 <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/JPS_STATUS.png"> 
 3. create Dirctory in hadoop by using the following command.<br>
 <code>hdfs dfs -mkdir -p /YOURDIRECTORYNAME</code> <br>
 4. Command to Copy your localfiles to HDFS. <br>
 <code>SYNTAX: hdfs dfs -put /LOCALPATH /HADOOPPATH</code> <br>
 <code> hdfs dfs -put /root/eclipse-workspace/WCFile.txt /wordcount/WCFile.txt</code><br>
 5. Now go to Hadoop Dashboard.URL: http://localhost:50070.
 <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/Hadoop_Home_page.png" height="400px" width="700px">
 
 6. Here click utilise path. you can check your folder avaiable. then click the folder your text file stored in this location.
 <img src="https://github.com/prawinrajan/Hadoop-Wordcount/blob/master/screenshot/move_to_filesfolder.png" height="400px" width="700px">
 7. To run wordcount program type the following command. <br>
 <code> SYNTAX: hadoop jar YOURJARFILE YOUR_JAVA_FILE_CLASS_NAME(which has the main function)  TEXT_FILE_PATH(stored in hdfs folder) OUTPUT_FILE_NAME</code> <br>
 <code> Example: hadoop jar WordCount.jar WCDriver hdfs://localhost:9000/wordcount/WCFile.txt WCOutput</code>
 8. To view the result of the WordCountFile. <br>
 <code>Example: hadoop fs -cat WCOutput/part-00000 </code>
 9. To stop all hadoop daemons, run <i>stop-all.sh</i>.
