# Corrupted file

- **CTF:** picoCTF 2025
- **Category**:*Forensics* 
- **Difficulty:** Easy

## Description
This file seems broken... or is it? Maybe a couple of bytes could make all the difference. Can you figure out how to bring it back to life?
Download the file here.

## Author
Yahaya Meddy

## hint
1. Try checking the file’s header.
2. JPEG
3. Tools like xxd or hexdump can help you inspect and edit file bytes.

## write-up
1. ファイルのヘッダ情報を確認すると**jfif**の文字が
<img width="1738" height="609" alt="スクリーンショット 2026-02-26 000408" src="https://github.com/user-attachments/assets/9dcddb87-f2f0-4414-9d40-0a74b1cac4e0" />

2. 拡張子を.jpegに変えてみるとエラー
3. `xxd`で16進数で調べてみると**5c78**がjpegは**ffd8**で始まるので編集してみる
<img width="2240" height="1328" alt="スクリーンショット 2026-02-26 000957" src="https://github.com/user-attachments/assets/d35c598b-c4b8-4241-be6b-78d31017fb78" />

4. flagが出てきた
<img width="809" height="510" alt="スクリーンショット 2026-02-26 001814" src="https://github.com/user-attachments/assets/938821a4-bcff-4740-8466-3a855e453a9d" />

### flag
`FLAG : picoCTF{r3st0r1ng_th3_by73s_752d2c00}`


### 捕捉
- ファイル形式とヘッダ（マジックナンバー）一覧

| ファイル形式 | 拡張子 | ヘッダ (16進数/Hex) | 備考 |
| :--- | :--- | :--- | :--- |
| **JPEG** | `.jpg`, `.jpeg` | `FF D8 FF` | |
| **PNG** | `.png` | `89 50 4E 47 0D 0A 1A 0A` | `.PNG....` |
| **GIF** | `.gif` | `47 49 46 38` | GIF87a/89a |
| **PDF** | `.pdf` | `25 50 44 46` | %PDF |
| **ZIP / Office** | `.zip`, `.docx`, `.xlsx` | `50 4B 03 04` | PK.. |
| **EXE (Windows)** | `.exe` | `4D 5A` | MZ |
| **BITMAP** | `.bmp` | `42 4D` | BM |
| **MP3** | `.mp3` | `FF FB` | |
| **GZIP** | `.gz` | `1F 8B` | |
| **MP4** | `.mp4` | `66 74 79 70` | ftyp |
