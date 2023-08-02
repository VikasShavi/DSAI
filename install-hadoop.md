Steps:
1. Go to the link and download the binary suitable for your laptop:
     https://hadoop.apache.org/releases.html
   
     <img width="600" alt="Cursor_and_Apache_Hadoop" src="https://github.com/VikasShavi/DSAI/assets/83757578/7acc50fb-bb06-4ede-856e-9614abdea6ba">
     <img width="600" alt="DSAI" src="https://github.com/VikasShavi/DSAI/assets/83757578/6b421af4-f365-437f-8c52-f8da7cdf90a8">

2. Now follow the commands to setup hadoop
    ```
    cd /home/kali
    mkdir course
    cd course
    tar -xvzf /home/kali/Downloads/hadoop-3.3.6.tar.gz
    mv hadoop-3.3.6 hadoop
    ```

3. As we have a single device, single cluster node is to be installed as following:
   
     a. Check the current shell by running 
     ```
     echo $SHELL
     ```
     b. Now add the following text at the end of the file
   ```
   # Hadoop 
     export HADOOP_HOME=/home/kali/course/hadoop/ 
     export HADOOP_INSTALL=$HADOOP_HOME 
     export HADOOP_MAPRED_HOME=$HADOOP_HOME 
     export HADOOP_COMMON_HOME=$HADOOP_HOME 
     export HADOOP_HDFS_HOME=$HADOOP_HOME export YARN_HOME=$HADOOP_HOME 
     export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_HOME/lib/native 
     export PATH=$PATH:$HADOOP_HOME/sbin:$HADOOP_HOME/bin 
     export HADOOP_OPTS="-Djava.library.path=$HADOOP_HOME/lib/nativ"
   ```
   
   * /home/kali/.bashrc   ------>if the current shell is /bin/bash

   * /home/kali/.zshrc    ------>if the current shell is /bin/zsh

5. Source the file:
   ```
   source /home/kali/.bashrc
        or
   source /home/kali/.zshrc
   ```
   Close the terminal and open a new one.

6. Now follow the commands carefully.
   ```
   cd /home/kali/course/
   sudo su -
   nano hadoop/etc/hadoop/hadoop-env.sh
   ```
7. Find the "export JAVA_HOME=" line in the opened file, uncomment it and change it to without quotes at end and beginning
   "export JAVA_HOME=/usr/lib/jvm/jdk1.8.0_381"

8. Edit core-site.xml:
   
   copy the following in between "configuration" tags present in the file
   ```
    <property>
        <name>hadoop.tmp.dir</name>
        <value>/home/kali/course/hdfs/tmp/</value>
    </property>
    <property>
        <name>fs.default.name</name>
        <value>hdfs://127.0.0.1:9000</value>
    </property>
   ```

10. Edit hdfs-site.xml
    
    copy the following in between "configuration" tags present in the file
    ```
    <property>
      <name>dfs.data.dir</name>
      <value>/home/kali/course/hdfs/namenode</value>
       </property>
       <property>
           <name>dfs.data.dir</name>
           <value>/home/kali/course/hdfs/datanode</value>
       </property>
       <property>
           <name>dfs.replication</name>
           <value>1</value>
       </property>
    ```

12. Edit mapred-site.xml:
    
    copy the following in between "configuration" tags present in the file
    ```
    <property> 
         <name>mapreduce.framework.name</name> 
         <value>yarn</value> 
    </property> 
    ```

14. Edit yarn-site.xml:
    
    copy the following in between "configuration" tags present in the file
    ```
    <property>
    <name>yarn.nodemanager.aux-services</name>
    <value>mapreduce_shuffle</value>
       </property>
       <property>
         <name>yarn.nodemanager.aux-services.mapreduce.shuffle.class</name>
         <value>org.apache.hadoop.mapred.ShuffleHandler</value>
       </property>
       <property>
         <name>yarn.resourcemanager.hostname</name>
         <value>127.0.0.1</value>
       </property>
       <property>
         <name>yarn.acl.enable</name>
         <value>0</value>
       </property>
       <property>
         <name>yarn.nodemanager.env-whitelist</name>   
         <value>JAVA_HOME,HADOOP_COMMON_HOME,HADOOP_HDFS_HOME,HADOOP_CONF_DIR,CLASSPATH_PERPEND_DISTCACHE,HADOOP_YARN_HOME,HADOOP_MAPRED_HOME</value>
       </property>
    ```

15. Now format the HDFS by

    ```
    hdfs namenode -format
    ```

16. Start the hadoop:

    ```
    start-all.sh
    ```

17. Then go to HTTP://localhost:9870/ . It should show a dashboard of hadoop which ensures everything worked perfectly.
    
    <img width="600" alt="image" src="https://github.com/VikasShavi/DSAI/assets/83757578/09dcb00c-54f8-42bb-8f73-e09ad01cffeb">

18. Now go to utilities dropdown, then to "browse the file system". You will see an empty table because we have not yet added any files or folders in our HDFS.
    
20. To add a folder named folder1:
    ```
    hadoop fs -mkdir /folder1
    ```
    
21. To add a file named demo.csv(present in the current folder) in folder1:
    ```
    hadoop fs -put demo.csv /folder1
    ```
   
   
