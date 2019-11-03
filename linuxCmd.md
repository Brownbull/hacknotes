# Linux Commands
- [Linux Commands](#Linux-Commands)
  - [history](#history)
  - [pwd](#pwd)
  - [cd](#cd)
  - [ls](#ls)
  - [mkdir](#mkdir)
  - [rmdir](#rmdir)
  - [touch](#touch)
  - [nano](#nano)
    - [Commands](#Commands)
  - [cat](#cat)
  - [less](#less)
    - [Pres q for quit](#Pres-q-for-quit)
  - [echo](#echo)
  - [cp](#cp)
  - [mv](#mv)
  - [locate](#locate)
    - [use udpatedb to refresh index](#use-udpatedb-to-refresh-index)
  - [chmod](#chmod)
***

## history
History of previous commands
```shell
root@kali:~/hack/bgnrpentest/Notes# history 10
  191  cat net.txt
  192  less net.txt
  193  ls
  194  rm net.txt
  195  netstat -ano | grep -a 22980
  196  route
  197  history
  198  man history
  199  history -t
  200  history 10
```

## pwd
print working directory 
```shell
root@kali:~/hack/bgnrpentest/Notes# pwd
/root/hack/bgnrpentest/Notes
```
## cd
change directory
```shell
root@kali:~/hack/bgnrpentest/Notes# cd 
root@kali:~# pwd
/root
root@kali:~# cd ..
root@kali:/# pwd
/
root@kali:/# 
```
## ls
list files
```shell
root@kali:~# ls
Desktop    Downloads  HTB    Pictures  Templates
Documents  hack       Music  Public    Videos
root@kali:~# ls -la
total 108
drwxr-xr-x 22 root root 4096 Nov  3 11:04 .
drwxr-xr-x 20 root root 4096 Oct 27 16:25 ..
-rw-------  1 root root 3019 Nov  3 11:51 .bash_history
-rw-r--r--  1 root root 3391 May  8 03:20 .bashrc
drwx------ 14 root root 4096 Nov  3 11:46 .cache
drwxr-xr-x 18 root root 4096 Nov  3 11:46 .config
drwxr-xr-x  2 root root 4096 Jun 17 22:48 Desktop
drwxr-xr-x  2 root root 4096 Jun 17 22:48 Documents
drwxr-xr-x  2 root root 4096 Jun 17 23:12 Downloads
drwx------  3 root root 4096 Jun 17 22:48 .gnupg
drwxr-xr-x  5 root root 4096 Nov  3 12:10 hack
drwxr-xr-x  3 root root 4096 Jun 18 21:19 HTB
-rw-------  1 root root 3084 Nov  3 11:04 .ICEauthority
drwx------  5 root root 4096 Jun 18 21:28 .local
drwx------  5 root root 4096 Jun 17 22:58 .mozilla
drwxr-xr-x  2 root root 4096 Jun 17 22:48 Music
drwxr-xr-x  2 root root 4096 Nov  3 11:47 Pictures
drwx------  3 root root 4096 Jun 18 21:22 .pki
-rw-r--r--  1 root root  148 May  3  2019 .profile
drwxr-xr-x  2 root root 4096 Jun 17 22:48 Public
drwxr-xr-x  2 root root 4096 Jun 18 23:24 .pylint.d
drwxr-xr-x  3 root root 4096 Aug 25 15:15 .set
drwx------  2 root root 4096 Oct 27 17:08 .ssh
drwxr-xr-x  2 root root 4096 Jun 17 22:48 Templates
drwxr-xr-x  2 root root 4096 Jun 17 22:48 Videos
drwxr-xr-x  3 root root 4096 Jun 18 21:22 .vscode
-rw-r--r--  1 root root  214 Aug 25 15:15 .wget-hsts
```
## mkdir
make directory
```shell
root@kali:~/hack/bgnrpentest/Notes# mkdir test
root@kali:~/hack/bgnrpentest/Notes# ls
linuxCmd.md  test
root@kali:~/hack/bgnrpentest/Notes# 
```

## rmdir
remove dir
```shell
root@kali:~/hack/bgnrpentest/Notes# rmdir test
root@kali:~/hack/bgnrpentest/Notes# ls
linuxCmd.md
root@kali:~/hack/bgnrpentest/Notes# 
```
## touch
create a file
```shell
root@kali:~/hack/bgnrpentest/Notes# touch test.txt
root@kali:~/hack/bgnrpentest/Notes# ls
linuxCmd.md  test.txt
root@kali:~/hack/bgnrpentest/Notes# 
```

## nano
modify a file
### Commands
- Ctrl+O Save file
- Ctrl+X Exit

```shell
  GNU nano 3.2                 test.txt                           

this is a test text

asd

^G Get Help  ^O Write Out ^W Where Is  ^K Cut Text  ^J Justify
^X Exit      ^R Read File ^\ Replace   ^U Uncut Text^T To Spell
```

## cat
see file
```shell
root@kali:~/hack/bgnrpentest/Notes# cat test.txt | grep text
this is a test text
```
## less
less shor file quickly
### Pres q for quit
```shell
this is a test text
test.txt (END)
```

## echo
print something somewhere
```shell
root@kali:~/hack/bgnrpentest/Notes# echo "this is another test" > new.txt
root@kali:~/hack/bgnrpentest/Notes# ls
linuxCmd.md  new.txt  test.txt
```
## cp
copy file
```shell
root@kali:~/hack/bgnrpentest/Notes# cp new.txt folder
root@kali:~/hack/bgnrpentest/Notes# cd folder
root@kali:~/hack/bgnrpentest/Notes/folder# ls
new.txt
```

## mv
move file
```shell
root@kali:~/hack/bgnrpentest/Notes# mv new.txt folder
root@kali:~/hack/bgnrpentest/Notes# cd folder/
root@kali:~/hack/bgnrpentest/Notes/folder# ls
new.txt
```
## locate
locate files
### use udpatedb to refresh index
```shel
root@kali:~/hack/bgnrpentest/Notes# nano asd.txt
root@kali:~/hack/bgnrpentest/Notes# less asd.txt 
root@kali:~/hack/bgnrpentest/Notes# locate asd.txt
root@kali:~/hack/bgnrpentest/Notes# updatedb
root@kali:~/hack/bgnrpentest/Notes# locate asd.txt
/root/hack/bgnrpentest/Notes/asd.txt
```

## chmod
change permissions on files
```shell
root@kali:~/hack/bgnrpentest/Notes# nano asd.txt
root@kali:~/hack/bgnrpentest/Notes# ls -la
total 20
drwxr-xr-x  3 root root 4096 Nov  3 13:14 .
drwxr-xr-x 14 root root 4096 Nov  3 11:39 ..
-rw-r--r--  1 root root   13 Nov  3 13:14 asd.txt
drwxr-xr-x  8 root root 4096 Nov  3 13:10 .git
-rw-r--r--  1 root root 3798 Nov  3 13:14 linuxCmd.md
root@kali:~/hack/bgnrpentest/Notes# chmod +x asd.txt
root@kali:~/hack/bgnrpentest/Notes# ls -la
total 20
drwxr-xr-x  3 root root 4096 Nov  3 13:14 .
drwxr-xr-x 14 root root 4096 Nov  3 11:39 ..
-rwxr-xr-x  1 root root   13 Nov  3 13:14 asd.txt
drwxr-xr-x  8 root root 4096 Nov  3 13:10 .git
-rw-r--r--  1 root root 3798 Nov  3 13:14 linuxCmd.md
```









