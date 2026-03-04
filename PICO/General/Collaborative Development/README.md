# Collaborative Development

- **CTF:** picoCTF 2024
- **Category:** General
- **Difficulty:** Easy

### Description
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?
You can download the challenge files here:

### Author
Jeffery John

### hint
1. `git branch -a` will let you see available branches
2. How can file 'diffs' be brought to the main branch? Don't forget to `git config`!
3. Merge conflicts can be tricky! Try a text editor like nano, emacs, or vim.

### write-up 
1. `git branch -a`で3つのbranchがあることがわかる
2. `git merge`やテキストエディタなどでそれぞれのprintで表示される文字列をつなげることでflagを取得できる

### FLAG
`FLAG : picoCTF{t3@mw0rk_m@k3s_th3_dr3@m_w0rk_2c91ca76}`