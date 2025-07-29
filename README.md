# vlsm-subnetting
VLSM stands for Variable Length Subnet Masking. This is a network addressing technique. By using this we can divide a network into subnets of different sizes. This maximize the efficiency of IP address allocation.

This project documents a simple example of how to use VLSM (Variable Length Subnet Masking.

## problem
Given the network 192.168.10.0/24, create subnets for:
- subnet with 20 hosts
- subnet with 100 hosts
- subnet with 10 hosts
- subnet with 50 hosts

## steps
### 1. Arrange the subnets in descending order
- Subnet A: 100 hosts
- Subnet B: 50 hosts
- Subnet C: 20 hosts
- Subnet D: 10 hosts

### 2. Allocating subnets
Subnet A (100 hosts)
- Needs 100 hosts. 2^7 = 128 hosts. Prefix: /25
- Network: 192.168.10.0/25
- Range: 192.168.10.1 – 192.168.10.126
- Broadcast: 192.168.10.127
- Block size: 128

Subnet B (50 hosts)
- Next available: 192.168.10.128
- 2^6 = 64 hosts. Prefix: /26
- Network: 192.168.10.128/26
- Range: 192.168.10.129 – 192.168.10.190
- Broadcast: 192.168.10.191
- Block size: 64

Subnet C (20 hosts)
- Next available: 192.168.10.192
- 2^5 = 32 hosts. Prefix: /27
- Network: 192.168.10.192/27
- Range: 192.168.10.193 – 192.168.10.222
- Broadcast: 192.168.10.223
- Block size: 32

Subnet D (10 hosts)
- Next available: 192.168.10.224
- 2^4 = 16 hosts. Prefix: /28
- Network: 192.168.10.224/28
- Range: 192.168.10.225 – 192.168.10.238
- Broadcast: 192.168.10.239
- Block size: 16

## Final subnet table

| Subnet | Network Address | Prefix | Usable IP Range          | Broadcast      |
|--------|-----------------|--------|--------------------------|----------------|
| A      | 192.168.10.0    | /25    | 192.168.10.1 - 126       | 192.168.10.127 |
| B      | 192.168.10.128  | /26    | 192.168.10.129 - 190     | 192.168.10.191 |
| C      | 192.168.10.192  | /27    | 192.168.10.193 - 222     | 192.168.10.223 |
| D      | 192.168.10.224  | /28    | 192.168.10.225 - 238     | 192.168.10.239 |

Remaining free space: 192.168.10.240 – 192.168.10.255 (for future use)
