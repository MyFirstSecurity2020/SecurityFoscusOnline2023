

## AlexCTF: Fore1: Hit the core
```
https://github.com/ctfs/write-ups-2017/tree/master/alexctf-2017/forensics/fore1-hit-the-core-50

本題必須使用 linux strings 指令照出關鍵字
strings 指令==在目的檔或二進位檔案中查找可列印的字串
strings - print the strings of printable characters in files


底下是AlexCTF 2017改編的題目

你能解出古典密碼的答案嗎?

cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}
解答格式:ALEXCTF{XXXXXXXXXXXXXXXXXXXXXXXXXXX}
```
#### 第一種解法
```
cipher='cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}'

cipher=cipher[3:] 

flag = '' 

for x in range(0,len(cipher),1): 
    if x%5==0: 
       flag +=cipher[x]
        
print(flag)
```
#### 第二種解法
```

s = 'cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}' 
print(s[3::5])
```
#### 第三種解法
```
cipher='cvqAeqacLtqazEigwiXobxrCrtuiTzahfFreqc{bnjrKwgk83kgd43j85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}' 

''.join(cipher[3 : : 5])
```



