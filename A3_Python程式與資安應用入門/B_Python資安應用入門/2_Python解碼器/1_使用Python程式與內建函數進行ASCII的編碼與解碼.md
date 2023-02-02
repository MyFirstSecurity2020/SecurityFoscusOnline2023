### [1]使用Python程式與內建函數進行ASCII的編碼與解碼 [YOUTUBE錄影教學](https://youtu.be/0Tr-X0Lpi7g)

### Python 內建函數(Built in Functions):chr()與ord()
```
https://docs.python.org/3/library/functions.html

chr(97)

chr(66)

#ord('a')
#print(bin(ord('a')))
#oct(ord('a'))
print(hex(ord('a')))
```
### 編碼與解碼 101---ASCII編碼解題

### 字串的分割
```
a="66 114".split("")
a

a="66 114".split("  ")
a

a="66 114".split(" ")
a
type(a)
```
### 把每一個分割後的字串==轉成整數後===再編碼出ASCII的字
```
a="66 114".split(" ")

result=''

for x in a:
  y=chr(int(x))
  result += y
# result = result + y 

result
```
### 最後的解答
```
#!/usr/bin/python

c = '66 114 101 97 107 65 76 76 67 84 70 123 65 109 118 48 117 68 121 101 114 118 80 116 109 86 114 57 83 83 83 75 125'

flag = ""

for _ in c.split(' '):
  flag += chr(int(_))

print(flag)
```
#### 
```
#!/usr/bin/python

c = '66 114 101 97 107 65 76 76 67 84 70 123 65 109 118 48 117 68 121 101 114 118 80 116 109 86 114 57 83 83 83 75 125'

flag = ""

for x in c.split(' '):
  flag += chr(int(x))

print(flag)
```
