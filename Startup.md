# 開機流程
## BIOS/UEFI
* **檢查硬體**  
檢查I/O設備(POST)，無誤就發出短音蜂鳴聲。  
* **讀取第一個可開機裝置**  
硬碟、光碟、USB  

## boot loader
* **放在第一個硬碟的sector(磁區)**
* **boot loader種類**

|   種類    |                   |
| -------- | ------------------ |
| GRUB     | 以硬碟打開(叫醒)kernel |
| SYSLINUX | 可以硬碟也可以光碟      |
| ISOLINUX | 以光碟打開(叫醒)kernel |

~~啟動OS~~  
要有能力找到kernel，並啟動他  

## kernel 
* 會得知I/O資訊  
將硬體資訊記錄到 /proc、/dev  

## init
* kernel將控制權交給第一個程式  
* 各LinuxOS的init

| Linux OS | first process |
| -------- | -------- |
|Ubuntu    | Systemd  |
|Alpine    | init     |
|TinyCore  | busybox  |  

init再啟動以下程式  
:arrow_lower_right: Daemon背景程式: sshd、httpd、dhcp、squid  
:arrow_lower_right: login前景程式


:arrow_forward: [工作環境]()  

:arrow_double_up: [目錄](https://github.com/ict39/SRE-basis/blob/main/README.md)
###### tags: `SRE-basis`