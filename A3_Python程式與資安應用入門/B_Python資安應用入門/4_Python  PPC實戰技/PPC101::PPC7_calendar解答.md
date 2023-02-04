## PPC101::PPC7_calendar解答

### 題目敘述
```
可以判斷哪些年年是閏年年嗎?

nc 120.114.62.201 2402
```
### 解答
```python
#!/usr/bin/env python3
from pwn import *

r = remote('127.0.0.1', 20000)

r.recvlines(9)

for i in range(100):
    r.recvuntil('year : ')
    year = int(r.recvline().strip().decode())
    
    if ((year%400==0) or (year%4==0 and year%100!=0)):
        ans = 1
    else:
        ans = 0
        
    r.sendlineafter('answer : ', ["ordinary", "leap"][ans])

r.interactive()
```
