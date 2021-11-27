# Process

## Basic
![](https://i.imgur.com/W6u5WE4.png)  
存在於硬碟中的，我們稱之為 Program (程式)  
載入到記憶體後，我們稱之為 Process (程序)  

程式要能夠被執行，取決於：  
- 檔案所記錄的**權限(owner,group,other)**  
- **Seccomp** 限制 process 所呼叫的 syscall  
- **CGroup** 限制 process 的硬體資源  

查看當前運行的 process 的命令：  
```bash=
$ ps

#動態顯示
$ top
```

---

**parent & child**  
子程序會繼承父程序的資源限制、環境變數  

`$$` 表當前 process 的 pid  
`$0` 表當前 process 的名字  

---

**中斷信號**  

埋一個陷阱，收到 SIGINT 信號時，會執行中間的 command  
```bash=
trap "echo signal received!" SIGINT
```
**一位好的程式設計師，會在程式中埋trap，在接收中斷信號時，會進行正常關機，以維護程式的健康。**  


---

**背景執行**  
在 command 後面加上 `&`  
就可讓 process 在背景執行  

`Ctrl + x ` 會將程式暫停並推到背景  

- 讓上一個推到背景的程式，回到前景執行  
```bash=
$ fg
#foreground
```

- 讓上一個推到背景**暫停**的程式，繼續在背景執行  
```bash=
$ bg
#background
```

---

**停止process**
```bash=
#將 process 終止，預設為 -15
$ sudo kill $pid

#以正常的程序通知程式停止執行，這是預設的訊號。
$ sudo kill -15 $pid

#與鍵盤輸入 Ctrl + C 相同，也是通知程式停止執行。
$ sudo kill -2 $pid

#立刻強制停止程式執行
$ sudo kill -9 $pid
```

---

## Seccomp (SECure COMPuting)

![Linux Process 運作架構](https://i.imgur.com/YbCeaX5.png)  

執行程式時會去使用system library(linux作業系統提供)來做為輔助執行，並藉由system library操作kernel  
若是駭客攻入process，很有可能藉著system library進入kernel進行攻擊  
所以使用seccomp做為第一層防守，限制systen library的使用，當有需要時才給用  

:arrow_double_up: [MENU](https://github.com/ict39/SRE-basis/blob/main/README.md)

###### tags: `SRE-basis`
