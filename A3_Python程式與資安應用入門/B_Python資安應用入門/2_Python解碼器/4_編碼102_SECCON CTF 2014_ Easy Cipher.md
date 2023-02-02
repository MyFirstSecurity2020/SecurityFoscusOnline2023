# 編碼102:SECCON CTF 2014: Easy Cipher 
```
87 101 108 1100011 0157 6d 0145 040 116 0157 100000 0164 104 1100101 32 0123 69 67 0103 1001111 1001110 040 062 060 49 064 100000 0157 110 6c 0151 1101110 101 040 0103 1010100 70 101110 0124 1101000 101 100000 1010011 1000101 67 0103 4f 4e 100000 105 1110011 040 116 1101000 0145 040 1100010 0151 103 103 0145 1110011 0164 100000 1101000 0141 99 6b 1100101 0162 32 0143 111 1101110 1110100 101 0163 0164 040 0151 0156 040 74 0141 1110000 1100001 0156 056 4f 0157 0160 115 44 040 0171 1101111 117 100000 1110111 0141 0156 1110100 32 0164 6f 32 6b 1101110 1101111 1110111 100000 0164 1101000 0145 040 0146 6c 97 1100111 2c 100000 0144 111 110 100111 116 100000 1111001 6f 117 63 0110 1100101 0162 0145 100000 1111001 111 117 100000 97 114 0145 46 1010011 0105 0103 67 79 1001110 123 87 110011 110001 67 110000 1001101 32 55 060 100000 110111 0110 110011 32 53 51 0103 0103 060 0116 040 5a 0117 73 0101 7d 1001000 0141 1110110 1100101 100000 102 0165 0156 33
```
```
[參考解答]
http://4ngelboy.blogspot.com/2014/12/span-display-block-overflow-hidden.html


很明顯的這段文字是由四種不同進位的數字所組成，必須判斷出他是屬於哪個進位在轉換成 ASCII code 印出，
不過起初在解的時候沒有發現有特別的規則，導致剛開始一直判別不出來，仔細觀察過後可發現每個進位的數字有不同的特徵：
2 進位：字串長度 >= 6
8 進位：開頭一定是 0
16 進位：必有英文字 6d
10 進位：上述之外的

https://github.com/S42X/CTF/blob/master/SECCON/EasyCipher.md
```
```

ord('a')

oct(10)

hex(10)

```
```
https://www.quora.com/How-do-I-convert-hex-into-a-string-using-Python

https://stackoverflow.com/questions/18806772/most-pythonic-way-to-convert-a-string-to-a-octal-number

http://mini-stable.blogspot.com/2015/03/python-int-hex-char-string.html
```
### Python - int, hex, char, string的轉換
```
Int to Hex:   hex(97)  # '0x61'
Int to Char:   chr(97)  # 'a'
Int to String:  str(97)  # '97'
Hex to int:  int('0x61', 16)  # 97
Hex to Char:   chr(int('0x61', 16)) # 'a'
Hex to String:
string = '61626364'
''.join(chr(int(string[i:i+2], 16)) for i in range(0, len(string), 2))  # 'abcd'
```
```
Char to Int: ord('a')  # 97
Char to Hex: hex(ord('a'))  # '0x61'
String to Int: int('97')  # 97
String to Hex:

string = 'abcd'
''.join([hex(ord(x))[2:] for x in string])  # '61626364'
```

```
string = '61626364'
''.join(chr(int(string[i:i+2], 16)) for i in range(0, len(string), 2))  # 'abcd'
```
### 使用python內建模組 binascii
```
https://docs.python.org/2/library/binascii.html
```
```
#coding:utf-8
import binascii
a = 'HappyCTF{Useful tools binascii}'
b = binascii.b2a_hex(a)
print b
print binascii.a2b_hex(b)
```
```
Python2 Online
https://paiza.io/en/languages/python
```

```
https://nandynarwhals.org/seccon2014-easycipher/
```
```
#!/usr/bin/python

vals = "87 101 108 1100011 0157 6d 0145 040 116 0157 100000 0164 104 1100101 32 0123 69 67 0103 1001111 1001110 040 062 060 49 064 100000 0157 110 6c 0151 1101110 101 040 0103 1010100 70 101110 0124 1101000 101 100000 1010011 1000101 67 0103 4f 4e 100000 105 1110011 040 116 1101000 0145 040 1100010 0151 103 103 0145 1110011 0164 100000 1101000 0141 99 6b 1100101 0162 32 0143 111 1101110 1110100 101 0163 0164 040 0151 0156 040 74 0141 1110000 1100001 0156 056 4f 0157 0160 115 44 040 0171 1101111 117 100000 1110111 0141 0156 1110100 32 0164 6f 32 6b 1101110 1101111 1110111 100000 0164 1101000 0145 040 0146 6c 97 1100111 2c 100000 0144 111 110 100111 116 100000 1111001 6f 117 63 0110 1100101 0162 0145 100000 1111001 111 117 100000 97 114 0145 46 1010011 0105 0103 67 79 1001110 123 87 110011 110001 67 110000 1001101 32 55 060 100000 110111 0110 110011 32 53 51 0103 0103 060 0116 040 5a 0117 73 0101 7d 1001000 0141 1110110 1100101 100000 102 0165 0156 33"
vals = vals.split()

def contains_hex(val):
    h = "abcdef"
    for i in val:
        if i in h:
            return True
    return False

def main():
    flag = []
    for i in vals:
        if len(i) > 5:
            flag.append(int(i, 2))
        elif i[0] == "0":
            flag.append(int(i, 8))
        elif contains_hex(i):
            flag.append(int(i, 16))
        else:
            flag.append(int(i))
    print("%s" % "".join(map(chr, flag)))

if __name__ == "__main__":
    main()
```
### 使用Python正規表達法Regular expression
- [Python正規表達法](https://docs.python.org/zh-tw/3/howto/regex.html#:~:text=%E6%AD%A3%E8%A6%8F%E8%A1%A8%E7%A4%BA%E5%BC%8F(%E4%B9%9F%E7%A8%B1,TeX%20%E5%91%BD%E4%BB%A4%E6%88%96%E4%BB%BB%E4%BD%95%E6%9D%B1%E8%A5%BF%E3%80%82)

- [解答資料來源](https://wiremask.eu/writeups/seccon-ctf-2014-crypto-100-easy-cipher/)
```
#!/usr/bin/env python
import re
import sys

message = "87 101 108 1100011 0157 6d 0145 040 116 0157 100000 0164 104 1100101 32 0123 69 67 0103 1001111 1001110 040 062 060 49 064 100000 0157 110 6c 0151 1101110 101 040 0103 1010100 70 101110 0124 1101000 101 100000 1010011 1000101 67 0103 4f 4e 100000 105 1110011 040 116 1101000 0145 040 1100010 0151 103 103 0145 1110011 0164 100000 1101000 0141 99 6b 1100101 0162 32 0143 111 1101110 1110100 101 0163 0164 040 0151 0156 040 74 0141 1110000 1100001 0156 056 4f 0157 0160 115 44 040 0171 1101111 117 100000 1110111 0141 0156 1110100 32 0164 6f 32 6b 1101110 1101111 1110111 100000 0164 1101000 0145 040 0146 6c 97 1100111 2c 100000 0144 111 110 100111 116 100000 1111001 6f 117 63 0110 1100101 0162 0145 100000 1111001 111 117 100000 97 114 0145 46 1010011 0105 0103 67 79 1001110 123 87 110011 110001 67 110000 1001101 32 55 060 100000 110111 0110 110011 32 53 51 0103 0103 060 0116 040 5a 0117 73 0101 7d 1001000 0141 1110110 1100101 100000 102 0165 0156 33"
codes = message.split()

for i, code in enumerate(codes):
    if re.match("^[01]+$", code)  and code[0] == "1" and len(code) > 3:
        sys.stdout.write(chr(int(code, 2)))
    elif re.match("^[0-9]+$", code) and code[0] == "0":
        sys.stdout.write(chr(int(code, 8)))
    elif re.match("^[0-9]+$", code):
        sys.stdout.write(chr(int(code, 10)))
    else:
        sys.stdout.write(chr(int(code, 16)))

```


