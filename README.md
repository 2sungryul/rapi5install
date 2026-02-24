# rapi5install

## Raspberry pi5 설정파일 cmdline.txt,config.txt 파일수정방법

```
- 윈도우즈에서 SD카드를 연결
- 파일탐색기에서 SD카드 검색
- /boot/firmware/ 폴더 아래에 있는 파일을 메모장으로 편집하면 됨
```

## 3핀 디버그 uart 커넥터 활성화
```
/boot/firmware/cmdline.txt
console=ttyAMA10,115200 맨앞에 추가
/boot/firmware/config.txt 
enable_uart=1 추가
```

## UART포트로 부팅시 GUI출력 비활성화 ->cmdline.txt 파일수정
```
$ sudo nano /boot/firmware/cmdline.txt
splash 옵션 : 그래픽 로딩 화면을 출력
quiet 옵션 : 부팅 로그를 숨김 
splash,quiet 옵션을 삭제
```
# 카메라 설치
- camera 연결시 cam1 커넥터 이용할것
- 카메라사용시 media 그룹 추가해야함
- libcamera 소스빌드방식으로 설치해야함
- https://billowy-water-a69.notion.site/raspberry-5-IMX219-OS-Ubuntu24-04-2f7d17f8526780aeb388d931438ef32f

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

