### keyword
> 1. TCP/IP 통신
> 2. TCP, UDP
> 3. Socket과 Socket API 구분
> 4. URI, URL
> 5. Host
>>  - IP Address
>>  - Domain name
>>  - DNS
> 6. Port
> 7. Path

# HTTP Client

## TCP/IP 통신
> - TCP/IP != TCP 프로토콜 <br>
> - TCP/IP = 인터넷 프로토콜 스위트(Internet Protocol Suite)

### TCP & UDP
1. TCP : 연결 필요. 전달 및 순서 보장 (ex. 전화) => web
2. UDP : 연결 X. 전달 및 순서 보장 X (ex. 편지)

### Socket
> socket이라하면 socket api으로 쓰이는데 그 안에 socket이 있어요 <br>
> 비틐코인은 프로토콜인데 거기서 쓰이는 화폐도 비트코인인 것 처럼
1. Socket(네트워크 소켓, 종착점 end point) : 기본적으로 파일과 유사하게 다룰 수 있다. 
2. Socket API(Berkeley socket, BBS socket) : 종착점 간 연결돼서 어떻게 통신할지 프로그래밍 하는 것 <br>
=> Java에서는 Stream으로 다룰 수 있다. (자바 8에서 도입된 Stream API가 아님)
<br>
❓ 그냥 stream, Java8에서의 stream

### TCP 통신 순서
1. 서버는 접속 요청을 받기 위한 소켓을 연다 -> Listen
2. 클라이언트는 소켓을 만들고 서버에 접속을 요청 -> Connect
3. 서버는 접속 요청을 받아서 클라이언트와 통신할 소켓을 따로 만든다 -> Accept
4. 소켓을 통해 서로 데이터를 주고 받는다 -> Send & Receive (반복)
5. 통신을 마치면 소켓을 닫는다 -> Close (상대방은 Receive로 인지 가능) <br>
=> Client : 2, 4, 5번 처리

## HTTP 클라이언트
### 🍊 Connect
> 호스트는 IP 주소 또는 도메인 이름을 사용할 수 있다. <br>
> 도메인 경우 DNS를 활용하기 때문에 제대로 하려면 복잡해질 수 있으나 알아서 처리해 준다. <br>
>> String host = "example.com"; <br>
>>  http, https 둘 다 지원

- HTTP 기본 포트 번호 : 80
- IP 주소와 포트 번호만 알면, 서버에 접속할 수 있다.
  ''' Socket socket = new Socket(host, port); '''
=> 자바에서는 소켓 생성하며 바로 접속 요청, 실패하면 ConnectException 예외 처리



### intellJ 단축키
- cmd + shift + T : 테스트 코드로 이동
- cmt + , : settings
- option + enter : create method

### intellJ
> - gradle init
> - generate: 2.application <br>
> - language: 3.Java <br>
> - DSL: 1.Groovy <br>
> - framework: 4.JUnit Jupiter
- settings > Actions on Save > Reformat code, Optimize imports 체크 : cmd + shift + o 가 저장할 때 자동으로 됨 
- terminal > ./gradlew run : gradle 실행 (run)