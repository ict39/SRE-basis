# File System
1. permission  
r ->ls、cat、head、tail  
w ->mkdir、touch,rm,rm -r  
x ->cd、~~source~~  
source，不須給予執行權限也可引用裡面的內容。  
2. setuid,setgid,sticky  
* setuid -> 對檔案影響  
執行時以 owner 權限執行。  
* setgid -> 檔案及目錄  
檔案 -> 是以擁有該文件的"群組"運行。  
目錄 -> 讓該目錄內的檔案不屬於創建者的群組，而是父目錄所屬的群組。  
* sticky -> 對目錄影響  
該目錄內所有檔案都只能被它的 owner 移動、刪除，但其他使用者有寫的權限  
3. Umask 修改預設權限  
檔案 666  
目錄 777  
預設 022  
就是拿掉 group 和 other 的 w 權限  

:arrow_double_up: [MENU](https://github.com/ict39/SRE-basis/blob/main/README.md)  

###### tags: `SRE-basis`
