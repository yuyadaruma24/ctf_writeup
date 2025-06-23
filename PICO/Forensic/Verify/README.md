# Verify

- **CTF:** picoCTF 2025
- **Category:** Forensic
- **Difficulty:** Easy

## Description
People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.
Additional details will be available after launching your challenge instance.


## Author
 Jeffery John

## hint
1. Checksums let you tell if a file is complete and from the original distributor. If the hash doesn't match, it's a different file.
2. You can create a SHA checksum of a file with sha256sum <file> or all files in a directory with `sha256sum <directory>/*`.
3. Remember you can pipe the output of one command to another with |. Try practicing with the 'First Grep' challenge if you're stuck!


## Write-up

### checksumを確認
1. `sha256sum flags/* | grep "467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02"`を用いてチェックサムが同じファイルを`/files`から探す
2. `467a10447deb3d4e17634cacc2a68ba6c2bb62a6637dad9145ea673bf0be5e02  files/c6c8b911`と出力されるので`c6c8b911`が該当ファイルだとわかる
3. `./decrypt.sh files/c6c8b911`を用いることでflagを得ることが出来る．

### Flag
`FLAG : picoCTF{trust_but_verify_c6c8b911}`
