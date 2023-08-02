Steps:
1. start ssh server
    ```
    sudo service ssh start
    ```
2. Generate key pairs(dont input anything when asked for passphrase, just press enter):
    ```
    ssh-keygen -t rsa
    ```
3. Add keys to authorized_keys:
    ```
    cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
    ```