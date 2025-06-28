# Secret of the Polyflot

- **CTF:** picoCTF 2025
- **Category:** Forensic
- **Difficulty:** Easy

## Description

The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?
Download the suspicious file here.

## Author
syreal

## hint
1. This problem can be solved by just opening the file in different ways


## Write-up
1. 与えられたファイル"flag2of2-fianl.pdf"には`1n_pn9_&_pdf_53b741d6}`が記載されていた．
2. このpdfファイルは.pngファイルである可能性が高い．
   ```
   file flag2of2-final.pdf 
   ```
   `flag2of2-final.pdf: PNG image data, 50 x 50, 8-bit/color RGBA, non-interlaced`
3. 拡張子を.pngにして中をのぞくと`picoCTF{f1u3n7_`となっていたため2つをつなげるとflagを入手できる．

### Flag
`FLAG : picoCTF{f1u3n7_1n_pn9_&_pdf_53b741d6}`
