# 1_2_Linux基本指令
- Linux 有許多指令學習主要使用方法 有需要時上網查
- [The 40 Most-Used Linux Commands You Should Know](https://kinsta.com/blog/linux-commands/#:~:text=A%20Linux%20command%20is%20a,abstraction%20of%20command%2Dline%20programs.)
- [Linux Command 命令列指令與基本操作入門教學](https://blog.techbridge.cc/2017/12/23/linux-commnd-line-tutorial/)
- [Linux 命令大全](https://www.runoob.com/linux/linux-command-manual.html)


# 使用putty遠端連線

- [下載putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html)
- [putty]()
- 下載putty的版本
![下載putty版本](./putty.png)

## lab實作:目錄存取常用指令(linux command)
- pwd ==>  顯示目前的工作目錄位置(Print Working Directory)
- cd ==> 用來變換工作目錄的指令(Change Directory)
  - cd ==> 回到使用者目錄
  - cd .. ==> 回到上層目錄
  - cd /bin ==> 切竄到/bin 目錄
- ls ==> 列出目前目錄中的檔案與目錄列表
- cat ==> (1)印出檔案內容 (2)合併多檔(concatenate）
  - cat flag
  - cat /etc/passwd

```
試輸入底下指令與參數 看看結果有何不同
ls
ls -l   <== 注意:有空格  顯示檔案與目錄的詳細資訊
ls -a    <== 注意:大小寫有區別(Case-sensitive) -a 參數可以顯示隱藏的檔案與目錄
ls -A

可以把兩個參數合在一起
ls -Al

梗多說明請參看
https://blog.gtwang.org/linux/linux-ls-command-tutorial/
```
## 指令語法與參數
```
pwd 的語法:  pwd [OPTION]

參數[OPTION]：
-L 如果當前目錄為連結檔, 會顯示連結檔名稱。
-P: 如果當前目錄為連結檔, 不會以連結檔的路徑來顯示, 會顯示實際的目錄位置。
–help: 顯示幫忙訊息。
–version: 顯示 pwd 版本。
```
## 查閱指令參數小撇步
```
1.直接在terminal 查 
    ls -h
    ls --h
    ls -help
    ls --help
    
2.上網google ==> linux ls

3.man ls
```
### 完成linux-101 ==> linux-1 與linux-2

## Linux 101-Linux CTF 3
```
你知道如何 在Linux上做hex to string嗎?

提示 : 檔案位置 /home/lab/hex.txt
```
### 解題思維
```
hex to string ==>  ?
              ==> 就是 ASCII code

http://www.tutorialspoint.com/unix_commands/xxd.htm
https://linux.die.net/man/1/xxd
```
### 解法一:使用線上工具 直接解
```
Google 一下 hex to string ==> 找線上工具 直接解
```
### 解法二:使用linux指令解題
```
列出當前檔案與目錄==> ls

檢視hex.txt檔案內容==>cat hex.txt

使用xxd工具將hex.txt的16進位內容轉換為字串==>xxd -r -p hex.txt
```
### 解法三:開發python程式解題  see HappyPythonDay 

## Linux 101-Linux CTF 4
```
你知道如何 在Linux上做base64 解碼嗎?

提示 : 檔案位置 /home/lab/base64.txt
```
### 解法一:使用線上工具 直接解
```
列出當前檔案與目錄==> ls

檢視base64.txt檔案內容 ==> cat base64.txt

Google 一下base64  decoder==> 找線上工具 直接解
```
### 解法二:使用linux指令解題
```
https://linux.die.net/man/1/base64

列出當前檔案與目錄==> ls

檢視base64.txt檔案內容 ==> cat base64.txt

使用base64工具將base64.txt的內容解碼==>base64 -d base64.txt
```
### 解法三:開發python程式解題  see HappyPythonDay 

## Linux 101-Linux CTF 5
```
你知道如何 找到 secret秘密檔案嗎?
```
## 解題思維
```
Linux中 要 找檔案的指令 ?? locate.. find ..which.. 

上網找上述指令的用法 ==> linux locate
                       linux find
                       linux which
https://www.binarytides.com/linux-find-command-examples/
```
## 解題步驟
```
從根目錄開始尋找有關secret名稱的檔案 ==> find / -name secret

檢視目錄底下的secret檔案內容 ==> 找沒有permission denied的檔案 ==> cat顯示答案 
```


## Linux重要的redirection(重定向)與 pipe(管道)功能

- pipe(管道)
  - cat /etc/passwd | less

- redirection(重定向)
  - 輸出重定向(Output redirection)  ==> ls -al > ls.txt

## shell programming



