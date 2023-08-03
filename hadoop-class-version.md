# Steps to install HADOOP:

1. ### Java Installation

      a. Run these commands
      ```
      sudo apt update
      sudo apt install default-jdk
      readlink -f /usr/bin/java | sed "s:bin/java::"
      ```
      This should output the installed path, copy paste it somewhere. Now this should be used for the value of JAVA_HOME evrywhere. In my case it was "/usr/lib/jvm/java-11-openjdk-amd64/". But you use what you got from the output above.
   
      b. Modifing environment file
      ```
      sudo nano /etc/environment
      ```
      Add this line at the end of file, 
      ```
      JAVA_HOME="/usr/lib/jvm/java-11-openjdk-amd64/"
      ```
      then close it with "Ctrl-X".

      c. Run the commands below now:
      ```
      export JAVA_HOME
      source /etc/environment
      echo $JAVA_HOME
      ```
      the echo command should output "/usr/lib/jvm/java-11-openjdk-amd64/" indicating proper installation.

3. ### Hadoop Installation

      a. Go to this link(https://hadoop.apache.org/releases.html) and download the marked file shown below:

   <img width="600" alt="Apache_Hadoop" src="https://github.com/VikasShavi/DSAI/assets/83757578/8b092feb-7aa2-41f1-ba40-bc5eb4230569">

      b. Now follow the commands to install hadoop
     ```
     cd ~/Downloads
     tar -xvzf hadoop-3.2.4.tar.gz
     sudo mv hadoop-3.2.4 /usr/local/hadoop
     export PATH=$PATH:/usr/local/hadoop/bin/
     hadoop version
     ```
     If the last command run perfectly, then hadoop is installed perfectly.

4. ### Streaming Jar Download

      * Go to this link(https://jar-download.com/artifacts/org.apache.hadoop/hadoop-streaming) and download the file

      <img width="600" alt="Download_org_apache_hadoop_JAR_files_with_all_dependencies" src="https://github.com/VikasShavi/DSAI/assets/83757578/858ef9e0-985d-48f6-ba2c-5bd172cc21b8">
      
      Unzip the file,
      ```
      unzip jar_files.zip
      ```
      If the above does not work, try the following
   
      * Go to this link(https://mvnrepository.com/artifact/org.apache.hadoop/hadoop-streaming/3.2.4) and download the file shown below
   
      <img width="600" alt="Maven_Repository__org_apache_hadoop_»_hadoop-streaming_»_3_2_4" src="https://github.com/VikasShavi/DSAI/assets/83757578/c83c3e7a-66e3-4096-935f-dcf3b76fb37e">

6. ### Python3 installation
      ```
      sudo apt install python3
      sudo ln -sf /usr/bin/python3 /usr/bin/python
      ```
   
### Everything is setup now.

       
