# agenda

- 1.認識linux作業系統
- 2_核心(kernel) 與 shell
- 3_發行版本(distributions)
- 4_linux目錄結構

## 1.認識linux作業系統
```
Linux…是一種自由和開放原始碼(open source)的UNIX-like作業系統。

The Linux kernel is a free and open-source, monolithic, 
modular,multitasking(多工), Unix-like operating system kerne
[https://en.wikipedia.org/wiki/Linux_kernel]

該作業系統的核心(kernel)由林納斯·托瓦茲Linus Torvalds在1991年首次發布。

核心原始碼公布在github ==> Linux kernel source tree
https://github.com/torvalds/linux
```

## 2_核心(kernel) 與 shell
```
Linux kernel(內核|核心)::
https://en.wikipedia.org/wiki/Linux_kernel
https://zh.wikipedia.org/wiki/Linux%E5%86%85%E6%A0%B8

上網去看看說明

架構 <== 底下有許多觀念 上大學後再學 

Linux是一個單體核心，支援真正的搶占式多工處理（於使用者態，和版本2.6系列之後的核心態）、
虛擬記憶體、共享庫、請求分頁、共享寫時複製可執行體（通過核心同頁合併）
、記憶體管理、Internet協定族和執行緒等功能。
```
```
Linux核心地圖(Map of the Linux kernel) 
==> 大學/研究所有一門課 【Linux 作業系統核心】就是在講底下內容與程式實作

   有許多模組化的功能與系統程式 ==> 如 記憶體管理子系統   行程排程子系統
```
### shell
```
shell 是提供使用者輸入各種指令(linux command)來執行各種工作 <==我們今天要學一些基本指令

linux有許多不同功能特色的shell ==> bourne Shell﹑C Shell﹑Korn Shell﹑Zsh Shell﹑等等
  ==> 我們要學的是 BASH (Bourne Again SHell) 
            == GNU 所加強的一個 Bourne shell 版本﹐ 也是大多數 Linux 套件的預設 shell 
```
## lab 實作: 檢查你使用中的linux核心
```
打開terminal  ==> 輸入 uname -a
```
## lab 實作: 檢查你使用中的bash 版本
```
打開terminal  ==> 輸入 bash --version
```

## 3_Linux發行版本(distributions)

### [Ubuntu](https://zh.wikipedia.org/zh-tw/Ubuntu)
- Ubuntu是以桌面應用為主的Linux發行版，基於Debian。
- Ubuntu有許多正式版本: [官方網址](https://ubuntu.com/#download)
  - 電腦版Ubuntu Desktop
  - 伺服器版Ubuntu Server
  - 用於物聯網裝置和機器人的Core版。Ubuntu for IoT
  - 雲端版本Ubuntu Cloud
- Ubuntu是著名的Linux發行版之一，也是目前最多使用者的Linux版本。
- [長期支援 Long-term support,LTS）](https://zh.wikipedia.org/zh-tw/%E9%95%B7%E6%9C%9F%E6%94%AF%E6%8F%B4)
  - Ubuntu 22.04 LTS

### [Red Hat](https://www.redhat.com/en)
- 作業:上網蒐集資料並整理到你的github

### 駭客與資安專家常用的Linux發行版本(Distribution)
```
Kali Linux <==今天使用的linux 版本 
     offensive linux ==攻擊型的linux版本
     滲透測試常用平台
     根據Debian修訂的Linux發行版，被設計用於滲透測試的。
      Kali Linux預設安裝了許多滲透測試軟體，包括nmap (埠掃描器)、Wireshark (封包分析器)、
          John the Ripper (密碼破解),以及Aircrack-ng (無線區域網路滲透測試軟體) 數百種工具。 
更多內容請參閱
官方網址 https://www.kali.org/
文件 https://docs.kali.org/
```
```
Security Onion 2  ==>擁有許多安全工具的Linux發行版本
Latest version: 2.3.40

更多內容請參閱
官方網址 https://securityonionsolutions.com/
文件 https://docs.securityonion.net/en/2.3/
```

```
Parrot Security OS ==> 物聯網與雲端的滲透測試平台
Security GNU/Linux distribution designed with cloud pentesting and IoT security in mind.
官方網址  https://www.parrotsec.org/
```
```
REMnux: A Linux Toolkit for Reverse-Engineering and Analyzing Malware
專門設計用來從事逆向工程與分析惡意程式的Linux版本
官方網址  https://remnux.org/
```

# 4_linux目錄結構
## windows 作業系統目錄結構
```
Windows 作業系統目錄結構==> 有 C: D:

   目錄 C:\Windows\System32 ==>  有許多檔案與子目錄  
   ==> 點選  diskmgmt ==> 開啟 【磁碟管理】 
   ==> 點選  compmgmt ==> 開啟 【電腦管理】    
   
   calc
   notepad
   winword
```
## Linux 作業系統目錄結構 
```
沒有 C: D:

最上層目錄 /
          /etc  ==> 主機或系統配置文件或設定檔絕大部分都在此目錄
          /bin
          /root ==> 最高權限使用者(管理者)登入時的目錄
          /home ==> 一般使用者登入時的目錄
          /home/ksu ==> ksu使用者登入時的目錄   
```
