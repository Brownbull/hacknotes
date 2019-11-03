# User Checking Cmd
- [User Checking Cmd](#User-Checking-Cmd)
  - [SUDO](#SUDO)
  - [Create User](#Create-User)
  - [Change User](#Change-User)
    - [Unauthorized operation](#Unauthorized-operation)
      - [Operation](#Operation)
      - [Log check](#Log-check)
  - [Passwd File](#Passwd-File)
  - [Shadow File](#Shadow-File)

***

## SUDO
stands for Superuser do, allows to execute a command as superuser
```shell
sudo chmod 777 asd.txt
```

## Create User
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

## Change User
Change current user on console
```shell
root@kali:~/hack/bgnrpentest/Notes# su bob
bob@kali:/root/hack/bgnrpentest/Notes$ cat /etc/shadow
cat: /etc/shadow: Permission denied
bob@kali:/root/hack/bgnrpentest/Notes$ su -
Password: 
root@kali:~# 
```

### Unauthorized operation
Example of unauthorized operation using unpriviliged user
#### Operation
```shell
bob@kali:/root/hack/bgnrpentest/Notes$ sudo cat /etc/shadow

We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:

    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

[sudo] password for bob: 
bob is not in the sudoers file.  This incident will be reported.
```
#### Log check
```shell
root@kali:~# less /var/log/auth.log | grep -a bob
Nov  3 13:18:49 kali groupadd[8062]: group added to /etc/group: name=bob, GID=1001
Nov  3 13:18:49 kali groupadd[8062]: group added to /etc/gshadow: name=bob
Nov  3 13:18:49 kali groupadd[8062]: new group: name=bob, GID=1001
Nov  3 13:18:49 kali useradd[8066]: new user: name=bob, UID=1001, GID=1001, home=/home/bob, shell=/bin/bash
Nov  3 13:19:00 kali passwd[8074]: pam_unix(passwd:chauthtok): password changed for bob
Nov  3 13:19:02 kali chfn[8078]: changed user 'bob' information
Nov  3 13:29:51 kali su: (to bob) root on pts/1
Nov  3 13:29:51 kali su: pam_unix(su:session): session opened for user bob by (uid=0)
Nov  3 13:34:00 kali sudo:      bob : user NOT in sudoers ; TTY=pts/1 ; PWD=/root/hack/bgnrpentest/Notes ; USER=root ; COMMAND=/usr/bin/cat /etc/shadow
```

## Passwd File
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

## Shadow File
get hash information used to crack systems using unshadowing
```shell
root@kali:~/hack/bgnrpentest/Notes# cat /etc/shadow
root:$6$ZkqnJYrguEPlN3cJ$opLtElxSOi
...
```




