## HTTP 서버

⚠️ 실습 있음

### 1️⃣ Listen
다른 곳에 접속하는 게 아니라 포트 번호만 정하면 된다.

  `int port = 8080;`

Java에서는 ServerSocket이라는 별도의 클래스를 사용. <br>
리슨하는 애로는 send receive 안 할테니 리슨 용도로 따로 만들어 준 것. <br>

  `ServerSocket listener = new ServerSocket(port);`

I/O에서 이렇게 기다리는 걸 Blocking이라고 한다. <br>
파일 읽기, 쓰기 등도 모두 Blocking 동작이지만, TCP 통신에서는 네트워크 상태 등 다양한 요인에 의해 멈출 수 있다. <br>
accept처럼 상대의 요청이 없으면 영원히 기다리는 일이 벍어질 수 있다. 멀티스레드나 비동기, 이벤트 처리 등이 필요한 이유 <br>

### 2️⃣ Request
서버는 요청을 하는 게 아니라, 요청을 받는다. <br>
따라서 먼저 읽어야 한다. <br>

### 3️⃣ Response
클라이언트의 요청과 마찬가지로, 응답 메시지를 만들어서 전송하면 된다.


-- > 18분 20초 부터 