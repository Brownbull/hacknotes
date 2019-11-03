# Network Commands
- [Network Commands](#Network-Commands)
  - [ifconfig](#ifconfig)
  - [iwconfig](#iwconfig)
  - [ping](#ping)
  - [arp](#arp)
  - [netstat](#netstat)
  - [route](#route)

***
## ifconfig
similar to ipconfig
```shell
root@kali:~/hack/bgnrpentest/Notes# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.0.2.15  netmask 255.255.255.0  broadcast 10.0.2.255
        inet6 fe80::a00:27ff:fe6a:f621  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:6a:f6:21  txqueuelen 1000  (Ethernet)
        RX packets 489666  bytes 650015423 (619.9 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 93979  bytes 10053474 (9.5 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```

## iwconfig
wireless adapters confg
```shell

root@kali:~/hack/bgnrpentest/Notes# iwconfig
eth0      no wireless extensions.

lo        no wireless extensions.
```

## ping
send package of info to check connection
```shell
root@kali:~/hack/bgnrpentest/Notes# ping www.google.com
PING www.google.com (64.233.190.103) 56(84) bytes of data.
64 bytes from gsademo22.google.com (64.233.190.103): icmp_seq=1 ttl=45 time=15.8 ms
64 bytes from gsademo22.google.com (64.233.190.103): icmp_seq=2 ttl=45 time=17.4 ms
^C
--- www.google.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 6ms
rtt min/avg/max/mdev = 15.751/16.579/17.407/0.828 ms
```

## arp
associates ip ith mac adress, see who as which IP address
```shell
root@kali:~/hack/bgnrpentest/Notes# arp -a
_gateway (10.0.2.2) at 52:54:00:12:35:02 [ether] on eth0
```

## netstat
show all ports that are open, and what is connected to those ports
```shell
root@kali:~/hack/bgnrpentest/Notes# netstat -ano | grep -a 22980
unix  3      [ ]         STREAM     CONNECTED     22980 
```

## route
see route table
```shell
root@kali:~/hack/bgnrpentest/Notes# route
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
default         _gateway        0.0.0.0         UG    100    0        0 eth0
10.0.2.0        0.0.0.0         255.255.255.0   U     100    0        0 eth0
```






