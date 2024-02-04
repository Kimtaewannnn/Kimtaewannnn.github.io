---
title: 웹소켓을 이용한 채팅방 구현
description: 기술세미나 
image: https://kimtaewannnn.github.io/kimtaewannnn.github.io/assets/images/project/web.png
date: 2023-07-05
youtube: E08cy4y82xY
---

# 프로젝트 소개

자바와 스프링 부트를 활용하여 웹소켓을 이용한 채팅방 구현 프로젝트를 수행했습니다. 
이 프로젝트는 자바 수업에서 쌓은 다양한 웹 애플리케이션 기능(게시판 만들기, 회원가입, 글쓰기 글 목록 보기... )구현 경험을 토대로,
더 발전된 기술을 학습하고 적용하고자 했습니다. 
채팅방을 선택한 이유는 실시간 통신의 복잡성과 흥미로움에 주목했기 때문입니다. 롤, 인스타그램, 그리고 금융 분야의 실시간 데이터 전송에서 사용되는 웹소켓 기술을 선택하여 더 깊이 이해하고자 했습니다.

# 프로젝트 목표 및 의의

**웹소켓**

프로젝트의 주요 목표는 웹소켓 기술을 활용하여 실시간 채팅 기능을 구현하는 것이었습니다. 
웹소켓을 이용한 양방향 통신을 통해 사용자들이 실시간으로 대화할 수 있는 환경을 제공하였습니다.

**웹소켓과 HTTP 차이점**

웹소켓과 HTTP의 차이점을 명확히 이해하고자 했습니다. 기존의 HTTP 프로토콜과 웹소켓의 장단점을 비교하여 웹소켓이 어떠한 상황에서 필요한지를 깊이 이해하는 것이 프로젝트의 목표 중 하나였습니다.

**웹소켓 동작 방법**

웹소켓의 동작 방식에 대해 깊이 파악하여, 클라이언트와 서버 간의 실시간 통신이 어떻게 이루어지는지를 자세히 다뤘습니다. 이를 통해 실제로 어플리케이션에서 발생할 수 있는 다양한 시나리오에 대응할 수 있게 되었습니다.

# 기간 및 참여자
23.06~23.07 / 김태완 이소영

# 사용 기술 및 도구

**프로그래밍 언어**: Java , JS , HTML , CSS

**통합 개발 환경 (IDE)**: Visual Studio Code , Spring Boot

# 결과물 및 성과

![web1](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/a002cd32-89b1-4a1b-a29a-fac1dc7c49e9)
**pom.xml에 위와 같은 dependency 추가**

Apache Tomcat을 내장
Spring Boot에서 Web Socket을 사용할 수 있는 필수 라이브러리와 구성요소 포함

![web2](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/7178d983-9b20-4b5d-94a0-df2be0a165ae)
**@EnableWebSocket**

-웹소켓 관련 기능을 사용할 수 있도록 스프링 애플리케이션에 활성화

-일반적으로 스프링의 구성 클래스 또는 구성 파일에 적용

![web3](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/cbf7fc9c-e282-4fd0-afd1-86d6a8c301b6)
**@Controller**

해당 클래스가 스프링의 컨트롤러로 인식되도록 설정함

**@RequestMapping("/chatting/chat")**
 
"/chatting/chat" 경로로 들어오는 요청을 이 메서드가 처리함

![web4](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/d7fbe0f7-376d-4756-8a46-60beee591432)
**@Commponent**

TextWebSocketHandler 클래스를 상속받은 SocketTextHandler 클래스를 스프링의 컴포넌트로 등록

![web5](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/c27581dc-f691-4716-af5e-48cc50480295)

**handleTextMessage 메서드**

클라이언트에서 서버로 메시지가 전송될 때 실행되는 로직

해당 메서드에서는 모든 세션에게 받은 메시지를 다시 전송하는 로직으로 구현


![web6](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/060bb74e-b622-4654-9e5d-84949b6ea910)

**afterConnectionEstablished 메서드**

세션이 생성될 때 호출되며, 세션을 sessions 맵에 추가하는 역할

**afterConnectionClosed 메서드**

세션이 종료될 때 호출되며, sessions 맵에서 해당 세션을 제거하는 역할

![web7](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/41024759-450c-4f04-aac1-709f75cca438)

**wsOpen()**

웹 소켓을 열기 위한 함수

Ip주소를 사용하여 현재 호스트의 ip주소를 가져와서 WebSocket 주소에 포함


![web8](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/a6259278-dc04-44ef-9dc4-8e9336e4dbcf)

**wsEvt()**

웹 소켓 이벤트를 처리하는 함수

onopen 이벤트 핸들러는 소켓이 열리면 동작

onmessage 이벤트 핸들러는 메시지를 받으면 동작 

받은 메시지를 파싱하여 해당 메시지의 유형에 따라 동작
 
getId 타입의 메시지인 경우 세션 ID를 추출하여 sessionId라는 요소에 설정

message 타입의 메시지인 경우 sessionId와 현재 sessionId 값이 일치하는지 확인하고, 채팅창에 메시지를 추가합니다.
 
![web9](https://github.com/Kimtaewannnn/Kimtaewannnn.github.io/assets/133857370/f814ff5f-9b70-4cac-b62b-966837b797ee)

**chatName()**

사용자 이름을 입력받고, 유효성을 검사한 후 WebSocket을 열고 업데이트

**Send()**

사용자가 입력한 메시지를 WebSocket을 통해 서버로 전송






 


