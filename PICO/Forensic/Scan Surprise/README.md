# Scan Surprise

- **CTF:** picoCTF 2025
- **Category:** Forensic
- **Difficulty:** Easy

## Description

I've gotten bored of handing out flags as text. Wouldn't it be cool if they were an image instead?
You can download the challenge files here:
challenge.zip
Additional details will be available after launching your challenge instance.

## Author
Prince Niyonshuti N.

## hint
1. QR codes are a way of encoding data. While they're most known for storing URLs, they can store other things too.
2. Mobile phones have included native QR code scanners in their cameras since version 8 (Oreo) and iOS 11
3. If you don't have access to a phone, you can also use zbar-tools to convert an image to text


## Write-up

### wiresharkで確認
1. `flag.pmg`はQRコードでありそれを読み取るとflagを入手できる．

### Flag
`FLAG : picoCTF{p33k_@_b00_3f7cf1ae}`
