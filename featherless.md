


To check ARP filter status:

```
for i in {101..169}; do
  ip="10.32.56.$i"
  printf "%-15s : " "$ip"
  ssh "$ip" "cat /proc/sys/net/ipv4/conf/all/arp_filter"
done
```

To fix ARP filter status 

```for i in {101..169}; do
  ip="10.32.56.$i"
  printf "%-15s : " "$ip"
  ssh "$ip" "sudo sysctl -w net.ipv4.conf.all.arp_filter=0"
done
```