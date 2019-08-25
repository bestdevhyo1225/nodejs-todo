# Chatting Service (Console Version) 기획서 및 설계도

<br>

## :pencil2: 1. 프로젝트 명

* TCP 소켓 모듈을 이용한 실시간 채팅 서비스

<br>

## :pencil2: 2. 기획 의도

* Slack, KakaoTalk 대표적인 회사를 비롯하여 실시간 채팅서비스는 어떻게 동작되는걸까? 궁금증이 생겨서 채팅 서비스 프로그램을 만들게 되었습니다.

<br>

## :pencil2: 3. 구현 기능

* 로그인 기능

* 회원가입 기능

* 사용자가 채팅할 수 있는 공간을 만드는 기능

* 옵션) 사용자가 채팅 내용을 파일 형태로 저장하는 기능

<br>

## :pencil2: 4. 요구 사항

* 데이터 베이스를 사용하지 않는다.

* 'http' 모듈을 사용하지 않는다.

<br>

## :pencil2: 5. Use Case 다이어 그램
![image-20190531165212354](https://github.com/bestdevhyo1225/image_repository/blob/master/image-20190531165212354.png?raw=true)

<br>

## :pencil2: 6. 실제 프로그램 흐름도
![image-20190612171301426](https://github.com/bestdevhyo1225/image_repository/blob/master/image-20190612171301426.png?raw=true)

<br>

## :pencil2: 7. 구현 모듈

### :page_with_curl: app.js

* 사용자 인터페이스 모듈이다.

* 로그인, 회원 가입, 채팅하기 목록이 존재한다.

### :page_with_curl: chat_client.js

* 채팅을 관리하는 client 모듈이다.

* 서버에게 데이터를 송수신 한다.

### :page_with_curl: chat_server.js

* 채팅을 관리하는 server 모듈이다.

* 클라이언트에게 데이터를 송수신 한다.

### :page_with_curl: file_manager.js

* 회원 정보를 관리하는 server와 file 사이에서 데이터를 전달하는 모듈이다.

* 회원 가입 기능 (존재하는 ID 체크)

* 회원 가입 경우, PW를 암호화 하는 기능

* 로그인 기능 (ID 와 PW 확인)

### :page_with_curl: member_client.js

* 회원 정보를 관리하는 client 모듈이다.

* 회원 가입이 가능한지를 판단하는 기능

* 존재하는 회원이 로그인 했는지 체크하는 기능

### :page_with_curl: member_server.js

* 회원 정보를 관리하는 server 모듈이다.

* 회원 정보와 관련된 데이터를 송수신 한다.

### :page_with_curl: utility.js

* 사용자 입력을 위한 모듈

<br>

## :pencil2: 실행 화면

### :memo: Server Socket 실행

![gif1](https://github.com/bestdevhyo1225/image_repository/blob/master/2019-08-25%2015-26-22.2019-08-25%2015_30_26.gif?raw=true)

<br>

### :memo: 사용자 회원 가입

![gif2](https://github.com/bestdevhyo1225/image_repository/blob/master/2019-08-25%2015-54-29.2019-08-25%2015_55_40.gif?raw=true)

<br>

### :memo: 사용자 로그인

![gif3](https://github.com/bestdevhyo1225/image_repository/blob/master/2019-08-25%2015-59-06.2019-08-25%2015_59_47.gif?raw=true)

<br>

### :memo: 사용자 로그아웃 & 프로그램 종료

![gif4](https://github.com/bestdevhyo1225/image_repository/blob/master/2019-08-25%2016-03-18.2019-08-25%2016_04_12.gif?raw=true)

<br>

### :memo: 사용자 채팅

![gif5](https://github.com/bestdevhyo1225/image_repository/blob/master/2019-08-25%2016-12-03.2019-08-25%2016_14_48.gif?raw=true)