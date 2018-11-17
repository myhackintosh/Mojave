# 構建USB安裝程序

一旦你有8 + GB USB安裝程序，我們需要確保它已正確設置。如果您不打算修補安裝程序（我沒有） - 您希望通過以下方式進行USB設置：
* GUID分區圖
* 1分區
* OS X Extended \(Journaled\)

要執行此操作，請啟動終端（位於/Applications/Utilities）並鍵入diskutil list。
這將為您提供所有已連接磁盤及其分區的列表。記下USB驅動器的磁盤標識符。不要因為我們要刪除它！然後運行以下替換disk#為您的實際標識符：

```text
diskutil partitionDisk /dev/disk# GPT JHFS+ "USB" 100%
```

這將對上面列出的磁盤進行分區，並將其重命名為“USB”。

您現在可以從[Apple's own instructions](https://support.apple.com/en-us/HT201372) 運行相應的命令- 對於此示例，我們將使用Mojave命令：

```text
sudo "/Applications/Install macOS Mojave.app/Contents/Resources/createinstallmedia" --volume /Volumes/USB
```

整個安裝過程取決你的硬體速度。大約20-30分鐘左右。
安裝完畢之後，你只需要設置與Hackintosh相關的東西，

對於那些在命令行周圍膽怯的人 - 可從這裡下載 [a script](https://github.com/polo7261/USB-Installer-Creator) 直接複製再EFI\CLOVER\ 放在一起，便可以開始安裝。

