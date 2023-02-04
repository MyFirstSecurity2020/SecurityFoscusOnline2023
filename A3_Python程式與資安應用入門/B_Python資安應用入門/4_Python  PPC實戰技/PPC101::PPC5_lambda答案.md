# PPC101::PPC5_lambda
### 題目敘述
```
nc 120.114.62.201 5124
```
### 解答
```python
#!/usr/bin/env python3
from pwn import *

F = [lambda x: 3 * (x ** 2) + x + 3,
     lambda x: 5 * (x ** 2) + 8,
     lambda x: 4 * (x ** 3) + 6 * x + 6,
     lambda x: 7 * (x ** 3) + 5 * (x ** 2),
     lambda x: x ** 2 + 4 * x + 3]

r = remote('127.0.0.1', '20000')

r.recvlines(12)

for _ in range(100):
    r.recvline()
    r.recvuntil("function : ")
    f = int(r.recvline().strip())
    r.recvuntil("x = ")
    x = int(r.recvline().strip())
    r.sendline(str(F[f](x)))

r.interactive()
```
