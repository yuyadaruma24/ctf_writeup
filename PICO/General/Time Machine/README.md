# Time Machine

- **CTF:** picoCTF 2025
- **Category:** General
- **Difficulty:** Easy

### Description

What was I last working on? I remember writing a note to help me remember...
You can download the challenge files here:
challenge.zip

### Author
Jeffery John

### hint
1. The cat command will let you read a file, but that won't help you here!
2. Read the chapter on Git from the picoPrimer here.
3. When committing a file with git, a message can (and should) be included.


### Write-up
1. ```git log message.txt``` を実行する
2.
    ```
   git log message.txt
   commit 10228f3d6437701ef5aaac04213757031f30ebec (HEAD -> master)
   Author: picoCTF <ops@picoctf.com>
   Date:   Tue Mar 12 00:07:24 2024 +0000

    picoCTF{t1m3m@ch1n3_8defe16a}

   ```
flagを得ることが出来る．

### Flag
`FLAG : picoCTF{t1m3m@ch1n3_8defe16a}`
