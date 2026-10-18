# arduino-sensor-examples

아두이노 우노로 센서·액추에이터 기초를 실습한 스케치 모음과, 이를 응용한 장애물 회피 이륜차 프로젝트입니다.

각 스케치는 Arduino IDE 규칙에 맞게 `스케치이름/스케치이름.ino` 형태로 폴더마다 하나씩 들어 있어 바로 열 수 있습니다.

## 구성

### sensor-basics/

| 분류 | 스케치 |
|---|---|
| 디지털·아날로그 출력 | `digitalWrite_1~3`, `analogWrite_1~3`, `RGBLED1~2`, `heartLED1~4`, `roulette` |
| 입력 | `button1~3`, `VariableResistor1~3`, `Photoresistor1~2` (조도 센서), `water1~2` (수위 센서), `sound2` |
| 온습도 | `DHT11_1~2`, `temperature1~2` (DHT 라이브러리) |
| 표시 장치 | `7segment1~2`, `lcd`, `lcdAutoScroll1~2`, `lcdLight` |
| 소리 | `ActiveBuzzer1~3`, `PassiveBuzzer1~2` |
| 모터·시리얼 | `servo1~2`, `SerialServo`, `SerialServo2`, `SerialRead1~3` |

### projects/obstacle-avoiding-car/

블루투스로 조종하는 2륜 RC카입니다.

- 블루투스(SoftwareSerial) 명령 `F` / `B` / `L` / `R` / `S`로 전진·후진·좌회전·우회전·정지
- 전진 중 초음파 센서로 잰 전방 거리가 10cm 이하이면 정지
- I2C LCD(16x2)에 거리와 현재 상태 표시
- 핀: 모터 드라이버 ENA 5, IN1 7, IN2 6, ENB 9, IN3 8, IN4 10 / 초음파 TRIG 4, ECHO 12 / 블루투스 RX 2, TX 3

필요 라이브러리: `hd44780` (LCD), `DHT sensor library` (온습도 스케치)
