# Topic 4a - IP Addressing

# Table of contents


-----------------

# IPv4 Addressing
- An IPv4 address is a 32-bit number that uniquely identifies a device on a network.
- They are devided into 4 octets, each octet is 8 bits long.
- Each octet is converted to decimal and seperated by a dot.
  - Fore deciaml numbers are seperated by a dot.
    - Example 
    - ```11111111.11111111.11111111.11111111``` is ```255.255.255.255```

- Subnet masks are also 32-bit numbers that serve to determine how the IP address is divided into network and host portions.
- When written in binary form, the subnet mask consists of a series of ones followed by a series of zeros.

Example: 
192.168.1.10/24

```11000000.10101000.00000001.00001010``` is ```
255.255.255.0``` converts to ```11111111.11111111.11111111.00000000```

The first 24 bits are ones, and the last 8 bits are zeros. This means that the first 24 bits of the IP address are the network portion, and the last 8 bits are the host portion.

The example shows that 192.168.1.0 is the network address, and the 10 is the network host, and the subnet mask is 24.

-----------------

# Binary Math 
- How is the subnet mask used to determine the network ID?
  - Computers determine the network ID by doing a logical ```AND``` operation on the IP address and the subnet mask.
  - A logical AND in an operation between two binary values
- AND operations can be the following

||||=|
|-|-|-|-|
|0|AND|0|0|
|0|AND|1|0|
|1|AND|0|0|
|1|AND|1|1|

## Finding the Subnet mask
- The logical AND operation between a computer's IP address and subnet mask looks like this:


![img](https://i.imgur.com/tc8WFaS.png)

# How does binary works



|128|64|32|16|8|4|2|1|=|255|
|-|-|-|-|-|-|-|-|-|-|
|1|1|1|1|1|1|1|1|=|255|
|1|1|1|1|1|1|1|0|=|254|
|1|1|1|1|1|1|0|0|=|252|
|1|1|1|1|1|0|0|0|=|248|
|1|1|1|1|0|0|0|0|=|240|
|1|1|1|0|0|0|0|0|=|224|
|1|1|0|0|0|0|0|0|=|192|
|1|0|0|0|0|0|0|0|=|128|
|0|0|0|0|0|0|0|0|=|0|





