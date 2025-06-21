# EVEN RSA CAN BE BROKEN???

- **CTF:** picoCTF 2025
- **Category:** cyptography
- **Difficulty:** Easy

## Description

This service provides you an encrypted flag. Can you decrypt it with just N & e?
Connect to the program with netcat:
$ nc verbal-sleep.picoctf.net 51434
The program's source code can be downloaded here.

## Author
Michael Crotty

## hint
1. How much do we trust randomness?
2. Notice anything interesting about N?
3. Try comparing N across multiple requests

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
