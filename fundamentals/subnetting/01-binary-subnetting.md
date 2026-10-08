

# Why use binary to subnet?

Binary is the main language computers understand. If you use binary, you will gain a broader knowledge of the technology that all tech relies on.

## The rules

The host portion of a network(subnet) address with be all 0's, the network ID portion will be all 1's.

### Finding the Broadcast Address

Fill the host portion with binary 1's.

### Finding the First Host

Fill the host portion of the address with all binary 0's, with the last bit being binary 1.

### Finding the Last Host

Fill the host portion of the address with all binary 1's, with the last bit being binary 0.

**Example**

#### Network 192.168.1.18/24 or 255.255.255.0

|Solve for|Host Portion w/ Binary|Hexadecimal Representation|
|---------|----------------------|--------------------------|
|Subnet   |192.168.1.00000000    |192.168.1.0               |
|1st Host |192.168.1.00000001    |192.168.1.1               |  
|Last Host|192.168.1.11111110    |192.168.1.254             |  
|Broadcast|192.168.1.11111111    |192.168.1.255             |

*The network portion is everything before the host portion*

**Challenging Example**

#### 172.16.35.123/20

This is not a simple split like the previous example. The previous example has a simple subnet mask of 255.255.255.0 this network has a subnet mask of 255.255.240.0.

To figure out the network and host portion, we know that each octet is 8 bits, we have a total of 20 on bits, this means our network and hosts will be split in the third octet as 8x3 is 24 which is higher than the listed CIDR notation.

Because we know the split is somewhere in the third octet, we only need to convert the third and forth to binary as the first and second will be part of the network id.

  | 128 | 64 | 32 | 16 | 8 | 4 | 2 | 1 |
  |-----|----|----|----|---|---|---|---|
  
 - 35 converted using the chart above would be, 00100011.
 - 123 converted using the cart above would be, 01111011.

Now we can take our original address, removing the 3rd and 4th octet, appending our binary representations in place. After this, we can count up the bits till our defined CIDR notation.

```
172.16.001000011.01111011
|_____|____|____________|
   |     |       |
  /16   /20     Host
```

We can now repeat the steps listed initially. The subnet and 1st host field will be the same, the last host and broadcast address will change here.This is because the four Zeros on the network side need to be added together with the four zeros on the host side.

**Example**

#### Network 172.16.32.123/20 or 255.255.240.0

172.16.0010|00011.01111011

Everything after the 20th bit(the network ID) will now be changed like the previous example.

**To find the subnet, we change all host bits to 0.**
172.16.0010|0000.00000000 = 172.16.32.0

**To find the first address, we change all host bits to 0, except the last bit.**
172.16.0010|0000.00000001 = 172.16.32.1

**To find the last host address, we change all host bits to 1, except for the last bit.**
172.16.0010|1111.11111110

At this point, you'll need to convert your 3rd and 4th octet back to hexadecimal. In this case, it would be 47 and 254.
172.16.0010|1111.11111110 = 172.16.47.254

**To find the broadcast address, we will change all host bits to 1.**

172.16.0010|1111.11111111 = 172.16.47.255

 









