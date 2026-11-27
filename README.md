# dns-captures

Reading DNS header flags in tcpdump: QR, AA, TC, RD, RA and RCODE, with filters and live captures on Ubuntu.

A self-directed lab on one Ubuntu VM. Each flag is checked with a tcpdump mask-and-target filter against real traffic that I triggered with dig.

## What's covered
- Byte 10 of the DNS header: QR, AA, TC, RD
- Byte 11: RA and RCODE (NXDOMAIN)
- The OPT record and how the advertised UDP size decides whether a reply is truncated

## Tools
tcpdump, dig, Ubuntu

## How the filters work
tcp-style masks on the DNS header: `udp[10] & MASK == TARGET`, with the DNS header starting at `udp[8]`.
