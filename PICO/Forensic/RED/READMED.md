# RED

- **CTF:** picoCTF 2025
- **Category**:*Forensics* 
- **Difficulty:** Easy

## Description

RED, RED, RED, RED
Download the image: red.png

## Author
Shuailin Pan (LeConjuror)
## hint
1. The picture seems pure, but is it though?
2. Red?Ged?Bed?Aed?
3. Check whatever Facebook is called now.

## Write-up

### red.pngを解析
![red](https://github.com/user-attachments/assets/5a0e2956-8ab9-42d0-911c-3538c282daee)

1. `exiftool`で**CHECKLSB**が出現した．
2. `zsteg -a`を用いたところ`cGljb0NURntyM2RfMXNfdGgzX3VsdDFtNHQzX2N1cjNfZjByXzU0ZG4zNTVffQ==`が見られた．
3. base64でエンコードされていそうなのでデコードするとflagが見つかった．

### LSBとは
least signficant bitの略で，**末尾のビットのこと**  
LSB方式のsteganographyとはLSBを書き換えることで、あまり見た目に影響させずにデータを隠すものである  
参考  
https://tkmr.hatenablog.com/entry/2014/07/28/223854#:~:text=LSB%E3%81%A8%E3%81%AFleast%20significant,%E3%82%92%E9%9A%A0%E3%81%99%E3%82%82%E3%81%AE%E3%81%A7%E3%81%82%E3%82%8B%E3%80%82

### Flag
`FLAG : picoCTF{r3d_1s_th3_ult1m4t3_cur3_f0r_54dn355_}`
