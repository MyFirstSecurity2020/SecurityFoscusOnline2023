## 3_使用wireshark分析HTTP Basic Authentication(認證)封包 [YOUTUBE教學影片](https://youtu.be/IH3Q7jdDX5s)

### [HTTP 協定](https://github.com/MyFirstSecurity2020/SecurityFirst2022/blob/main/DAY1/HappyLinuxDay/3_Linux%20%E9%91%91%E8%AD%98%E5%88%86%E6%9E%90%E5%85%A5%E9%96%80/HTTP.md)

### HTTP Basic Authentication(認證)
- HTTP 兩大Authentication(認證) 
  - 1.[Digest access authentication](https://en.wikipedia.org/wiki/Digest_access_authentication)
  - 2.[英文版wiki說明:Basic access authentication](https://en.wikipedia.org/wiki/Basic_access_authentication)
    - [中文版wiki說明:HTTP基本認證](https://zh.wikipedia.org/zh-tw/HTTP%E5%9F%BA%E6%9C%AC%E8%AE%A4%E8%AF%81)


## 解題步驟
- 步驟1:使用wireshark來開啟pcap檔
- 步驟2:在display filter 欄位中輸入http，只查看http 的封包
- 步驟3:找到GET /flag.zip封包 
- 步驟4:按右鍵 > Follow > TCP Stream
- 步驟5:發現Authorization有串Base64的字串
- 步驟6:將字串進行Base64解碼即可找到密碼
- 步驟7:將密碼輸入到解壓縮的flag.zip即可得到答案
