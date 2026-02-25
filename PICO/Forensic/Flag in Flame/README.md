# Flag in Flame

- **CTF:** picoCTF 2025
- **Category**:*Forensics* 
- **Difficulty:** Easy

## Description
The SOC team discovered a suspiciously large log file after a recent breach. When they opened it, they found an enormous block of encoded text instead of typical logs. Could there be something hidden within? Your mission is to inspect the resulting file and reveal the real purpose of it. The team is relying on your skills to uncover any concealed information within this unusual log.
Download the encoded data here: Logs Data. Be prepared—the file is large, and examining it thoroughly is crucial .

## Author  
Prince Niyonshuti N.
## hint  
Use base64 to decode the data and generate the image file.

## write-up
1. `base64`でデコードしたところ画像が生成される．  <img width="896" height="1152" alt="download" src="https://github.com/user-attachments/assets/e863005d-edb3-4173-8d7f-1a6fb7c77dc7" />
2. 画像内には**7069636F4354467B666F72656E736963735F616E616C797369735F69735F616D617A696E675F32346431363839357D**が記載されている．
3. 16進数っぽいのでasciiコードで変換するとflagが見つかる．

### Flag
`FLAG : picoCTF{forensics_analysis_is_amazing_24d16895}`
