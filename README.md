# Smart_Light_Pollution_Prevention_System_IoT_Mini_Project


## 프로젝트 개요
![image](https://github.com/user-attachments/assets/95cb6a01-07c2-4413-8b9f-ac8e528eba07)


식물의 하루 광합성 시간은 10~12시간이지만, 밤에도 형광등 빛에 의해 계속 광합성을 해서 번식 능력이 떨어진다는 것을 확인했다.


따라서 자연빛과 인공빛을 구분해 조도와 온도 값을 측정해 밤 시간대가 되면 자동으로 커튼을 내려 빛을 차단하는 프로그램을 개발하기로 계획했다.


그러하여 온도와 조도 센서를 이용해 값을 측정해 일정 수치를 충족하면 밤에 자동으로 커튼을 내려 식물의 빛 공해를 방지하고, 


다양한 기기에서 서버에 접속해 다른 클라이언트 및 하드웨어와 실시간으로 통신할 수 있는 스마트 홈 IoT 시스템을 개발하였다.


## 개발 일정
2024/07/23 ~ 2024/07/26


## 팀원 소개 및 역할 분담
이성우 : 아두이노 온습도 코드, STM 모터 코드, 라즈베리파이 통신 코드, MariaDB 코드 작성, ppt 제작 


정희중 : HW 제작, 아두이노 온습도 코드 작성

## 개발 환경
- Raspberry Pi 4

  
- STM32 NUCLEO F411RE


- Arduino Uno


- 온도 센서: DHT11, 조도 센서, LCD 모듈: SZH-EK101


- Servo Motor, DC Motor, Motor Driver


- Wifi Module: ESP8266, Bluetooth Module: HC-06


- Ubuntu 22.04


- MariaDB

## 수행 목표
1) Raspberry Pi 기반 Server 개발


2) 아두이노로 온도, 조도 값을 측정해 출력 후 MariaDB에 자동으로 기록


3) Raspberry Pi 기반 Server에 MariaDB 데이터베이스 구축


4) 블루투스 모듈로 접근하여 MariaDB의 값을 STM32로 수신


5) 조건에 부합하면 STM32에서 DC 모터를 가동시켜 커튼을 내리기 


## System Architecture Diagram


![스크린샷 2024-07-27 135958](https://github.com/user-attachments/assets/6fb9b197-9a17-43e2-b9d2-d102b0d6e496)


## 담당 역할
- Client에서 요청한 동작을 수행하도록 Raspberrypi를 이용한 TCP/IP 소켓 통신 기반 Server 제작


- 아두이노에서 기록한 정보를 저장하고 관리하도록 MariaDB 구축


- 다양한 클라이언트 환경(Raspberry, Ubuntu, Bluetooth, Windows 등)에서 Server와 통신할 수 있게 SW 아키텍쳐 설계 및 구현


- 블루투스 모듈을 이용해 STM32로 측정값을 받게 구현하고 DC 모터를 구동


## 수행 역할

- 다양한 빛과 열 조건에서 온도, 조도 변화를 LCD 모듈에 출력


- 아두이노에서 측정한 데이터 전송 오류 해결 수정


- DB에 접근하는 클라이언트에게 값을 전송하는 방법을 개선


- 측정한 값을 문자열로 전송하므로 수신한 값을 문자열로 변환하도록 개선


- 회전 속도, 각도를 제어하기 위해 서보 모터에서 DC 모터로 변경 및 PWM 신호 사용


- DC 모터의 PWM 신호 인식 문제 발생 후 실패 분석

- 수행 역할에 대해 더 자세하고 알고 싶다면 아래의 [프로젝트 정리 - 노션]을 참고 바랍니다!

## 프로젝트 개선 방향

  
- 향후 프로젝트에서 모터 드라이버 선택 시, 사전에 충분한 테스트를 통해 호환성을 면밀히 검토할 예정이다

  
- 시간 기능을 추가하여 저녁 시간대 (오후 7시 ~ 오전 5시) 에만 작동시킬 것이다. (오전에 비가 온다던가 흐려져서 오작동 할 가능성 예외 처리)

## 참고 자료
[프로젝트 정리 - 노션](https://www.notion.so/8f011c5eb08d440ba6a0829c53bfeead)


[서버-클라이언트 시연 영상](https://youtu.be/Ppk5ixnDE7E)


[LCD 모듈에 출력 영상](https://youtube.com/shorts/XRogJqEBZsI)
