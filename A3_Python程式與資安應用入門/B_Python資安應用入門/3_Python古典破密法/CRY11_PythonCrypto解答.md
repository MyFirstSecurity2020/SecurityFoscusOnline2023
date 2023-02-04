## Crypto102::CRY11_PythonCrypto

#### 第一種解法
```
cipher='cvqBeqacRtqazEigwiAobxrKobxrAobxrLwgk8Lwgk8CrtuiTzahfFreqc{bnjrZwgk8Ikgd4Pj85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}'

cipher=cipher[3:] 

flag = '' 

for x in range(0,len(cipher),1): 
    if x%5==0: 
       flag +=cipher[x]
        
print(flag)
```
#### 第二種解法
```
s = 'cvqBeqacRtqazEigwiAobxrKobxrAobxrLwgk8Lwgk8CrtuiTzahfFreqc{bnjrZwgk8Ikgd4Pj85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}' 
print(s[3::5])
```
#### 第三種解法
```
cipher='cvqBeqacRtqazEigwiAobxrKobxrAobxrLwgk8Lwgk8CrtuiTzahfFreqc{bnjrZwgk8Ikgd4Pj85ePgb_e_rwqr7fvbmHjklo3tews_hmkogooyf0vbnk0ii87Drfgh_n kiwutfb0ghk9ro987k5tfb_hjiouo087ptfcv}' 

''.join(cipher[3 : : 5])
```



