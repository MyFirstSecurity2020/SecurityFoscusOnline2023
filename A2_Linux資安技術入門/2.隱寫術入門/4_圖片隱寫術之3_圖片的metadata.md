# 4_圖片隱寫術之3:圖片的metadata
- 圖片還能怎麼藏資料?
- [How To View Image Metadata On Linux](https://ostechnix.com/how-to-view-image-metadata-on-linux/)

## 示範題目:
```
隱寫術102_CSAW QUALS 2015: keep-calm-and-ctf(必)50
```
[檔案下載處 metadata圖片隱寫術](https://raw.githubusercontent.com/MyFirstSecurity2020/backup/main/steg/steg102/img.jpg)

# 參考解題步驟
## 解題步驟1:查看檔案格式
```
file /root/Desktop/img.jpg
```

## 解題步驟2:查看檔案內藏的字串
```
strings /root/Desktop/img.jpg
```

## 解題步驟3:安裝工具並學習使用技術
```
google搜尋jpg metadata linux

看看怎麼用 ==>
http://xahlee.info/img/metadata_in_image_files.html
http://libre-software.net/edit-image-metadata-on-linux/

安裝工具 ==> sudo apt-get install exiftool

sudo ==> GNU/Linux允許 一般使用者 透過安全的方式使用 特殊的權限 執行程式
      https://blog.gtwang.org/linux/sudo-su-command-tutorial-examples/

apt-get ==>  (Debian)Linux用來安裝(install)軟體與套件的利器
        更多指令參數請參閱底下參考資料
```

## 解題步驟4:查看檔案並讀出答案
```
exiftool img.jpg  ==>即可讀出答案
```

## 作業
```
上網找資料學習ImageMagick的技巧 試看看用此工具解此題
http://xahlee.info/img/imagemagic.html
```
## Kali linux 20220618
```
file img.jpg
strings img.jpg
exif img.jpg
```
# 建議研讀
## metadata ==> 關於資料 的 資料（data-about-data）
```
https://zh.wikipedia.org/wiki/元資料

1969年，由Jack E. Myers所提出的.metadata即關於資料的資料（data-about-data），
可以說是一種標準，是為支援互通性的資料描述，所取得一致的準則
```
## 解析 圖片 元資料 的 ExifTool
```
https://zh.wikipedia.org/wiki/ExifTool

ExifTool是Phil Harvey以Perl寫成的免費開源軟體，可讀寫及處理圖像、視頻及音頻的metadata，
例如Exif、IPTC、XMP、JFIF、GeoTIFF、ICC Profile。
它是跨平台的，可作為命令列(我們上課用的)或Perl函式庫使用。

==>官方網址  https://exiftool.org/
            https://github.com/exiftool/exiftool
            https://zh.wikipedia.org/wiki/ExifTool
```

## (Debian)Linux用來安裝(更新)軟體與套件的利器 ==> apt-get
```
apt-get install  ==> 軟體安裝

apt-get update ==> 軟體資料庫同步
     apt-get update 會根據 /etc/apt/sources.list 中設定到 APT Server 去更新軟體資料庫，
     在任何更新之前最好都先做這一個動作，讓軟體資料保持在最新的狀況之下。

apt-get remove  ==> 軟體移除

apt-get upgrade ==> 軟體升級
```
## 另外補充apt-cache 
```
apt-cache ==> 用來取得套件的資訊

apt-cache showpkg  ==> 顯示套件資訊

apt-cache stats   ==> 顯示相關的統計資訊

apt-cache dump   ==> 顥示 cache 中每個套件的簡短資訊
```
```
請上網將其他相關技巧整理到你的github
強烈鼓勵學生主動學習 --主動找資料 主動整理成筆記(github)

不只是坐在課堂下 單純聽講
```

