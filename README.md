# Smart_Light_Pollution_Prevention_System_IoT_Mini_Project (빛 공해 차단 시스템)

### 개요

야간 빛 공해가 식물 번식을 방해하는 것을 방지하기 위한 프로그램이다.


식물의 하루 광합성 시간은 10~12시간이지만, 밤에도 형광등 빛에 의해 계속 광합성을 해서 번식 능력이 떨어진다는 것을 확인했다.


따라서 자연빛과 인공빛을 구분해 조도와 온도 값을 측정해 밤 시간대가 되면 자동으로 커튼을 내려 빛을 차단하는 프로그램을 개발하기로 계획했다.


### 개발 일정
2024/07/23 ~ 2024/07/26


### 팀원 소개 및 역할 분담
이성우 : 아두이노 온습도 코드, STM 모터 코드, 라즈베리파이 통신 코드, MariaDB 코드 작성, ppt 제작 


정희중 : HW 제작, 아두이노 온습도 코드 작성, ppt 제작



### System Architecture Diagram
![스크린샷 2024-07-27 111339](https://github.com/user-attachments/assets/91179857-1b02-4195-9df1-a1a69e0e7b9c)


### S/W 구성
아두이노에서 온도, 조도 값을 측정한 후 LCD 모듈로 이를 출력한다.


와이파이 모듈을 사용해 측정한 값을 내 라즈베리파이 서버 MariaDB에 자동으로 올라가도록 구성했다.


MariaDB에 올라간 값을 블루투스 모듈을 통해 자동으로 STM32로 내려받도록 제작했다.


이후 조도 값 90 이상, 온도 값 27 이하이면 DC 모터가 작동해 커튼을 내리도록 구성했다.


수집한 데이터가 5초마다 자동으로 라즈베리파이 서버 DB에 등록된 사진
![스크린샷 2024-07-27 112946](https://github.com/user-attachments/assets/b6c1cfc6-cf46-4fbf-965a-677e266e5c30)


아두이노에서 데이터 값을 전송하는 코드, STM32에서 MariaDB의 데이터를 내려받는 코드는 깃 참고


### H/W 구성
아두이노에 온도, 조도 센서, LCD 모듈, 와이파이 모듈을 설치한 사진과 LCD 모듈로 측정한 값이 출력된 사진 첨부 
![스크린샷 2024-07-27 113142](https://github.com/user-attachments/assets/7e7960d0-b223-4e16-a5aa-40124e96d954)

![스크린샷 2024-07-27 113137](https://github.com/user-attachments/assets/03bd37f8-034c-4a1e-adac-d4fb83d698e4)


STM32에 모터 드라이버, DC 모터, 블루투스 모듈을 설치한 사진 첨부  
![스크린샷 2024-07-27 113131](https://github.com/user-attachments/assets/9f1b04ed-c5b4-491a-9463-b3666322954a)


H/W 구성 사진 첨부
![스크린샷 2024-07-27 111641](https://github.com/user-attachments/assets/7020d69b-15c0-4278-bbc6-29f96d245ae3)


### 개선 및 발전 방향
- 서보 모터만으로는 생각한만큼 회전시키지 못해 블라인드를 내리기 쉽지 않아서 모터 드라이버를 사용했지만 모터의 자체 성능이 부족해 만족스럽지 못했고, 다음에는 서보 모터를 이용해 천을 뚜껑처럼 덮는 방식이나 스텝 모터를 사용해 더 강력하게 모터가 작동하도록 모터 전환을 고려하고 있다.

  
- 시간 기능을 추가하여 저녁 시간대 (오후 7시 ~ 오전 5시) 에만 작동시킬 것이다. (오전에 비가 온다던가 흐려져서 오작동 할 가능성 예외 처리)


