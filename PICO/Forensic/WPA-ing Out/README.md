# WPA-ing Out

- **CTF:** picoCTF
- **Category:** Forensic

## Write-up

### aircrack-ngでパスワードを解析

1. 配布された`wpa-ing_out.pcap`に対して，`aircrack-ng`で辞書攻撃を行う．パスワード候補には`rockyou.txt`を使用する．

   ```bash
   aircrack-ng -w /usr/share/wordlists/rockyou.txt wpa-ing_out.pcap
   ```

2. 読み込み結果から，ネットワーク名（ESSID）が`Gone_Surfing`であり，WPAのハンドシェイクが1件含まれていることがわかる．このハンドシェイクを使って，辞書内のパスワード候補が正しいかを検証する．

   ```text
   Read 23523 packets.

      #  BSSID              ESSID                     Encryption

      1  00:5F:67:4F:6A:1A  Gone_Surfing              WPA (1 handshake)
   ```

3. 解析結果に`KEY FOUND! [ mickeymouse ]`と表示されるため，Wi-Fiのパスワードは`mickeymouse`だとわかる．`Current passphrase`は検証中の候補を表し，パスワードの発見を示すのは`KEY FOUND!`の表示である．

   ```text
   KEY FOUND! [ mickeymouse ]
   ```

4. 見つかったパスワードを`academyF{}`で囲み，flagとする．

### Flag

`FLAG : academy{mickeymouse}`
