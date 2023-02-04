## PPC101::PPC8_temperature答案
### 題目敘述
```
我需要你幫忙把華氏轉攝氏

nc 120.114.62.201 5127
```
### 分析
```
[XD] % nc 120.114.62.215 5127
===== Welcome =====
I need you to transform from Fahrenheit to Celsius
----- wave : example -----
Fahrenheit : 10 (guarantee to be integer)
Celsius : -110/9
----- wave : 1/100 -----
Fahrenheit : -10
Celsius : 
```
- 一般數字運算都是寫成小數點型式
- 本題卻是要用有理數|分數(fractions — Rational numbers)方式呈現
- 需要使用python內建的fractions模組

## [python內建的fractions模組](https://docs.python.org/3/library/fractions.html)
- 參考資料:[Fraction module in Python](https://www.geeksforgeeks.org/fraction-module-python/)
```python
from fractions import Fraction

half = Fraction(1, 2)

print(half.numerator)
print(half.denominator)
```
```
from fractions import Fraction

# 1.把分數轉成小數
three_quarters = Fraction(3, 4)

print(float(three_quarters))

# 2.把小數轉成有理數
print(Fraction('1.13'))

# 3.會自動化成最簡分數
print(Fraction(9, 12))  # GCD(9, 12) = 3


# 4.執行 有理數|分數 運算 ==>結果也是用 有理數|分數 表達
print(Fraction(113, 100) + Fraction(25, 18))
# returns Fraction(2267, 900)
  
print(Fraction(18, 5) / Fraction(18, 10))
# returns Fraction(2, 1)
  
print(Fraction(18, 5) * Fraction(16, 19))
# returns Fraction(288, 95)
```
### 解答
```python
#!/usr/bin/env python3
from pwn import *
from fractions import Fraction

r = remote("127.0.0.1", 20000)

r.recvlines(5)

for _ in range(100):
    r.recvuntil("Fahrenheit : ")
    F = Fraction(int(r.recvline().strip()), 1)
    C = (F - 32) * 5 / 9
    r.sendline(str(C.numerator) + '/' + str(C.denominator))

r.interactive()
```
