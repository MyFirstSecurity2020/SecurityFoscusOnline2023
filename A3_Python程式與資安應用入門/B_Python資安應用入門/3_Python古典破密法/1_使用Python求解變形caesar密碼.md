## 1_使用Python求解變形caesar密碼 {Crypto102::CRY12_變形caesar密碼}

```
import string

caesaralpha = "abcdefghijklmnopqrstuvwxyz0123456789"

def caesar(input_string,rot) :
    output_string = ""
    for i in range(len(input_string)):
        if input_string[i].isalnum():
            idx = (caesaralpha.find(input_string[i]) + rot) % len(caesaralpha)
            output_string += caesaralpha[idx]
        else:
            output_string += input_string[i]
    return output_string

enc = '7sj-ighm-742q3w4t' # encrypt data

for i in range(len(caesaralpha)):
    print(caesar(enc, i))
```

```
'rc3-2016-romangod'.upper()
```
