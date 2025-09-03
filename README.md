
# 🎲 Boogi Party

> **멀티플레이 네트워크 보드게임**  
> 자바 소켓 프로그래밍과 Swing GUI를 이용해 구현한 부루마블 + 마리오 파티 스타일의 보드게임  

---

## 📖 프로젝트 소개
- 프로젝트명: **Boogi Party**  
- 개발환경: **Java (IntelliJ)**  
- 팀명: **멋**  
- 팀원: 정웅, 유정균  

Boogi Party는 **부루마블**과 **마리오 파티**에서 아이디어를 얻어 만든 **멀티플레이 보드게임**입니다.  
게임의 배경은 **한성대학교**, 캐릭터는 학교 마스코트로 구성하여 재미 요소를 더했습니다.  

플레이어는 주사위를 굴려 보드를 이동하며, 특정 칸에서는 퀴즈나 미니게임 이벤트가 발생합니다.  
**총 2바퀴를 완주하는 플레이어가 우승**합니다.  

---

## ✨ 주요 기능
- 🎲 **주사위 및 이동**: 애니메이션과 함께 캐릭터가 이동  
- ⚔️ **공격 기능**: 상대 말과 겹치면 상대를 시작점으로 돌려보냄  
- 👥 **멀티플레이 지원**: 최대 4명까지 동시 플레이  
- 🛒 **상점/아이템 시스템**: 코인으로 아이템을 구매하고 활용 가능  
- 🎶 **배경음/효과음**: 음악과 효과음으로 몰입감 강화  
- 💬 **실시간 채팅**: 대기방/게임 내 채팅 지원  
- 🎮 **미니게임 3종**:  
  - ✊ 가위바위보  
  - 🎰 겜블링 게임  
  - 🔫 총알 피하기 게임  
- ❓ **퀴즈 이벤트**: 특정 칸에 도달 시 문제 출제 및 정답 맞히기  

---

## 🖼️ 시연 영상
[![시연 영상](https://img.youtube.com/vi/o_s6Ucdrao8/0.jpg)](https://youtu.be/o_s6Ucdrao8)  
👉 클릭하면 유튜브 시연 영상을 볼 수 있습니다.

---

## 🛠️ 기술 스택
- **Language**: Java  
- **GUI**: Swing  
- **Network**: Socket Programming (TCP)  
- **IDE**: IntelliJ  

---

## 📂 프로젝트 구조
```plaintext
src/
 ├── client/
 │   ├── ClientThread.java
 │   ├── Main.java
 │   ├── Menu.java
 │   ├── PlayMusic.java
 │   ├── RoomList.java
 │   └── WaitingRoom.java
 │
 ├── Game/
 │   ├── Game.java
 │   ├── GameGUI.java
 │   ├── Player.java
 │   ├── PointManager.java
 │   ├── Quiz.java
 │   ├── MiniGame.java
 │   ├── Map4_GBBGame.java
 │   ├── Map8_GamblingWithThread.java
 │   ├── Map12_BulletGameFrame.java
 │   └── SpeechBubble.java
 │
 └── server/
     ├── CentralServer.java
     └── RoomThread.java
````

---

## ⚡ 실행 방법

1. **서버 실행**

   ```bash
   javac server/CentralServer.java
   java server.CentralServer
   ```

   * 9999번 포트에서 실행 (방 관리 및 클라이언트 연결)

2. **클라이언트 실행**

   ```bash
   javac client/Main.java
   java client.Main
   ```

   * 닉네임 입력 후 대기방(RoomList)으로 진입
   * 방 생성 또는 기존 방 참여

---

## 📡 네트워크 프로토콜

### 클라이언트 명령어

* `USER_UPDATE` : 방 유저 목록 업데이트
* `USER_MSG` : 채팅 메시지 전송
* `READY_STATE` : 준비 상태 동기화
* `ROLL_DICE` : 주사위 결과 전송
* `MINI_GAME` : 미니게임 시작
* `QUIZ` / `QUIZ_OVER` : 퀴즈 시작/종료
* `ITEM_USE` : 아이템 사용
* `GAME_OVER` : 게임 종료

### 서버 명령어

* `WAITING_ROOM_PROCESS` : 대기방 처리
* `EXIT_ROOM` : 접속 종료
* `EXIT_GAME` : 게임 시작
* `EXIT_DICE` : 주사위 굴리기
* `EXIT_MINI_GAME` : 미니게임 실행
* `EXIT_ITEM` : 아이템 사용
* `EXIT_GAME_OVER` : 게임 종료


## ⚠️ 주의사항

* **IntelliJ에서는 정상 동작**하지만, **Eclipse 실행 시 소리 경로 이슈**로 배경음/효과음 재생이 안 될 수 있습니다.

