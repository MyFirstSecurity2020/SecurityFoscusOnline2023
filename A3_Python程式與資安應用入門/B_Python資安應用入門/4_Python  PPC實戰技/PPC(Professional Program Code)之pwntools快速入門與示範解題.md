# PWNTOOLS
- 官方說明
  - pwntools is a CTF framework and exploit development library. 
  - Written in Python, it is designed for rapid prototyping and development, and intended to make exploit writing as simple as possible.
- [官方GITHUB網址](https://github.com/Gallopsled/pwntools)
- [官方教學pwntools-tutorial(英文版)](https://github.com/Gallopsled/pwntools-tutorial#readme)
- [官方使用手冊(英文版)](https://docs.pwntools.com/en/stable/)

# PWNTOOLS安裝(本課程提供的環境已經安裝好了)
## 1.撰寫安裝SCRIPT: XXX.sh
```
apt-get update
apt-get install python3 python3-pip python3-dev git libssl-dev libffi-dev build-essential
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade pwntools
```
## 2.執行: bash XXX.sh
```
root@kali:~# gedit pwntools_install.sh
root@kali:~# bash pwntools_install.sh 
```
```
一路yes到底
```
# 3.查看各種參數 pwn -h
- [ pwn  Command Line Tools](https://docs.pwntools.com/en/latest/commandline.html#pwn)
```
usage: pwn [-h]
           {asm,checksec,constgrep,cyclic,debug,disasm,disablenx,elfdiff,elfpatch,errno,hex,
            phd,pwnstrip,scramble,shellcraft,template,unhex,update,version}
           ...

Pwntools Command-line Interface

positional arguments:
  {asm,checksec,constgrep,cyclic,debug,disasm,disablenx,elfdiff,elfpatch,errno,hex,phd,pwnstrip,scramble,
    shellcraft,template,unhex,update,version}
    asm                 Assemble shellcode into bytes    <=== 重要
    checksec            Check binary security settings   <=== 重要
    constgrep           Looking up constants from header files. Example:
                        constgrep -c freebsd -m ^PROT_ '3 + 4'
    cyclic              Cyclic pattern creator/finder    <=== 重要
    debug               Debug a binary in GDB
    disasm              Disassemble bytes into text format  <=== 重要
    disablenx           Disable NX for an ELF binary
    elfdiff             Compare two ELF files
    elfpatch            Patch an ELF file
    errno               Prints out error messages
    hex                 Hex-encodes data provided on the command line or stdin
    phd                 Pwnlib HexDump
    pwnstrip            Strip binaries for CTF usage
    scramble            Shellcode encoder
    shellcraft          Microwave shellcode -- Easy, fast and delicious
    template            Generate an exploit template
    unhex               Decodes hex-encoded data provided on the command line
                        or via stdin.
    update              Check for pwntools updates
    version             Pwntools version

optional arguments:
  -h, --help            show this help message and exit
```

## pwntools 常用技術
- 載入pwntools套件 ==> from pwn import *  # 可將所有子模組和一些常用的系統函數庫導入
- 建立與程式連結(connection) 
  - 與遠端程式(使用remote())
    - conn = remote('ip_address', port_num)
    - conn = remote('173.4.5.1', 8888) 
  - 與本地端程式(使用process())==> conn = process('./pwn1')
- 接收資料 receive
  - recv(numb=1096, timeout=default)：接收指定位元組數的資料
  - recvall()：接收資料直到 EOF
  - recvline(keepends=True)：接收一行，可選擇是否保留行尾的 \n
  - recvlines(N):接收 N行輸出
  - recvrepeat(timeout=default)：接收資料直到 EOF(END of FILE) 或 timeout
  - recvuntil(delims, timeout=default)：接收資料直到 delims 出現
- 傳資料
  - send(data)：發送資料
  - sendline(data)：發送一行，預設會在行尾加 \n
  - sendlineafter(delims, 要送出的資料)：從 delims 出現後,將要送出的資料 傳送給程式
- 互動 ==> conn.interactive()
  - 可同時對遠端系統讀寫資料
  - 相當於回到 shell 模式進行互動
  - 在取得 shell 之後調用 

  [pwntools工具的使用](https://blog.csdn.net/A951860555/article/details/110990925)
  
## PPC2_3rd 分析與解題
```
可以幫我找出第三大的數字嗎?

nc 120.114.62.216 2400
```
### 先連線看看 nc 120.114.62.216 2400
```
===== Welcome to 3rd Game =====
Can you help me find the 3rd largest number?
All numbers are unique
----- Example -----
numbers : 1 9 7 3 6 2
answer : 6
----- Now You Turn -----
numbers : 26101 59484 71067 3659 60676 16911 90992 84588 36095 6072 85067 44556 28648 30530 3723 85728 17658 71651 26494 82346 49468 40305 83547 66994 38093 23009 10713 11613 57481 66864 78220 16603 78326 93108 60024 90354 72992 78097 14177 36505 42824 35583 84293 94194 86569 17291 60452 95279 62714 29826 62555 50916 64029 29753 598 22380 22623 84748 38691 85756 25071 59893 32306 43447 65107 89621 67137 21846 40460 30377 94665 5229 41864 5549 47196 84516 98601 14389 59604 76420 60875 87412 67073 57658 50835 56111 27423 67654 93585 16019 39156 41773 82041 39784 38452 7709 24484 64275 16990 30925
answer :
```
## 運算思維與分析
### 前7行都不要
```
===== Welcome to 3rd Game =====
Can you help me find the 3rd largest number?
All numbers are unique
----- Example -----
numbers : 1 9 7 3 6 2
answer : 6
----- Now You Turn -----
```
### 運算思維
```
前7行都不要
第8行 ==> 要數字 ==> 然後排序(由小排到大)==> 再取倒數第3個 就是答案
把數字轉成字串
送出答案
```
### 程式實作
```
#!/usr/bin/env python3
from pwn import *

r = remote(‘題目的IP',題目的PORT)  <==

r.recvlines(7)

r.recvuntil('numbers : ')
numbers = map(int, r.recvline().strip().split())
ans = sorted(numbers)[-3]
r.sendlineafter('answer : ', str(ans))

r.interactive()
```
### 最後解答
```
#!/usr/bin/env python3
from pwn import *

r = remote(‘題目的IP',題目的PORT)

r.recvlines(7)

r.recvuntil('numbers : ')
numbers = map(int, r.recvline().strip().split())
ans = sorted(numbers)[-3]
r.sendlineafter('answer : ', str(ans))

r.interactive()
```
### 執行畫面
```
python3 test.py 


[+] Opening connection to 120.114.62.216 on port 2400: Done
[*] Switching to interactive mode
CTF{>>>>>>>解答在這裡>>>>>>>>>}  <====解答在此
[*] Got EOF while reading in interactive
```


