# 黑蘋果新手注意事項

## 如何安裝Clover EFi

#### 前言

香草EFI的設置，以EFI開機引導來啟動macOS作業系統，Hackintosh所需要相關的kexts，補丁等都包含在EFI分區中。香草安裝的EFI與官方蘋果電腦EFI相同。

*快速術語詞彙表**

您將在本指南中看到許多術語 - 我將在此概述其中的一些術語及其定義：

* Clover - 這是我們將使用的引導程序。真正的mac有一個自定義固件，允許他們啟動macOS。PC硬件需要一些幫助才能使其正常工作; Clover幫助我們實現這一目標。它還處理kext注入，ACPI重命名，kext補丁和許多其他功能。
* _Kexts_ - “kext”這個詞實際上就是K ernel Ext ension 的組合; 你可以把kexts簡單地想像為macOS的驅動程序。
* _Config.plist_ - 這是告訴Clover要做什麼的文件。它是一個XML格式的屬性列表（看起來非常類似於HTML），是設置Hackintosh最重要的部分之一。.
* _OOB_ -  _Out Of the Box_ 首字母縮寫詞，意味著工作支持而不需要調整。
* 當我處理本指南（可能）時，會添加更多內容

## 先決條件

本指南僅關注桌面。筆記本電腦還有其他指南  [RehabMan's guide](https://www.tonymacx86.com/threads/guide-booting-the-os-x-installer-on-laptops-with-clover.148093/) at TMac\) - 但它們通常比本指南更具體。

我們需要一些東西才能讓我們開始：

1. 準備一隻8G以上的 USB flash drive
2. 安裝OS X / macOS.app（最好直接從應用程序商店下載）
3. \_\_[_Clover's Install Package_](https://github.com/Dids/clover-builder/releases) __\(courtesy of Dids\)
4. [_Clover Configurator_](http://mackie100projects.altervista.org/download-clover-configurator/) \(the brave can edit with any text editor - but CC is typically quicker\)
   * 勇敢者可以使用任何文本編輯器進行編輯 - 但CC通常更快）
5. \_\_[_VirtualSMC.kext_](https://github.com/acidanthera/VirtualSMC/releases) - this supercedes _FakeSMC.kext_ as our SMC emulator and either _VirtualSMC_ or _FakeSMC_  這取代了FakeSMC.kext作為我們的SMC模擬器，VirtualSMC或FakeSMC對於啟動我們的Hackintosh至關重要。沒有其中一個，我們永遠不會開機。
確保您獲得全球版
6. 我們的主板/等的任何其他kexts
我們將在下一節中討論這個問題！
7. 你需要的耐心、堅持。

