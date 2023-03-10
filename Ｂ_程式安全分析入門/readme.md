# 預計2023年6月開始
# 程式安全分析入門課程宗旨
- 本課程特別以範例學習模式教導學生快速掌握Linux上的C程式設計與相關安全觀念。
- 課程將使用gcc進行C語言程式設計與使用gdb進行程式動態分析與調試(debug)，運用file、strings、readelf等Linux指令進行linux執行檔(ELF)分析及使用objdump、gdb-peda與radare2、ghidra進行逆向工程。
- 另外為有效提升學生對程式漏洞威脅的認知，本課程將範例說明buffer overflow(緩衝區溢位)的測試與PWN CTF的介紹。
- 這些程式相關技術是程式安全分析的基礎同時也是CTF搶旗大賽的核心基礎知識。
- 本課程強調範例學習模式，透過幾個重要範例讓學生能快速掌握相關技能，並特別鼓勵學生盡早養成自主學習的主動精神。
- 課程提供Linux上C程式設計的開發基礎，完整的C程式設計仍建議學生修讀相關書籍。
- 逆向工程尚須對組合語言的解讀與開發有一定程度理解，鼓勵有高度學習興趣的學生繼續參加後續逆向工程的課程。

# 程式安全分析入門課程內容
- A.linux C程式設計入門
  - 使用gcc 編譯C程式
  - linux C程式的編譯與執行各階段: 預處理 => 編譯 => 彙編 => 連結
  - 使用gdb進行程式動態分析與調試(debug)
- B.Linux執行檔分析(Linux binary analysis)
  - 使用file strings 分析 Linux binary
  - Linux binary的 ELF格式
  - 使用 readelf 分析Linux binary
  - 使用 objdump 分析Linux binary
- C.組合語言程式入門
  - 認識組合語言程式:指令|暫存器|記憶體
  - 組合語言的AT&T與Intel格式
  - 使用nasm開發簡易組合程式
  - CALLING CONVENTION:函數呼叫與參數傳遞
- D.逆向工程(Reverse Engineering)入門
  - 逆向工程
  - 逆向工程常用工具
  - 使用objdump進行逆向工程解題
  - 使用gdb進行逆向工程解題
  - 使用Ghidra進行逆向工程解題
  - 使用radare2進行逆向工程解題
- E.程式安全測試pwn入門
  - 應用程式漏洞
  - Pwntools 應用程式漏洞分析
  - 緩衝區溢位(buffer overflow)漏洞測試
