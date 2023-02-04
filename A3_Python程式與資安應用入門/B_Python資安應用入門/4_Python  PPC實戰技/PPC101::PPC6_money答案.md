## PPC101::PPC6_money
### 題目敘述
```
nc 120.114.62.201 2407
```
## 分析  nc 120.114.62.215 2407
```
===== Welcome to money game =====
Can you help me calculate bank interest
Give you total amount of money (will be multiple of 100) and annual interest rate
Give me the total amount of money I will have next year
----- Example -----
money : 10000
interest : 5%
answer : 10500
----- wave 1/100 -----
money : 641500
interest : 40%
answer : 
```
### 解答
```python
#!/usr/bin/env python3
from pwn import *
import string

r = remote('127.0.0.1', 20000)

r.recvlines(8)

for i in range(100):
    r.recvuntil('money : ')
    money = int(r.recvline().strip())
    r.recvuntil('interest : ')
    interest = int(r.recvline().strip().strip(b'%'))
    r.sendlineafter('answer : ', str(money + money // 100 * interest))

r.interactive()
```
