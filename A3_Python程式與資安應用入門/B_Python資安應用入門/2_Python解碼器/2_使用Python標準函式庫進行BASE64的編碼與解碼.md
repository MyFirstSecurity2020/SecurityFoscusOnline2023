### [2]使用Python標準函式庫進行BASE64的編碼與解碼 [YOUTUBE錄影教學](https://youtu.be/z2jxjkl5X-4)

###  Python 標準函式庫 (Standard Library)
```
C++ 有強大的標準模板庫(Standard Template Library，STL）

Python也有強大的標準函式庫 (Standard Library)

本課程示範幾個範例,帶你認識Python 標準函式庫

推薦書籍與資源

[1]官方說明
英文 https://docs.python.org/3/library/
中文 https://docs.python.org/zh-tw/3/library/index.html

[2]厚達上千頁的範例示範說明書

The Python 3 Standard Library By Example
Doug Hellmann

https://pymotw.com/3/
https://bitbucket.org/dhellmann/pymotw-3/src/master/
```

## Python 標準函式庫的Base 64 模組
- [官方文件](https://docs.python.org/zh-tw/3/library/base64.html)
- 此模組可以做底下編碼與解碼:
  - Base16  
  - Base32
  - Base64 == > base64.b64encode(s, altchars=None)  | base64.b64decode(s, altchars=None, validate=False)
  - Base85 
  - Ascii85
- [Python base64 編碼用法與範例](https://shengyu7697.github.io/python-base64/)
```
What does the 'b' character do in front of a string literal?

https://stackoverflow.com/questions/6269765/what-does-the-b-character-do-in-front-of-a-string-literal
```
### 使用Base 64 模組編碼:b64encode()
```
import base64

data =b'BreakAllCTF{HappyPythonDay}'
encoded_data = base64.b64encode(data)
print('Original Data :', data)
print('Encoded :', encoded_data)
```
### 使用Base 64 模組解碼:b64decode()
```
import base64

encoded_data = b'QnJlYWtBTExDVEZ7NTN1c1pRM2hXVzI1ZGNoWjdkWGV9'
decoded_data = base64.b64decode(encoded_data)
print('Encoded :', encoded_data)
print('Decoded :', decoded_data)
```
### 使用Base 64 模組也可以進行Base 32編碼與解碼
```
import base64

original_data = b'BreakAllCTF{HappyPythonDay}'
print('Original data:', original_data)

encoded_data = base64.b32encode(original_data)
print('Encoded :', encoded_data)

decoded_data = base64.b32decode(encoded_data)
print('Decoded :', decoded_data)
```
### [作業] 使用Pyhon程式解Crytpo 101: Base64及Base32哪兩題

## CTF TIME練習題:編碼102:angstromCTF 2016 : what-the-hex 20
```
Decode using hex and see what you get...
6236343a20615735305a584a755a58526659323975646d567963326c76626c3930623239736331397962324e72
```

#### [可以不必教]先試看看[底下程式要在Python 2 才會正常執行]

步驟一:先將十六進位的數字轉成文字
```
'6236343a20615735305a584a755a58526659323975646d567963326c76626c3930623239736331397962324e72'.decode("hex")
```
```
'b64: aW50ZXJuZXRfY29udmVyc2lvbl90b29sc19yb2Nr'
```
步驟二:將獲得的文字再使用base 64解碼
```
import base64
base64.b64decode('aW50ZXJuZXRfY29udmVyc2lvbl90b29sc19yb2Nr')
```
### Python 3的寫法[使用 標準函式庫的binascii模組]
```
binascii模組包含很多用來方法來轉換二進位制和各種ASCII編碼的二進位制表示法
更多說明請參閱:
https://docs.python.org/zh-cn/3/library/binascii.html
```

步驟一:先將十六進位的數字轉成文字
```
import binascii
binascii.unhexlify('6236343a20615735305a584a755a58526659323975646d567963326c76626c3930623239736331397962324e72')
```
步驟二:將獲得的文字再使用base 64解碼
```
import base64
base64.b64decode('aW50ZXJuZXRfY29udmVyc2lvbl90b29sc19yb2Nr')
```
