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

https://zenn.dev/spacemarket/articles/40be4b419fe1a6 を参照  

n,e,cryptdataがわかっている状態

### 捕捉：RSA暗号の作成・復号式
1. 2つの異なる素数pとqを選ぶ
2. n = p * q
3. f = (p-1) * (q-1)
4. 素数eを選ぶ
5. d = e**-1(mod(f)
暗号化
6. C = M**e(mod(f)
復号化
7. M = C**d(mod(f))

### dを求めることで復号が可能
1. `d = pow(e, -1, f)` -> ((e ** -1) % f)
2. `m = pow(c, d ,n)`をすることで復号化されたメッセージの整数表現を得られる
3. 得られたmを`print(long_to_bytes(m).decode())`を用いてバイト化，そして復号することでflagを得られる


### Flag
`FLAG : picoCTF{tw0_1$_pr!m381772be5}`
