

# Question 1:

What is the network address for host 172.16.1.1 with network mask 255.255.192.0?

A: 172.16.0.0/16
B: 172.16.1.0/16
C: 172.16.0.0/18
D: 172.16.1.1/18

Step 1: Identify network octets.
```text
172.16.0.0
```
Step 2: Turn the third octet to binary to find where the subnet splits from network to host. You can use the chart below if you need assistance.
```text
| 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
   1     1    0    0   0   0   0   0 = 192.
```

Step 3: Combine your network address value to the previous subnet ID.
```text
172.16.11000000.00000000
```
Now we know everything after the 1's is our host portion. This would give us a /18 CIDR notation as the first octet is 8 bits, the second octet is 8 bits, and we are stealing 2 bits from the "host" portion.

```text
172.16.11000000.00000000
        ||______________|
       /18    Hosts
```

Step 4: To find the amount of subnets, take your borrowed bits the power of 2.
```text
2^2 = 4 subnets
```
