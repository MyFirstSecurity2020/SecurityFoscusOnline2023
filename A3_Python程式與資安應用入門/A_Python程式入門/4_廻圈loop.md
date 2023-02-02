# agenda
```
[1].使用range 函式 的功能建立整數循序數列

[2].使用for 廻圈 執行固定次數的廻圈運算(通常)
[3].使用while 廻圈執行沒有固定次數的廻圈運算

[4].continue 指令: 在廻圈執行中途暫時停住不往下執行，而跳到廻圈的起始處執行
[5].break 指令:在廻圈執行中途強迫跳離廻圈，跳到廻圈後面的程式繼續執行。

[6].廻圈中又包含廻圈的巢狀廻圈(Nested Loop)　===>設計九九乘法表
```
```
C 程式設計有(1)for 廻圈 (2)while 廻圈 (3)do… while 廻圈 

Python沒有do… while 廻圈 ==>你自己實作一個吧?!!
```

# range() 函式
```
 使用range 函式 的建立整數循序數列
 
變數1 = range(整數值)
變數2 = range(起始值, 終止值)
變數3 = range(起始值, 終止值, 多少間隔)
```
### 變數1 = range(整數值)
```
list1=range(10)
print(list1)

print(list(list1))
```
### 變數2 = range(起始值, 終止值)
```
list2=range(-4,5)
print(list(list2))
```
### 變數3 = range(起始值, 終止值, 多少間隔)
```
list3=range(-4,5,2)
print(list(list3))
```
```
list4=range(-4,6,2)
print(list(list4))
```
# [2]for 廻圈 
```
使用for 廻圈 執行固定次數的廻圈運算(通常)
```
## 範例 1:
```
for n in range(5):
  print(n)
```
## 範例 2:
```
for n in range(10):
    print(n, end='@')

    #print(n, end='%%%%')
```
## 範例 3:底下兩個程式輸出為何? and why?
### 程式1
```
mysum = 0

for n in range(5):
  mysum += n
  print(mysum)
```
### 程式2
```
mysum = 0

for n in range(5):
  mysum += n

print(mysum)
```
Python 程式碼縮排
```
Python 語言以冒號「:」及縮排來表示程式區塊
縮排為 1 個 Tab 鍵或 4 個空白鍵
```
### 範例 4:計算1+2+3+ .....+ n
```
x = int(input("請輸入一個正整數:"))

mysum = 0

for n in range(x+1): ## 為什麼不是range(x)?
  mysum += n

print(mysum)
```
```
作業是回家做的,上課期間專心聽講

作業1:計算n!(==1*2*3* .....*n)

作業2:輸入n
      若n是偶數 則 輸出2+4+6+..+n 答案
      若n是奇數 則 輸出1+3+5+..+n 答案

作業3:續上題 增加判斷條件 ==> 輸入驗證(input validation)
      若使用者輸入錯誤(如 -3 或是 11.5等) 請他再輸入一次

作業4:再續上題 增加 錯誤次數記錄
      若 錯誤次數記錄 大於3次  輸出"你下輩子再來玩吧!"

以上題目再用while  loop再寫一次 ~~~~
```

### [程式閱讀題]執行下列程式並說明其結果
```
#底下程式如果第五行改成  if (number % 2 = 0):答案會是甚麼??

numbers = [21, 4, 35, 1, 8, 7, 3, 6, 9]
my_numbers = []

for number in numbers:
  if (number % 2 != 0): 
    my_numbers.append(number)

print(my_numbers)
```
# [3]While Loop
```
使用 while loop設計 
n階程的計算:n!=1*2*3*⋯*n

1!　=　１
2!　=　1*2　=　2
3!　=　1*2*3　=　6
```
```
輸入::一個正整數 n
輸出::n!

當使用者輸入一個正整數 n 後，程式就會顯示
1*2*3*...*n 的乘積
```
## 程式範例
```
total = i = 1

n = int(input("請輸入正整數 n 的值：")) # 再問一次:為什麼要加

while(i<=n):
    total *= i  
    i+=1      

print("%d!=%d" % (n, total))
```

# [4]break 指令
```
可在廻圈執行中途強迫跳離廻圈，跳到廻圈後面的程式繼續執行。
```
```
fruits = ["香蕉","蘋果","橘子","鳳梨","西瓜"]

while True:
    fruit = input("請輸入喜歡的水果(Enter 結束)：")

  # 要執行程式請記得把底下兩行 # 去除 
  #  if (fruit==""):
  #      break

    n = fruits.count(fruit) 
    if (n>0):  # 串列元素存在
        p=fruits.index(fruit)
        print("%s 在串列中的第 %d 項" %(fruit,p+1))
    else:
        print(fruit,"不在串列中!")
```
# [5]continue 指令 
```
在廻圈執行中途暫時停住不往下執行，而跳到廻圈的起始處繼續執行
```
```
撰寫一個可以排除數列中 5 的倍數的程式

輸入::一個正整數 n
輸出::
使用者只要輸入一個正整數，
程式會顯示由 1 到該整數的整數數列，但會將 5 的倍數排除
```
```
n = int(input("請輸入正整數："))

for i in range(1, n+1):
    if i % 5 ==0:
        continue
    print(i,end=" ")
```
# [6]巢狀廻圈Nested Loop[自主學習主題]
```
廻圈中又包含廻圈 ==> 巢狀廻圈(Nested Loop)
```

### [程式閱讀題] 底下程式執行的結果為何?請說明其邏輯
```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
 
for i in range(1,6):
    for j in range(1,5):
        for k in range(1,7):
            if( i != k ) and (i != j) and (j != k):
                print(i,j,k)
```

### 程式設計題:九九乘法表
```
留給你當作業：九九乘法表
```



