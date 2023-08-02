#Download latest JDK from Oracle website given below:

Steps:
1. Create an account in Oracle, https://profile.oracle.com/myprofile/account/create-account.jspx
2. Go to this link, https://www.oracle.com/in/java/technologies/downloads/
3. As shown in the below fig, scroll to the Java 8 section and download the tar.gz file compatible with your device.
   <img width="600" alt="Screenshot 2023-08-03 at 00 15 36" src="https://github.com/VikasShavi/DSAI/assets/83757578/1f6b119b-bd22-4609-be2c-08b60a724d5d">
4. Then change the directory to /usr/lib/jvm and follow the commands(enter password if prompted):
   
   ```
   cd /usr/lib/jvm
   sudo su -
   apt update
   tar -xvzf /home/kali/Downloads/jdk.tar.gz
   update-alternatives --install /usr/bin/java java /usr/lib/jvm/jdk1.8.0_381/bin/java 20000
   update-alternatives --install /usr/bin/javac javac /usr/lib/jvm/jdk1.8.0_381/bin/javac 20000
   java -version
    ```
