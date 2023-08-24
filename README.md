# atom2.0-3d-printer klipper octoprint

 Fluidd 跟 MainSail 相比octoprint 節省資源
如果預算考量想用raspberry pi 以外方案如orange pi 比較建議使用前兩者
配置上大同小異

使用KLIPPER 韌體3步驟

步驟一

在pi 安裝KLIPPER 
下載燒入器 將klipperoctoprint鏡像燒入sd卡
https://www.raspberrypi.com/software/

選單other specific-purpose os>>3d printing>>octoklipperpi

![image](https://github.com/aa2362339/atom2.0-3d-printer/blob/main/PI-IMAGE.jpg)

不驟二 
依照官網

構建刷寫微控制器

在編譯微控制器程式碼之前，首先在樹莓派上執行這些命令：
`cd ~/klipper/`
`make menuconfig`


打印機配置文件 頂部的註釋應描述“make menuconfig”期間需要設置的設置。在網絡瀏覽器或文本編輯器中打開文件，然後在文件頂部附近查找這些說明。一旦配置了適當的“menuconfig”設置，按“Q”退出，然後按“Y”保存。然後運行：


make

如果 打印機配置文件 頂部的註釋描述了將最終圖像“閃爍”到打印機控制板的自定義步驟，則按照這些步驟操作，然後繼續 配置OctoPrint。

否則，通常使用以下步驟來“刷新”打印機控制板。首先，需要確定連接到微控制器的串口。運行以下命令：

它應該報告類似以下的內容：
ls /dev/serial/by-id/*



/dev/serial/by-id/usb-1a86_USB2.0-Serial-if00-port0
通常每一個印表機都有自己獨特的串列埠名，這個獨特串列埠名將會在刷寫微處理器時用到。在上述輸出中可能有多行。如果是這樣的話選擇與微控制器相應的


刷寫微控制器 klipper 韌體
我是使xloader 我是使用mks gen l v2.1 應該與原廠板子使用的韌體相同(待確認)
![image](https://github.com/aa2362339/atom2.0-3d-printer/blob/main/xloder.jpg)


