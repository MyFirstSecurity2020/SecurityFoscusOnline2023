# 3_Linux 鑑識分析入門

## 數位鑑識(Digital Forensics)
- [Wiki 英文版說明Digital forensics](https://en.wikipedia.org/wiki/Digital_forensics)
- [Wiki 中文版說明Digital forensics](https://zh.wikipedia.org/wiki/%E6%95%B8%E4%BD%8D%E9%91%91%E8%AD%98)
- 數位鑑識|數位鑑識科學|數位取證
  - 是鑑識科學(Forensics)的其中一個分支，主要在針對數位裝置(電腦|手機)中的內容進行調查與復原

## 常見的數位鑑識(Digital Forensics)
- 1_電腦鑑識(Computer Forensics) [英文版wiki說明](https://en.wikipedia.org/wiki/Computer_forensics)
  - 自電腦系統或其它類似的儲存媒體中，尋找罪行相關物證或間接物證
  - 常用工具:[autospy](https://www.autopsy.com/) [下載autospy](https://www.autopsy.com/download/)
- 2_網路鑑識(Network Forensics) 
  - 自側錄的網路流量中尋找相關證據
  - 常用工具:[wireshark](https://www.wireshark.org/) [下載wireshark](https://www.wireshark.org/#download)
  - 本次課程使用linux上的wireshark  
  - 同學可以下載 windows版本的wireshark 
- 3_記憶體鑑識(Memory Forensics)
  - 自記憶體中尋找相關證據  
  - [英文版Wiki說明: forensic analysis of a computer's memory dump](https://en.wikipedia.org/wiki/Memory_forensics)
  - 常用工具:[Volatility (使用python程式開發的)](https://www.volatilityfoundation.org/)

## 課程內容
- 1.認識wireshark
- 2.網路鑑識分析第一步:使用file 和 string 指令進行分析
- 3.使用wireshark檢視出user使用的瀏覽器版本號
- 4.使用wireshark分析HTTP Basic Authentication(認證)封包
