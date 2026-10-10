

# The quick method

This method relies on shortcut table memorization. The table below is the first shortcut table we will use.

```text
128   64   32  16   8   4   2   1
128  192  224 240 248 252 254 255
```

Line number one shows the decimal values for the binary numbers of an octet.

**Example_1:**

172.16.35.123/20 172.16.35.123 255.255.240.0

Step 1. Find out where the octet is not 255.

Step 2. Note that octet as the network and host portion reside within that octet.

Step 3. Subtract the subnet value that is not 255, from 256
```text
16
240

256-240 = 16
```
Step 4. Workout where 35 is the range of networks worked out in step 2. Just start at zero in the range of networks worked out in step 3. Once you go past the value, that is your network.
Networks in multiples of 16 would be:
```text
1: 0
2: 16
3: 32
        ---------- 35 between the two
4: 48
```

Step 5. Leave the network address the same, our in between values are 32 and 48, our subnet value is 35. We then round, because 35 is closer to 32, that is our subnet.
```text
172.16.32.0
```
This means, our next subnet will be 48.

Step 6. Finding The Broadcast
Broadcast address = Next Network - 1

Step 7. Finding the first host
First Host = Subnet + 1

Step 8. Finding the last host
Last Host = Broadcast -1 
