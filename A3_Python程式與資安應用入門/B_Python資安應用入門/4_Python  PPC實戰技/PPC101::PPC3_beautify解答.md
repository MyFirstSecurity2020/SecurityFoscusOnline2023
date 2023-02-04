# PPC101::PPC3_beautify解答
### 題目敘述
```
幫我美化一下這句子

規則1 : 把所有 '-'和'_' 都換成 ' '

規則2 : 把所有英⽂文字母換成小寫

nc 120.114.62.201 2401
```
### 解答
```python
#!/usr/bin/env python3
from pwn import *

r = remote('120.114.62.215', 2401)

r.recvlines(8)
r.recvuntil('sentence : ')
sentence = r.recvline().strip().decode()
ans = sentence.lower().replace('-', ' ').replace('_', ' ')
r.sendlineafter('answer : ', ans)

r.interactive()
```
