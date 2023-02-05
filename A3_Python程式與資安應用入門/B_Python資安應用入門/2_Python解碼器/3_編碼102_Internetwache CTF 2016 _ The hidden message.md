# 編碼102:Internetwache CTF 2016 : The hidden message
```
My friend really can’t remember passwords. 
So he uses some kind of obfuscation. 
Can you restore the plaintext?

Attachment: misc50.zip
```
把misc50.zip解壓縮後可以得到:
```
0000000 126 062 126 163 142 103 102 153 142 062 065 154 111 121 157 113
0000020 122 155 170 150 132 172 157 147 123 126 144 067 124 152 102 146
0000040 115 107 065 154 130 062 116 150 142 154 071 172 144 104 102 167
0000060 130 063 153 167 144 130 060 113 012
0000071
```

```
參考解答(writeups)
https://0x90r00t.com/2016/02/22/internetwache-ctf-2016-misc-50-the-hidden-message-write-up/
```
## 第一種解法:使用線上工具解

步驟一：線上工具
```
http://www.unit-conversion.info/texttools/octal/

V2VsbCBkb25lIQoKRmxhZzogSVd7TjBfMG5lX2Nhbl9zdDBwX3kwdX0K
```
步驟二：
```
import base64

encoded_data = b'V2VsbCBkb25lIQoKRmxhZzogSVd7TjBfMG5lX2Nhbl9zdDBwX3kwdX0K'
decoded_data = base64.b64decode(encoded_data)
print('Encoded :', encoded_data)
print('Decoded :', decoded_data)
```
## 第二種解法

### 先試看看是不是如你所想的一般.......
```
#!/usr/bin/python

c = '126 062 126 163 142 103 102 153 142 062 065 154 111 121 157 113 122 155 170 150 132 172 157 147 123 126 144 067 124 152 102 146 115 107 065 154 130 062 116 150 142 154 071 172 144 104 102 167 130 063 153 167 144 130 060 113 012'

flag = ""

for _ in c.split(' '):
  flag += chr(int(_,8))

print(flag)
```
## 接著就可以完成大業......
```
#!/usr/bin/python
import base64

c = '126 062 126 163 142 103 102 153 142 062 065 154 111 121 157 113 122 155 170 150 132 172 157 147 123 126 144 067 124 152 102 146 115 107 065 154 130 062 116 150 142 154 071 172 144 104 102 167 130 063 153 167 144 130 060 113 012'

flag = ""

for _ in c.split(' '):
  flag += chr(int(_,8))
  

solution = base64.b64decode(flag)
print(solution)
```
