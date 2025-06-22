# Ph4nt0m 1ntrud3r

- **CTF:** picoCTF 2025
- **Category:** Forensic
- **Difficulty:** Easy

## Description

A digital ghost has breached my defenses, and my sensitive data has been stolen! 😱💻 Your mission is to uncover how this phantom intruder infiltrated my system and retrieve the hidden flag.
To solve this challenge, you'll need to analyze the provided PCAP file and track down the attack method. The attacker has cleverly concealed his moves in well timely manner. Dive into the network traffic, apply the right filters and show off your forensic prowess and unmask the digital intruder!
Find the PCAP file here Network Traffic PCAP file and try to get the flag.

## Author
Prince Niyonshuti N.

## hint
1. Filter your packets to narrow down your search.
2. Attacks were done in timely manner.
3. Time is essential

## Write-up

### wiresharkで確認
1. パケットを時系列順に並べる
2. ペイロード部分に
 ```
cGljb0NURg==

ezF0X3c0cw==

bnRfdGg0dA==

XzM0c3lfdA==

YmhfNHJfOQ==

NjZkMGJmYg==

fQ==
```
3. base64でデコードするとflagを見つけることが出来る．

### Flag
`FLAG : picoCTF{1t_w4snt_th4t_34sy_tbh_4r_966d0bfb}`
