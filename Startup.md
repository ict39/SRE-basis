# 開機流程
## BIOS/UEFI
* **檢查硬體**  
檢查 I/O 設備(POST)，無誤就發出短音蜂鳴聲。  
* **讀取第一個可開機裝置**  
硬碟、光碟、USB  

## boot loader
* **放在第一個硬碟的 sector(磁區)**
* **boot loader 種類**

| 種類     |                         |
| -------- | ----------------------- |
| GRUB     | 以硬碟打開(叫醒) kernel |
| SYSLINUX | 可以硬碟也可以光碟      |
| ISOLINUX | 以光碟打開(叫醒) kernel |

~~啟動OS~~  
要有能力找到 kernel，並啟動他  

## kernel 
* 會得知 I/O 資訊  
將硬體資訊記錄到 /proc、/dev  

## init
* kernel 將控制權交給第一個程式  
* 各 LinuxOS 的 init

| Linux OS | first process |
| -------- | ------------- |
| Ubuntu   | Systemd       |
| Alpine   | init          |
| TinyCore | busybox       |

init 再啟動以下程式  
:arrow_lower_right: Daemon 背景程式: sshd、httpd、dhcp、squid  
:arrow_lower_right: login 前景程式

:arrow_double_up: [目錄](https://github.com/ict39/SRE-basis/blob/main/README.md)
###### tags: `SRE-basis`
