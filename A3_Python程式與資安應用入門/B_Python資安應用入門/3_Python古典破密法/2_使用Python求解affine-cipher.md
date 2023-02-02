# [仿射密碼](https://zh.wikipedia.org/wiki/%E4%BB%BF%E5%B0%84%E5%AF%86%E7%A2%BC)[affine-cipher](https://en.wikipedia.org/wiki/Affine_cipher)

## 示範題:Crypto 102::School CTF 2015: affine-cipher-100
```
import string 

# 先產生小寫字母,再加入其他
s = string.ascii_lowercase # a-z 
s += '_'

# 使用 字典(dictionary)資料型態 來建立 轉換表|解密規則
d = {} 

for c in range(len(s)): 
      d[s[(c*4 + 15)%27]] = s[c] 

# 使用 轉換表|解密規則 逐字解出答案
ciphertext = 'ifpmluglesecdlqp_rclfrseljpkq' 
s1 = '' 

for x in ciphertext : 
     s1 += d[x] 

# 印出答案
print(s1)
```
