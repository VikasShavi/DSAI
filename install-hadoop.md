Steps:
1. Go to the link and download the binary suitable for your laptop:
     https://hadoop.apache.org/releases.html
     <img width="600" alt="Screenshot 2023-08-03 at 00 15 36" src="https://github.com/VikasShavi/DSAI/assets/83757578/1f6b119b-bd22-4609-be2c-08b60a724d5d">
     <img width="600" alt="Screenshot 2023-08-03 at 00 15 36" src="https://github.com/VikasShavi/DSAI/assets/83757578/1f6b119b-bd22-4609-be2c-08b60a724d5d">

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
    i. /home/kali/.bashrc        # if the current shell is /bin/bash
    ii. /home/kali/.zshrc        # if the current shell is /bin/zsh