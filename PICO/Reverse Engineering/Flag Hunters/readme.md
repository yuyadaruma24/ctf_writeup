# Flag Hunters

- **CTF:** picoCTF 2025
- **Category:** Reverse Engineering
- **Difficulty:** Easy

### Description

Lyrics jump from verses to the refrain kind of like a subroutine call. There's a hidden refrain this program doesn't print by default. Can you get it to print it? There might be something in it for you.
The program's source code can be downloaded here.
Connect to the program with netcat:
$ nc verbal-sleep.picoctf.net 59014

### Author
syreal

### hint
1. This program can easily get into undefined states. Don't be shy about Ctrl-C.
2. Unsanitized user input is always good, right?
3. Is there any syntax that is ripe for subversion?


### Write-up

1.  **`lyrics-reader.py`** を開く。

2.  コードを確認するとフラグが`secret_intro`という変数に格納され、これが`song_flag_hunters`という巨大な歌詞文字列の先頭に結合されていることがわかる．

  '''
  secret_intro = \
  ''Pico warriors rising, puzzles laid bare,
  Solving each challenge with precision and flair.
  With unity and skill, flags we deliver,
  The ether’s ours to conquer, ''\
  + flag + '\n'
  
  
  song_flag_hunters = secret_intro +\
  '''    

3.  歌詞を表示する箇所が下記のように書かれている．

  ```
  # Print lyrics
    line_count = 0
    lip = start
    while not finished and line_count < MAX_LINES:
      line_count += 1
      for line in song_lines[lip].split(';'):
        if line == '' and song_lines[lip] != '':
          continue
        if line == 'REFRAIN':
          song_lines[refrain_return] = 'RETURN ' + str(lip + 1)
          lip = refrain
        elif re.match(r"CROWD.*", line):
          crowd = input('Crowd: ')
          song_lines[lip] = 'Crowd: ' + crowd
          lip += 1
        elif re.match(r"RETURN [0-9]+", line):
          lip = int(line.split()[1])
        elif line == 'END':
          finished = True
        else:
          print(line, flush=True)
          time.sleep(0.5)
          lip += 1
  ```
  
4. 　`crowd = input('Crowd: ')`でユーザーが入力した情報を`song_lines[lip] = 'Crowd: ' + crowd`歌に入れている．
   
5. 　下記のようなコードで書かれいているため，`something_String;RETURN 0`のように入力すると**flag**を得ることが出来る．
   
  ```
  for line in song_lines[lip].split(';'):
          if line == '' and song_lines[lip] != '':
            continue
   ...
   ...
  elif re.match(r"RETURN [0-9]+", line):
            lip = int(line.split()[1])
  ```


  
### Flag
`FLAG : picoCTF{70637h3r_f0r3v3r_05182f4f}`
