```bash
# @local
## generate a key
ssh-keygen -t rsa

## copy the key to server
# alternative 1
ssh-copy-id -i ~/.ssh/id_rsa UserName@ServerIP 

# alternative 2
## @local
scp $HOME/.ssh/id_rsa.pub UserName@ServerIP:~/.ssh
## @server
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys 
# cp id_rsa.pub  authorized_keys
```

```bash
# server
chmod 755 ~ 
chmod 700 ~/.ssh 
chmod 600 ~/.ssh/authorized_keys
```

cr: https://shixiangwang.github.io/home/cn/post/2020-08-10-linux-cannot-login-with-publickey/