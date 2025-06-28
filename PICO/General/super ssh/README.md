# super SSH

- **CTF:** picoCTF 2025
- **Category:** General
- **Difficulty:** Easy

### Description
Using a Secure Shell (SSH) is going to be pretty important.
Additional details will be available after launching your challenge instance.

### Author
Jeffery John

### hint
1. [The cat command will let you read a file, but that won't help you here!](https://linux.die.net/man/1/ssh)
2. You can try logging in 'as' someone with <user>@titan.picoctf.net
3. How could you specify the port?
4. Remember, passwords are hidden when typed into the shell

### Write-up
1. ```
   ssh ctf-player@titan.picoctf.net -p 53563
   ``` を実行する
2. `ctf-player@titan.picoctf.net's password:`
と表示されるのでパスワードを入力するとflagを得ることが出来る

### Flag
`FLAG : picoCTF{s3cur3_c0nn3ct10n_8306c99d}`
