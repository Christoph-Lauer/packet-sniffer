# Packet-Sniffer
A simple network packet sniffer for Linux in 350 lines of code.

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

## Build Instructions:
```
git clone https://github.com/Christoph-Lauer/packet-sniffer.git
cd packet-analyzer
make
```

## Run:
```
sudo ./packet-analyzer
```

the program outputs:

```
Starting...
TCP : 8   UDP : 45   ICMP : 0   IGMP : 0   Others : 9   Total : 61
```

and writes the results in a log file `log.txt`:

```
cat log.txt
```


```
***********************TCP Packet*************************

Ethernet Header
   |-Destination Address : 64-4B-F0-13-B0-0A 
   |-Source Address      : DC-A6-32-1D-F2-EB 
   |-Protocol            : 8 

IP Header
   |-IP Version        : 4
   |-IP Header Length  : 5 DWORDS or 20 Bytes
   |-Type Of Service   : 16
   |-IP Total Length   : 104  Bytes(Size of Packet)
   |-Identification    : 25151
   |-TTL      : 64
   |-Protocol : 6
   |-Checksum : 20994
   |-Source IP        : 192.168.2.121
   |-Destination IP   : 192.168.2.117

TCP Header
   |-Source Port      : 22
   |-Destination Port : 59246
   |-Sequence Number    : 4107739630
   |-Acknowledge Number : 350711183
   |-Header Length      : 8 DWORDS or 32 BYTES
   |-Urgent Flag          : 0
   |-Acknowledgement Flag : 1
   |-Push Flag            : 1
   |-Reset Flag           : 0
   |-Synchronise Flag     : 0
   |-Finish Flag          : 0
   |-Window         : 63
   |-Checksum       : 50429
   |-Urgent Pointer : 0

                        DATA Dump                         
IP Header
    64 4B F0 13 B0 0A DC A6 32 1D F2 EB 08 00 45 10         dK......2.....E.
    00 68 62 3F                                             .hb?
TCP Header
    40 00 40 06 52 02 C0 A8 02 79 C0 A8 02 75 00 16         @.@.R....y...u..
    E7 6E F4 D7 21 EE 14 E7 6D 8F 80 18 00 3F C4 FD         .n..!...m.?..?..
Data Payload
    59 EF 37 3F 4D 3E AC 55 3F D3 5E CD C7 5F 8D B8         Y.7?M>.U?.^.._..
    0E 11 B8 E4 4F CC 7D B5 E5 3A CC 78 1D 2D 75 3C         ....O.}..:.x.-u<
    D3 D9 09 B0 93 04 DD 3C D8 5E D1 EF 49 E9 3A 3B         .......<.^..I.:;
    78 BC F6 E1                                             x...

###########################################################

***********************TCP Packet*************************

Ethernet Header
   |-Destination Address : DC-A6-32-1D-F2-EB 
   |-Source Address      : 64-4B-F0-13-B0-0A 
   |-Protocol            : 8 

IP Header
   |-IP Version        : 4
   |-IP Header Length  : 5 DWORDS or 20 Bytes
   |-Type Of Service   : 72
   |-IP Total Length   : 52  Bytes(Size of Packet)
   |-Identification    : 0
   |-TTL      : 64
   |-Protocol : 6
   |-Checksum : 46141
   |-Source IP        : 192.168.2.117
   |-Destination IP   : 192.168.2.121

TCP Header
   |-Source Port      : 59246
   |-Destination Port : 22
   |-Sequence Number    : 350711183
   |-Acknowledge Number : 4107739682
   |-Header Length      : 8 DWORDS or 32 BYTES
   |-Urgent Flag          : 0
   |-Acknowledgement Flag : 1
   |-Push Flag            : 0
   |-Reset Flag           : 0
   |-Synchronise Flag     : 0
   |-Finish Flag          : 0
   |-Window         : 2047
   |-Checksum       : 36
   |-Urgent Pointer : 0

                        DATA Dump                         
IP Header
    DC A6 32 1D F2 EB 64 4B F0 13 B0 0A 08 00 45 48         ..2...dK......EH
    00 34 00 00                                             .4..
TCP Header
    40 00 40 06 B4 3D C0 A8 02 75 C0 A8 02 79 E7 6E         @.@..=...u...y.n
    00 16 14 E7 6D 8F F4 D7 22 22 80 10 07 FF 00 24         ....m...""?....$
Data Payload

###########################################################

***********************UDP Packet*************************

Ethernet Header
   |-Destination Address : 01-00-5E-00-00-FB 
   |-Source Address      : 84-0D-8E-00-2E-C6 
   |-Protocol            : 8 

IP Header
   |-IP Version        : 4
   |-IP Header Length  : 5 DWORDS or 20 Bytes
   |-Type Of Service   : 0
   |-IP Total Length   : 265  Bytes(Size of Packet)
   |-Identification    : 53773
   |-TTL      : 255
   |-Protocol : 17
   |-Checksum : 17613
   |-Source IP        : 192.168.2.101
   |-Destination IP   : 224.0.0.251

UDP Header
   |-Source Port      : 5353
   |-Destination Port : 5353
   |-UDP Length       : 245
   |-UDP Checksum     : 10743

IP Header
    01 00 5E 00 00 FB 84 0D 8E 00 2E C6 08 00 45 00         ..^...........E.
    01 09 D2 0D                                             ....
UDP Header
    00 00 FF 11                                             ....
Data Payload
    00 F5 29 F7 00 00 84 00 00 00 00 05 00 00 00 00         ..).............
    04 5F 68 61 70 04 5F 74 63 70 05 6C 6F 63 61 6C         ._hap._tcp.local
    00 00 0C 00 01 00 00 11 94 00 0D 0A 4F 75 74 6C         ............Outl
    65 74 32 45 43 36 C0 0C C0 27 00 10 80 01 00 00         et2EC6...'..?...
    11 94 00 4F 0D 6D 64 3D 4F 75 74 6C 65 74 32 45         ...O.md=Outlet2E
    43 36 06 70 76 3D 31 2E 30 14 69 64 3D 30 46 3A         C6.pv=1.0.id=0F:
    38 39 3A 37 35 3A 30 43 3A 38 34 3A 33 31 04 63         89:75:0C:84:31.c
    23 3D 31 04 73 23 3D 31 04 66 66 3D 30 04 63 69         #=1.s#=1.ff=0.ci
    3D 37 04 73 66 3D 30 0B 73 68 3D 69 57 78 6C 35         =7.sf=0.sh=iWxl5
    67 3D 3D C0 27 00 21 80 01 00 00 00 78 00 1D 00         g==.'.!?....x...
    00 00 00 02 95 14 48 4B 5F 30 46 3A 38 39 3A 37         ......HK_0F:89:7
    35 3A 30 43 3A 38 34 3A 33 31 C0 16 C0 A1 00 01         5:0C:84:31......
    80 01 00 00 00 78 00 04 C0 A8 02 65 09 5F 73 65         ?....x.....e._se
    72 76 69 63 65 73 07 5F 64 6E 73 2D 73 64 04 5F         rvices._dns-sd._
    75 64 70 C0 16 00 0C 00 01 00 00 11 94 00 02 C0         udp.............
    0C                                                      .

###########################################################

***********************UDP Packet*************************

Ethernet Header
   |-Destination Address : 01-00-5E-00-00-FB 
   |-Source Address      : 4C-11-AE-00-31-4C 
   |-Protocol            : 8 

IP Header
   |-IP Version        : 4
   |-IP Header Length  : 5 DWORDS or 20 Bytes
   |-Type Of Service   : 0
   |-IP Total Length   : 265  Bytes(Size of Packet)
   |-Identification    : 54093
   |-TTL      : 255
   |-Protocol : 17
   |-Checksum : 17294
   |-Source IP        : 192.168.2.100
   |-Destination IP   : 224.0.0.251

UDP Header
   |-Source Port      : 5353
   |-Destination Port : 5353
   |-UDP Length       : 245
   |-UDP Checksum     : 15

IP Header
    01 00 5E 00 00 FB 4C 11 AE 00 31 4C 08 00 45 00         ..^...L...1L..E.
    01 09 D3 4D                                             ...M
UDP Header
    00 00 FF 11                                             ....
Data Payload
    00 F5 00 0F 00 00 84 00 00 00 00 05 00 00 00 00         ................
    04 5F 68 61 70 04 5F 74 63 70 05 6C 6F 63 61 6C         ._hap._tcp.local
    00 00 0C 00 01 00 00 11 94 00 0D 0A 4F 75 74 6C         ............Outl
    65 74 33 31 34 43 C0 0C C0 27 00 10 80 01 00 00         et314C...'..?...
    11 94 00 4F 0D 6D 64 3D 4F 75 74 6C 65 74 33 31         ...O.md=Outlet31
    34 43 06 70 76 3D 31 2E 30 14 69 64 3D 34 46 3A         4C.pv=1.0.id=4F:
    35 44 3A 31 41 3A 30 37 3A 42 43 3A 35 30 04 63         5D:1A:07:BC:50.c
    23 3D 31 04 73 23 3D 31 04 66 66 3D 30 04 63 69         #=1.s#=1.ff=0.ci
    3D 37 04 73 66 3D 30 0B 73 68 3D 63 59 67 6C 38         =7.sf=0.sh=cYgl8
    77 3D 3D C0 27 00 21 80 01 00 00 00 78 00 1D 00         w==.'.!?....x...
    00 00 00 02 95 14 48 4B 5F 34 46 3A 35 44 3A 31         ......HK_4F:5D:1
    41 3A 30 37 3A 42 43 3A 35 30 C0 16 C0 A1 00 01         A:07:BC:50......
    80 01 00 00 00 78 00 04 C0 A8 02 64 09 5F 73 65         ?....x.....d._se
    72 76 69 63 65 73 07 5F 64 6E 73 2D 73 64 04 5F         rvices._dns-sd._
    75 64 70 C0 16 00 0C 00 01 00 00 11 94 00 02 C0         udp.............
    0C                                                      .

###########################################################

***********************UDP Packet*************************

Ethernet Header
   |-Destination Address : 01-00-5E-00-00-FB 
   |-Source Address      : 84-0D-8E-00-2E-C6 
   |-Protocol            : 8 

IP Header
   |-IP Version        : 4
   |-IP Header Length  : 5 DWORDS or 20 Bytes
   |-Type Of Service   : 0
   |-IP Total Length   : 265  Bytes(Size of Packet)
   |-Identification    : 53774
   |-TTL      : 255
   |-Protocol : 17
   |-Checksum : 17612
   |-Source IP        : 192.168.2.101
   |-Destination IP   : 224.0.0.251

UDP Header
   |-Source Port      : 5353
   |-Destination Port : 5353
   |-UDP Length       : 245
   |-UDP Checksum     : 10743

IP Header
    01 00 5E 00 00 FB 84 0D 8E 00 2E C6 08 00 45 00         ..^...........E.
    01 09 D2 0E                                             ....
UDP Header
    00 00 FF 11                                             ....
Data Payload
    00 F5 29 F7 00 00 84 00 00 00 00 05 00 00 00 00         ..).............
    04 5F 68 61 70 04 5F 74 63 70 05 6C 6F 63 61 6C         ._hap._tcp.local
    00 00 0C 00 01 00 00 11 94 00 0D 0A 4F 75 74 6C         ............Outl
    65 74 32 45 43 36 C0 0C C0 27 00 10 80 01 00 00         et2EC6...'..?...
    11 94 00 4F 0D 6D 64 3D 4F 75 74 6C 65 74 32 45         ...O.md=Outlet2E
    43 36 06 70 76 3D 31 2E 30 14 69 64 3D 30 46 3A         C6.pv=1.0.id=0F:
    38 39 3A 37 35 3A 30 43 3A 38 34 3A 33 31 04 63         89:75:0C:84:31.c
    23 3D 31 04 73 23 3D 31 04 66 66 3D 30 04 63 69         #=1.s#=1.ff=0.ci
    3D 37 04 73 66 3D 30 0B 73 68 3D 69 57 78 6C 35         =7.sf=0.sh=iWxl5
    67 3D 3D C0 27 00 21 80 01 00 00 00 78 00 1D 00         g==.'.!?....x...
    00 00 00 02 95 14 48 4B 5F 30 46 3A 38 39 3A 37         ......HK_0F:89:7
    35 3A 30 43 3A 38 34 3A 33 31 C0 16 C0 A1 00 01         5:0C:84:31......
    80 01 00 00 00 78 00 04 C0 A8 02 65 09 5F 73 65         ?....x.....e._se
    72 76 69 63 65 73 07 5F 64 6E 73 2D 73 64 04 5F         rvices._dns-sd._
    75 64 70 C0 16 00 0C 00 01 00 00 11 94 00 02 C0         udp.............
    0C                                                      .

###########################################################

***********************UDP Packet*************************

Ethernet Header
   |-Destination Address : 01-00-5E-00-00-FB 
   |-Source Address      : 84-0D-8E-00-2E-C6 
   |-Protocol            : 8 

IP Header
   |-IP Version        : 4
   |-IP Header Length  : 5 DWORDS or 20 Bytes
   |-Type Of Service   : 0
   |-IP Total Length   : 265  Bytes(Size of Packet)
   |-Identification    : 53776
   |-TTL      : 255
   |-Protocol : 17
   |-Checksum : 17610
   |-Source IP        : 192.168.2.101
   |-Destination IP   : 224.0.0.251

UDP Header
   |-Source Port      : 5353
   |-Destination Port : 5353
   |-UDP Length       : 245
   |-UDP Checksum     : 10743

IP Header
    01 00 5E 00 00 FB 84 0D 8E 00 2E C6 08 00 45 00         ..^...........E.
    01 09 D2 10                                             ....
UDP Header
    00 00 FF 11                                             ....
Data Payload
    00 F5 29 F7 00 00 84 00 00 00 00 05 00 00 00 00         ..).............
    04 5F 68 61 70 04 5F 74 63 70 05 6C 6F 63 61 6C         ._hap._tcp.local
    00 00 0C 00 01 00 00 11 94 00 0D 0A 4F 75 74 6C         ............Outl
    65 74 32 45 43 36 C0 0C C0 27 00 10 80 01 00 00         et2EC6...'..?...
    11 94 00 4F 0D 6D 64 3D 4F 75 74 6C 65 74 32 45         ...O.md=Outlet2E
    43 36 06 70 76 3D 31 2E 30 14 69 64 3D 30 46 3A         C6.pv=1.0.id=0F:
    38 39 3A 37 35 3A 30 43 3A 38 34 3A 33 31 04 63         89:75:0C:84:31.c
    23 3D 31 04 73 23 3D 31 04 66 66 3D 30 04 63 69         #=1.s#=1.ff=0.ci
    3D 37 04 73 66 3D 30 0B 73 68 3D 69 57 78 6C 35         =7.sf=0.sh=iWxl5
    67 3D 3D C0 27 00 21 80 01 00 00 00 78 00 1D 00         g==.'.!?....x...
    00 00 00 02 95 14 48 4B 5F 30 46 3A 38 39 3A 37         ......HK_0F:89:7
    35 3A 30 43 3A 38 34 3A 33 31 C0 16 C0 A1 00 01         5:0C:84:31......
    80 01 00 00 00 78 00 04 C0 A8 02 65 09 5F 73 65         ?....x.....e._se
    72 76 69 63 65 73 07 5F 64 6E 73 2D 73 64 04 5F         rvices._dns-sd._
    75 64 70 C0 16 00 0C 00 01 00 00 11 94 00 02 C0         udp.............
    0C                                                      .

###########################################################

