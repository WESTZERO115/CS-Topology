### 01. 시스템 구성 정보
<details>
<summary> Commands </summary>
<div markdown="1">
  <br>
 
  - uname -a
  - dmesg
  - cat /proc/cmdline
  - cat /proc/booot/config-
  - dmidecode -t {bios | system | processor | memory}
  - cat /proc/cpuinfo
  - lscpu
  - df -h
  - smartctl -a /dev/sda -d cciss, 0
  - lspci | grep -i ether
  - ethtool eth0  
</div>
</details>

### 02. 프로세스 정보들
<details>
<summary> Commands </summary>
<div markdown="1">
  <br>
 
  - top 
</div>
</details>

### 03. Load average와 시스템 부하
<details>
<summary> Commands </summary>
<div markdown="1">
  <br>
 
  - uptime
  - strace
  - cat /proc/loadavg
  - vmstat
  - cat /proc/sched_debug
</div>
</details>

### 04. free 명령어

### 05. swap
