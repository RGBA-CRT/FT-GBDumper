# FT-GBDumper
GB Cartridge Dumper using FT232HL

## なにこれ
+ FT232H, MCP23S17を使ったGBダンパー
+ 256kb/sぐらいでる
+ GBAへの対応も予定
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

## 使い方 / usage
+ exeを実行
+ execute exe

## 参考 / technical reference
+ http://gbdev.gg8.se/wiki/articles/The_Cartridge_Header
+ http://gbdev.gg8.se/wiki/articles/Memory_Bank_Controllers
+ https://github.com/sanni/cartreader
+ https://labs.m2hq.net/Notes/20180219/GBMemoryCartridge
+ https://github.com/n13i/writeboy
+ https://forums.nesdev.com/viewtopic.php?f=12&t=11453&start=147
+ Thank you.
