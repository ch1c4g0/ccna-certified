
# Use the following instructions to configure the network.
```text
1) You have been allocated subnet 192.168.1.0/24. 
Subnet this into four subnets as follows 
2) Subnet 1 for site 1
3) Subnet 2 for the link between R1 and the Internet Router
4) Subnet 3 for site 2
5) Subnet 4 for the link between R2 and the Internet Router
6) Configure the routers per the instructions in the diagram.
7) Verify that PCs can access cisco.com and facebook.com using their browsers
```
# Quick Reference Formulas

**Finding available subnets**
```text
2^(new prefix - old prefix) = Total subnets
```
**Finding the amount of subnets you need**
```text
2^n = number of subnets

[!NOTE] Each borrowed bit doubles the number of possible subnet combinations:

1 borrowed bit  = 2¹ = 2 subnets
2 borrowed bits = 2² = 4 subnets
3 borrowed bits = 2³ = 8 subnets
```
**Calculating Block Size**
```text
256 - Last network octet = Block Size
```
**Calculating CIDR use-able hosts**
```text
2^(32-Current /CIDR) -2
```







