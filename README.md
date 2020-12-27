# packet-doubler

- origin: net-speeder, fork from https://github.com/snooda/net-speeder
- purpose: double the outgoing traffic according to BPF rule
- example: `PacketDoubler eth0 "tcp src port 443"`
- release: https://github.com/SiyaCheung/packet-doubler/releases/

## runtime

### runtime dependants
- glibc

### static build, no longer require 3rd lib

```
ldd PacketDoubler 
        linux-vdso.so.1 (0x00007ffdbc1ce000)
        libc.so.6 => /lib/x86_64-linux-gnu/libc.so.6 (0x00007f102aa5e000)
        /lib64/ld-linux-x86-64.so.2 (0x00007f102acbc000)
```

## build 

### build dependants
- libpcap.a
- libnet.a

### build release
- `mkdir -p build && cd build`
- `cmake ../ -DCMAKE_BUILD_TYPE=Release`
- `make`

## etc:
- use `-DCOOKED` macro to enable cooked package filter
- use `ethtool -K $ETH_NAME tso off` to disable TSO
