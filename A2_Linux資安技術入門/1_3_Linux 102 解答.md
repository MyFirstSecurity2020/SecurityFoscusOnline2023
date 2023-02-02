# Linux 102 解答
# Linux CTF 6
```
你知道如何找到Linux執行的服務嗎?

提示 : 2111 Port正在等待你的回應
```
```
ps(process status): http://www.linfo.org/ps.html pstree(有空試看看)

列出當前系統正在執行的Process ==> ps aux

解法一:執行flag程式 ==>/bin/flag

解法二: nc 127.0.0.1 2111
```
```
socat TCP-LISTEN:2111,reuseaddr,fork EXEC:/bin/flag
伺服器執行:sudo socat TCP-LISTEN:700 EXEC:/bin/bash

客戶端連線到伺服器: nc 127.0.0.1 700

socat
http://brieflyx.me/2015/linux-tools/socat-introduction/
Ubuntu安装:sudo apt-get install socat
```
# Linux CTF 7
```
你知道如何找到Linux正在執行的網路服務嗎?

提示 : 80 Port有你要的答案
```
```
netstat (network statistics)

列出當前系統正在執行的網路服務 ==> netstat -ano

提示 : 80 Port有你要的答案 
==> 取得http://127.0.0.1/的網頁內容
==> curl http://127.0.0.1/
```
```
https://www.binarytides.com/linux-netstat-command-examples/
https://www.tecmint.com/20-netstat-commands-for-linux-network-management/
```
# Linux CTF 8
```
你知道如何在Linux下載並解壓縮ForYou檔案嗎?

下載連結: ForYou.tar.gz
```
```
如使用以下連線，需在 /tmp 目錄底下建立自己的目錄才能下載檔案 如: /tmp/404040

在tmp目錄下建立學號目錄 ==> mkdir /tmp/404050

==> cd /tmp/404050

下載遠端網站伺服器的ForYou.tar.gz壓縮檔  ==> wget http://IP/ForYou.tar.gz

列出當前檔案與目錄 ==> ls
  
解壓縮ForYou.tar.gz檔案 ==> tar zxvf ForYou.tar.gz
    
查看ForYou檔案類型  ==> file ForYou
      
檢視ForYou檔案內容  ==> cat ForYou
```

# Linux CTF 9
```
你知道如何下載TobeExe檔案並讓他執行嗎?
```
```
如使用以下連線，需在 /tmp 目錄底下建立自己的目錄才能下載檔案 如: /tmp/404040

進入tmp目錄下的學號目錄  ==> cd /tmp/404050

下載遠端網站伺服器的TobeExe檔案 ==> wget http://IP/TobeExe

查看TobeExe檔案類型 ==> file TobeExe

賦予TobeExe檔案執行權限 ==> chmod +x TobeExe

執行TobeExe檔案 ==> ./TobeExe
```
# Linux CTF 10
```
只有執行檔你如何顯示重要資訊?

下載連結:reverse
```
```
如使用以下連線

先在 /tmp 目錄底下建立自己的目錄才能下載檔案 如: /tmp/404040

進入tmp目錄下的學生目錄 ==> cd /tmp/404050

下載遠端網站伺服器的reverse檔案 ==> wget http://IP/reverse
 
查看reverse檔案類型 ==> file reverse
  
賦予reverse檔案執行權限  ==> chmod +x reverse

執行reverse檔案  ==> ./reverse

過濾reverse執行檔內的"flag"字串  ==> strings reverse | grep flag
  
過濾reverse執行檔內的"CTF"字串  ==> strings reverse | grep CTF
```
