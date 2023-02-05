# 資料型態(data Type)及其運算
```
Python有眾多資料型態(data Type)及其各種運算
    >* 數值(Numeric)資料及其運算
    >* 字串(string)及其運算
    >* 列表(list)資料及其運算
    >* 字典(dict)資料及其運算  
    >*[自我練習]tuple資料及其運算  
    >*[自我練習]set資料及其運算
    
 本課程規劃讓同學快速掌握python程式的開發技術
 還有更多技術及細節 請務必閱讀更多教材深入學習
 
 資料型態(Data Type)學習重點:
   各種運算
   各種內建函數
```

# 1_數值(Numeric)資料及其運算 [YOUTUBE錄影教學](https://youtu.be/KSwDTSubS1M)
```
[1]Python支援的數值型資料型別(Numerics Data Type)
[2]基本的運算  <==請參閱書籍
算術運算子Arithmetic operators
比較（關係）運算子Comparison operators
賦值運算子Assignment operators
邏輯運算符Logical operators
位元運算子Bitwise operators
成員運算子Identity operators
身份運算子Membership operators

運算子優先順序

[3]內建的各種數學函數(Built-in functions)
math模組 https://www.w3schools.com/python/module_math.asp
```
```
Python 支持三種不同的數值型別(Data Type)：

[1]Int 整數，是可以是正或負整數，不帶小數點。
   Python3  int是沒有限制大小的，可以當作 Long 類型使用，所以 Python3 沒有 Python2 的 Long 類型。
[2]浮點數(float) :由整數部分與小數部分組成，浮點型也可以使用科學計數法表示（2.5e2 = 2.5 x 10 0 = 250）
[3]複數( (complex)) - 複數由實數部分和虛數部分構成，可以用a + bj,或者complex(a,b)表示， 
                     複數的實部a和虛部b都是浮點型。
```
## [2]基本的運算
```
請參閱底下網址完成數值(Numeric)資料的各種運算
https://www.w3schools.com/python/python_operators.asp
```
- [Python 速查手冊1.6 運算子](http://kaiching.org/pydoing/py/python-operator.html)

### 算術運算子Arithmetic operators
|運算子|	功能|	範例|
| ---|---|---|
|+	|加	|a + b|
|-|	減	|a - b|
|*	|乘	|a * b|
|**	|指數	|a ** b|
|/	|除	|a / b|
|//	|整數除法	|a // b|
|%	|取餘數|	a % b|

### [實作練習]底下程式執行後結果為何?
```python
a = 17 / 3
b = 17 // 3
c = 17 % 3

a,b,c
```
- result = divmod(8, 3)
## CTF TIME 練習:Python101:11的51次方
## CTF TIME 練習:Python101:RSA加密演算法的數學計算

### 邏輯運算 Logical Operators
### 範例:底下輸出為何? and why?
```
x = 5
print(x > 3 and x < 10)
```

```
x = 5
print(x > 3 or x < 4)
```

```
x = 5
print(not(x > 3 and x < 10))
```
### 作業:Bitwise Operators[不要教,會花很多時間]
```
#!/usr/bin/python3
 
a = 60            # 60 = 0011 1100 
b = 13            # 13 = 0000 1101 
c = 0

print ("0 - a =  60 = 0011 1100(二進位) ")
print ("0 - b =  13 = 0000 1101(二進位) ")
c = a & b;        # 12 = 0000 1100
print ("1 - c = a & b的值為：", c)
 
c = a | b;        # 61 = 0011 1101 
print ("2 - c = a | b的值為：", c)
 
c = a ^ b;        # 49 = 0011 0001
print ("3 - c= a ^ b 的值為：", c)
 
c = ~a;           # -61 = 1100 0011
print ("4 - c = ~a的值為：", c)
 
c = a << 2;       # 240 = 1111 0000
print ("5 - c = a << 2的值為：", c)
 
c = a >> 2;       # 15 = 0000 1111
print ("6 - c = a >> 2的值為：", c)
```
### [3]內建函式: round()函數的測試  [YOUTUBE錄影教學](https://youtu.be/FSo8k4vFYGc)
```
#Round a number to only two decimals:
x = round(5.76543, 2)
print(x)


# Round to the nearest integer:
y = round(5.76543)
print(y)
```
```
作業:參考底網址完成十種函數的自我測試報告
https://www.w3schools.com/python/python_ref_functions.asp
```
### [4]Python 型態轉換
- 資料類型的轉換只需要將資料類型作為函數名即可。
- int(x) 將x轉換為一個整數。
- float(x) 將x轉換到一個浮點數。
- complex(x) 將x轉換到一個複數，實數部分為 x，虛數部分為 0。
- complex(x, y) 將 x 和 y 轉換到一個複數，實數部分為 x，虛數部分為 y。x 和 y 是數字運算式。

### 範例:
```python
a = 1.0004
int(a)

b = 0.9999
int(a)
```
### 數字系統(number system)的轉換
- [數目系統(number system)之n進位制說明](https://zh.wikipedia.org/wiki/進位制)
- 10進位(Decimal)  二進位(binary)  八進位(Octal)  十六進位(Hexadecimal)
- 1011(二進位) = $1*(2**3)$+0*(2**2)+1*(2**1)+1*(2**0)
- 1011(二進位) = 13(八進位) = B(十六進位) = 11(十進位)
- Python表示法:
  - 0b1011(二進位:0b開頭)  
  - 0o13(八進位:0o開頭)   
  - 0xb(十六進位:0x開頭)


###  使用Python 內建函數(Built in Functions)解決  數字系統的轉換問題

```
https://www.w3schools.com/python/python_ref_functions.asp

bin()
oct()
int()
hex()
```

### 給你十進位的 344, 二進位(binary)|八進位(octal)|十六進位(hexadecimal)是多少?
```python
dec = 344

print("10進位數字",dec,"可被轉換成:")
print(bin(dec),"二進位(binary).")
print(oct(dec),"八進位(octal).")
print(hex(dec),"十六進位(hexadecimal).")
```
## int[]內建函數
```
功能:將一個字串或數位轉換為整數型。

語法: int(x, base=10)

參數說明:
x -- 字串或數位。
base -- 進制數，預設是十進位。

返回值:會返回一個整數型資料。
```

##  CTF TIME 練習:數字系統的轉換:16進位轉10進位 (1111)16 =()10
##  CTF TIME 練習:數字系統的轉換:8進位轉10進位  (1111)8 =()10
##  CTF TIME 練習:數字系統的轉換:2進位轉10進位  (1111)2 =()10

- 運算優先順序 請參閱書籍



# 2_字串(string)及其運算  
## 字串(string)
```
[1]string字串 資料型態(data type) 
[2]string字串的運算
[3]Python内建的字串函数(Built-in String Methods)
```
- string字串 資料型態(data type) 
  - 變數值以一對雙引號 (「"」)或單引號 (「'」)
  - str1 = '這是字串'
  - str2 = "這也是字串"
  - str3 = 'allows embedded "double" quotes'
- string字串的運算:存取字串中的值: 使用方括號

### [實作練習]底下程式執行後結果為何?
```python
var1 = 'Hello Python!'

print("var1[0]: ", var1[0])
print("var1[1:8]: ", var1[1:8]) # Slicing 切片運算
```
### Slicing 切片運算範例:底下執行結果為何?
```
b = "Hello, World!"
print(b[2:5])
print(b[:5])
print(b[2:])
print(b[-5:-2]) # Negative Indexing
# 參考資料 https://www.w3schools.com/python/python_strings_slicing.asp
```
## [2_3]Python内建的字串函数(Built-in String Methods)
```
作業:參考底網址完成十種函數的自我測試報告
Python - String Methods
https://www.w3schools.com/python/python_strings_methods.asp
```
### [實作練習]底下程式執行後結果為何?
```
str1='happy python day'
str2='    Oh!   '

str4=str1 + str2   # 字串串接String Concatenation運算

print(str4.capitalize())

mystr = 'python'
str4.find(pyth, beg=0, end=len(str4))
```
# 3_列表(list)資料及其運算
- LIST是 Python 中最基本的資料結構。
- LIST使用一個方括號內的逗號分隔值出現。
- LIST的每個值都有對應的位置，稱之為索引( index) | 第一個索引是 0，第二個索引是 1，依此類推。
- LIST都可以進行的操作包括索引，切片，加，乘，檢查成員。
- Python 內建許多LIST函數: 
  - 1.len(list):元素個數
  - 2.max(list)返回元素最大值
  - 3.min(list):返回元素最小值

### 範例 1:底下程式執行後結果為何?
```
list1 = [21, 33, 14, 12, 32, 98]

list1[1]
list1[-2]
list1[1:3]  # 切片運算

#[內建函數]練習
len(list1)
max(list1)
min(list1)
sum(list1)
```
## 4_字典(dict)資料及其運算
- 字典的每筆資料都使用key(鍵)=>value(值) pair(對)
- 每筆資料都使用冒號 : 分割
- 每對之間用逗號(,)分割，
- 整個字典包括在花括弧 {} 
- key(鍵)必須是唯一的，但value(值)則不必。
- Python 內建許多函數: 
  - len(dict):計算字典元素個數，即鍵的總數。
- Python 內建許多方法(Method):
  - 字典.items():以列表返回LIST陣列
  - 字典.keys():返回所有keys
  - 字典.values():返回所有values

### 字典(dict)資料的定義方式:
```python
a = dict(one=1, two=2, three=3)
b = {'one': 1, 'two': 2, 'three': 3}
c = dict(zip(['one', 'two', 'three'], [1, 2, 3]))
d = dict([('two', 2), ('one', 1), ('three', 3)])
e = dict({'three': 3, 'one': 1, 'two': 2})
f = dict({'one': 1, 'three': 3}, two=2)
a == b == c == d == e == f
```
True
### 範例 1:底下程式執行後結果為何?
```python
dict = {'Name': 'DaDaLong', 'Age': 17, 'Class': 'First'}

print("dict['Name']: ", dict['Name'])
print("dict['Age']: ", dict['Age'])

dict.items()

list(dict.items())

list(dict.keys())
```
### 應用範例程式
```python
使用字典(dict)資料攢成簡單的小寫英文字母 的ASCII 字典
https://en.wikipedia.org/wiki/ASCII
 a-->97  ... z-->122
```
```
# key 是數字 value是小寫英文字母 97-->a  ... 122-->z
ascii_a2z = {num: chr(num) for num in range(97,123)}
ascii_a2z
```
```
# key 是小寫英文字母   value是 數字 a-->97  ... z-->122
alphas= []
for num in range(97,123):
    alpha = chr(num)
    alphas.append(alpha)
  
ascii_a2z = {alpha: ord(alpha) for alpha in alphas}
ascii_a2z
```
# [進階研讀]標準函式庫還定義有許多資料型態
```
The Python Standard Library
https://docs.python.org/3/library/

參考Built-in Types ==>
Numeric Types — int, float, complex
Text Sequence Type — str
Sequence Types — list, tuple, range
Mapping Types — dict
```

