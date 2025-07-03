# endianness

- **CTF:** picoCTF 2025
- **Category:** General
- **Difficulty:** Easy

### Description
Know of little and big endian?
Source
nc titan.picoctf.net 50367

### Author
Nana Ama Atombo-Sackey

### hint
1. You might want to check the ASCII table to first find the hexadecimal representation of characters before finding the endianness.
2. Read more about how endianness here

### Write-up
エンディアンについての説明  
https://ponsuke-tarou.hatenablog.com/entry/2017/10/09/224023

1. 与えられた`sqbdd`をリトルエンディアン，ビッグエンディアンにする問題
2. 文字列を16進数に変換すると`73,71,62,64,64`
3. リトルエンディアンは16進数を逆にすればよいので`64,64,62,71,73`
4. ビッグエンディアンは`73,71,62,64,64`
5. flagを入手できる
   ![image](https://github.com/user-attachments/assets/1cd6430b-aee5-4e03-8693-2915e0d2814f)


### Flag
`FLAG : picoCTF{3ndi4n_sw4p_su33ess_02999450}`
