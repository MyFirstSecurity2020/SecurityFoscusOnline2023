# 1_PWNTOOLS
- 官方說明
  - pwntools is a CTF framework and exploit development library. 
  - Written in Python, it is designed for rapid prototyping and development, and intended to make exploit writing as simple as possible.
- [官方GITHUB網址](https://github.com/Gallopsled/pwntools)
- [官方教學pwntools-tutorial(英文版)](https://github.com/Gallopsled/pwntools-tutorial#readme)
- [官方使用手冊(英文版)](https://docs.pwntools.com/en/stable/)

# 2_PWNTOOLS安裝(本課程提供的環境已經安裝好了)
## 撰寫安裝SCRIPT: XXX.sh
```
apt-get update
apt-get install python3 python3-pip python3-dev git libssl-dev libffi-dev build-essential
python3 -m pip install --upgrade pip
python3 -m pip install --upgrade pwntools
```
## 執行: bash XXX.sh
```
root@kali:~# gedit pwntools_install.sh
root@kali:~# bash pwntools_install.sh 
```
```
一路yes到底
```
# 3.查看各種參數 pwn -h
```
Command Line Tools
https://docs.pwntools.com/en/latest/commandline.html#pwn
```
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
