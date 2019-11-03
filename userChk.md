# User Checking Cmd
## Create 
Create new user 
```shell
root@kali:~/hack/bgnrpentest/Notes# adduser bob
Adding user `bob' ...
Adding new group `bob' (1001) ...
Adding new user `bob' (1001) with group `bob' ...
Creating home directory `/home/bob' ...
Copying files from `/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for bob
Enter the new value, or press ENTER for the default
        Full Name []: 
        Room Number []: 
        Work Phone []: 
        Home Phone []: 
        Other []: 
Is the information correct? [Y/n] Y
```

## Passwd
get password information
```shell
root@kali:~/hack/bgnrpentest/Notes# cat /etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
...
```

## Shadow
get hash information used to crack systems using unshadowing
```shell
root@kali:~/hack/bgnrpentest/Notes# cat /etc/shadow
root:$6$ZkqnJYrguEPlN3cJ$opLtElxSOi
...
```




