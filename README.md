# rapi5install

## UART포트로 부팅시 GUI출력 비활성화 ->cmdline.txt 파일수정
```
$ sudo nano /boot/firmware/cmdline.txt
splash 옵션 : 그래픽 로딩 화면을 출력
splash 옵션을 삭제
```
## USB 전력 최대화 

```
$ sudo nano /boot/firmware/config.txt
usb_max_current_enable=1
max_usb_current=1
```

## 전원체크 명령어

```bash
$ vcgencmd pmic_read_adc
```
<img width="399" height="544" alt="image" src="https://github.com/user-attachments/assets/2f5a7795-1259-4082-b7d6-027cad80e55f" />

- EXT5V_V 가 5.0V이상 출력되어야함

## 온도체크 명령어
```bash
$ sudo apt update
$ sudo apt install lm-sensors
$ sudo sensors-detect
$ sensors
```
- 50도씨 이하로 나와야함

