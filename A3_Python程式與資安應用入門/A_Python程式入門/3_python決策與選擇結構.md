### python決策與選擇結構(SELECTION /DECISION) [YOUTUBE錄影教學](https://youtu.be/Qp2rnckGlAg)
```
程式語言都會有的決策與選擇結構(SELECTION /DECISION)
C C++ C# 
```
```
[1]if
[2]if ...elsif
[3]if ...else
[4]if ...elsif ...else
[5]各種判斷條件==> 善用 AND   OR
[6]範例
```
```
單向判斷式（if⋯）: 是非題｜對的才要做
雙向判斷式（if⋯else）: 二選一｜一定要選的
多向判斷式（if⋯elif⋯else）: 多選一｜一定要選的
```
```
PS: Python沒有switch
https://www.w3schools.com/python/python_conditions.asp
```
```
教學重點:教學要教最簡單的範例,要快速教完
作業要出很難的 磨出學生的程式力
```
# [1]if ==>底下程式輸出為何?
```
a = 33
b = 200

if b > a:
  print("b is greater than a")
```
```
a = 33
b = 20

if b > a:
  print("b is greater than a")
```
# [2]if ...elsif ==>底下程式輸出為何?

## 範例1
```
a = 32
b = 33

if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
```
## 範例2
```
a = 33
b = 33
if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
```
## 範例3
```
a = 35
b = 33

if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
```

# 雙向判斷式（if⋯else）: 二選一｜一定要選的

```
a = 200
b = 33

if b > a:
  print("b is greater than a")
else:
  print("b is not greater than a")
```
# [4]if ...elsif ...else  多選一｜一定要選的
```
a = 200
b = 33

if b > a:
  print("b is greater than a")
elif a == b:
  print("a and b are equal")
else:
  print("a is greater than b")
```
# [5]各種判斷條件 ==> 善用  AND  OR
```
判斷是否為閏年
```
```
year= eval(input("請輸入年"))

if ((year%400==0) or (year%4==0 and year%100!=0)):
  print("{0} 是閏年".format(year))
else:
  print("{0} 不是閏年".format(year))
```


## 完成Python101:IF 潤年

