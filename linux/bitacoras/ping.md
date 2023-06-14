```
erickmain@erickmain:~$ ping -c 10 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=42.3 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=56 time=64.5 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=56 time=87.1 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=56 time=83.0 ms
64 bytes from 8.8.8.8: icmp_seq=5 ttl=56 time=36.2 ms
64 bytes from 8.8.8.8: icmp_seq=6 ttl=56 time=64.1 ms
64 bytes from 8.8.8.8: icmp_seq=7 ttl=56 time=19.3 ms
64 bytes from 8.8.8.8: icmp_seq=8 ttl=56 time=23.2 ms
64 bytes from 8.8.8.8: icmp_seq=9 ttl=56 time=25.1 ms
64 bytes from 8.8.8.8: icmp_seq=10 ttl=56 time=21.7 ms

erickmain@erickmain:~$ ping -i 5 -c 5 8.8.8.8
PING 8.8.8.8 (8.8.8.8) 56(84) bytes of data.
64 bytes from 8.8.8.8: icmp_seq=1 ttl=56 time=72.7 ms
64 bytes from 8.8.8.8: icmp_seq=2 ttl=56 time=84.3 ms
64 bytes from 8.8.8.8: icmp_seq=3 ttl=56 time=92.1 ms
64 bytes from 8.8.8.8: icmp_seq=4 ttl=56 time=104 ms
64 bytes from 8.8.8.8: icmp_seq=5 ttl=56 time=126 ms

--- 8.8.8.8 ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 20018ms
rtt min/avg/max/mdev = 72.679/95.866/125.810/18.190 ms

```