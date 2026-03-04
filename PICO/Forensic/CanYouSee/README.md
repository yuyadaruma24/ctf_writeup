# CanYouSee

- **CTF:** picoCTF 2024
- **Category:** Forensic
- **Difficulty:** Easy

### Description
How about some hide and seek?

### hint
1. How can you view the information about the picture?
2. If something isn't in the expected form, maybe it deserves attention?

### write-up
1. `exiftool`でがファイルのメタデータを確認すると`Attribution URL`のところにbase64でエンコードされたであろう文字列が見つかる
<img width="1095" height="725" alt="Image" src="https://github.com/user-attachments/assets/89023a89-4823-4377-a8b4-936cf55f962a" />
2. base64で復号するとflagを見つけることができる

### flag
`FLAG : picoCTF{ME74D47A_HIDD3N_d8c381fd}`