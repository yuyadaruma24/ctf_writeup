# interencdec

- **CTF:** picoCTF 2025
- **Category:** cyptography
- **Difficulty:** Easy

### Description

Can you get the real meaning from this file.
Download the file here.

### Author
NGIRIMANA Schadrack

### hint
1. Engaging in various decoding processes is of utmost importance

### Write-up
1. ファイルの中身は`YidkM0JxZGtwQlRYdHFhR3g2YUhsZmF6TnFlVGwzWVROclgyeG9OakJzTURCcGZRPT0nCg==`
2. base64っぽそうなのでbase64でデコードすると次のが得られた`b'd3BqdkpBTXtqaGx6aHlfazNqeTl3YTNrX2xoNjBsMDBpfQ=='`
3. 先頭の`b'`が意図的に付け足されている可能性があるためそれを除去してもう一度base64でデコード`wpjvJAM{jhlzhy_k3jy9wa3k_lh60l00i}`が得られる
4. タグにCAESARがあるためシーザー暗号でデコードするとflagが得られる
   ![image](https://github.com/user-attachments/assets/d0667573-41ed-475f-b5a5-e183f6e8f1eb)

### Flag
`FLAG : picoCTF{caesar_d3cr9pt3d_ea60e00b}`
