# FT-GBDumper
GB Cartridge Dumper using FT232HL

## なにこれ
+ FT232H, MCP23S17を使ったGBダンパー
+ 256kb/sぐらいでる
+ [GBAにも対応](https://github.com/RGBA-CRT/FT-GBADumper)
+ なぜかMBC2のセーブ読み書きができない
+ GBメモリカセットの読み出しに対応(未保障)
+ セーブ消えても知りません

## About this
+ GB Dumper using FT232HL, MCP23S17
+ Read Speed is about 256 KB/s
+ It is possible to support to GBA. (not implemented)
+ It not supported MBC2 save read/write.
+ Support GB Memory full dump. (not tested)

## 回路 / Circuit
+ 回路は[自作ROMライタ](https://github.com/RGBA-CRT/FT232H-EPROM-Prog)と同じ
+ [FT232H] ACbus <===> DataBus
+ [FT232H] SPI <===> [MCP23S17] SPI
+ [FT232H] AD4 ====> /WE
+ [FT232H] AD5 ====> unused
+ [FT232H] AD6 ====> /CE
+ [FT232H] AD7 ====> /OE
+ [MCP23S17] GPA ====> Address 0-7
+ [MCP23S17] GPB ====> Address 8-15
+ [GB] RST <==== VCC

回路図を[@YoutechA320U](https://twitter.com/YoutechA320U)さんから頂いたので掲載いたします。  
![Circuit](https://raw.githubusercontent.com/RGBA-CRT/FT-GBDumper/master/Circuit.png)

## 使い方 / usage
1. FT232Hに[D2XXドライバをインストール](http://www.ftdichip.com/Drivers/D2XX.htm)
1. exeを実行
1. カセットを挿す
1. Enterキーを押してROM情報を確認する
   + 接触不良というメッセージが出たら出なくなるまで試行錯誤する
1. 実行したい操作の番号を入力
------------
1. [Install FTDI D2XX driver](http://www.ftdichip.com/Drivers/D2XX.htm) to FT232H
1. Execute exe
1. Insert cartridge
1. Press enter key and check ROM header
   + If appear message [Contact Failure], cleanup connector and press Enter.
1. Input number of operation.  


## 参考 / technical reference
+ http://gbdev.gg8.se/wiki/articles/The_Cartridge_Header
+ http://gbdev.gg8.se/wiki/articles/Memory_Bank_Controllers
+ https://github.com/sanni/cartreader
+ https://labs.m2hq.net/Notes/20180219/GBMemoryCartridge
+ https://github.com/n13i/writeboy
+ https://forums.nesdev.com/viewtopic.php?f=12&t=11453&start=147
+ Thank you.

## Build
+ This project using the programming language of [Active Basic 4](https://www.activebasic.com/).
+ [AB-FT232HLib](https://github.com/RGBA-CRT/AB-FT232HLib) is required to build the program.
+ Place the library in the upper directory.

## SS
![ScreeenShot](https://user-images.githubusercontent.com/19349443/45218101-58ae3e00-b2e1-11e8-8570-d32ac8b97ccd.png)

---
Programmed by RGBA_CRT 2018  
Project url: https://github.com/RGBA-CRT/FT-GBDumper
