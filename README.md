### IP 주소 표시
```bash
echo $(hostname -I) > /var/www/html/ip.html
```

### 현재 시간 표시
```bash
date=$(TZ=Asia/Seoul date +"%Y-%m-%d:%H:%M")
echo $date > /var/www/html/date.html
```

### 호스트 이름 표시
```bash
echo $(hostname) > /var/www/html/hostname.html
```

### 시스템 업타임 표시:
```bash
echo $(uptime -p) > /var/www/html/uptime.html
```

### 현재 사용자 표시
```bash
echo $(whoami) > /var/www/html/user.html
```

### 시스템 부팅 시간 표시
```bash
echo $(uptime -s) > /var/www/html/boot_time.html
```

### 시스템 메모리 사용량 표시
```bash
free -h | grep Mem | awk '{print $3 "/" $2}' > /var/www/html/memory_usage.html
```

### 디스크 사용량 표시
```bash
df -h / | grep / | awk '{print $3 "/" $2}' > /var/www/html/disk_usage.html
```

### CPU 정보 표시
```bash
lscpu | grep "Model name" | awk -F: '{print $2}' > /var/www/html/cpu_info.html
```

### 네트워크 인터페이스 정보 표시
```bash
ip -br addr show | awk '{print $1 ": " $3}' > /var/www/html/network_interfaces.html
```
