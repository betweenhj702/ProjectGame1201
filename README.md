# 키보드 워리어

## 개요
3명의 팀원과 6일 동안 진행한 첫 프로젝트입니다.<br>
처음 접속한 유저가 선택한 제시어로 게임이 진행되고, 제시어에 관련된 단어를 많이 타이핑한 사람이 승리하는 게임입니다.<br>
자바의 서버소켓과 소켓 객체를 이용하여 온라인으로 최대 4명까지 같이 즐길 수 있습니다.<br>
자바 스윙으로 UI를 구현하였습니다.

## 화면 구성
![GUI](https://user-images.githubusercontent.com/75344320/114371206-3d072480-9bbb-11eb-9172-eeebd07308b0.PNG)


## 객체 다이어그램
![객체 다이어그램](https://user-images.githubusercontent.com/75344320/114371014-0cbf8600-9bbb-11eb-9343-9874df87a4a0.PNG)

 - 역할
    * 서버 객체 : Server Socket 객체를 이용하여 사용자가 접속할 수 있는 서버 역할.
    * OneClientModule 객체: 한 클라이언트가 서버에 접속할 때 또는 데이터를 전달받을 때 필요한 IO 스트림 객체의 모음.
    * MainWindow 객체 : 클라이언트가 접하는 GUI. 서버 접속, 채팅, 게임 진행 중 사용자의 모든 행위가 MainWindowHandler > Client 를 통해 Server로 전달되고 Server에서 Client로 전달된 데이터가 다시 MainWindow 객체에 전달되어 GUI로 표시해준다.
    * MainWindowHandler 객체 : Swing GUI 에서 이벤트 핸들러.
    * Client 객체 : Socket 객체를 가지고 서버와 연결하고, 서버와 데이터를 주고 받는 객체.
    * GameCharacter 객체 : 접속한 클라이언트의 캐릭터 정보(캐릭터 색깔, 이름, 점수 등)을 저장하는 객체. 서버 접속 시, 서버 측과 클라이언트 측에 동시에 만들어 줘 정보를 동기화 한다.
    * GameMode 객체 : 게임의 진행상태를 지정하는 Mode 정보( 게임 준비 상태, 채팅 모드, 게임 시작 모드 등), 서버와 모든 클라이언트 측에서 정보를 동기화해야 한다.
