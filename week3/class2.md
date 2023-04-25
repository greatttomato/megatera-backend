## 직렬화 Serialization

 객체를 그 자체로 DB에 저장하거나 네트워크로 전송하는 건 불가능.
 객체를 복구할 수 있도록 데이터화하는 게 필요.
 XML, JSON, YAML 같은 형태가 인기

> 직렬화를 통해서 데이터화 하고, 그 데이터로 다시 객체를 만들어 낸다.

직렬화와 마샬링은 거의 같지만, Java에선 마샬링을 특수하게 다룸.
- 직렬화: 역직렬화를 통해 객체(말 그대로 객체) 또는 데이터(객체까진 아닌 데이터 덩어리? DTO라고도 할 수 있다)의 복사본을 만들 수 있음.
- 마샬링: 직렬화와 같거나, 원격 객체로 복원할 수 있음. 내꺼를 마샬링해서 보냈더니 상대측에서 리모컨을 얻었다? 직렬화 보다 더 넓은 범위.


## JSON (JavaScript Object Notation)

> 사람이 읽고 쓰기에도 좋고, 기계가 분석하고 생성함에도 용이하다. => 가장 큰 장점
> 파싱 JSON.pars('문자열')
> JSON.stringify(객체)

JavaScript의 object는 기본적으로 key-value 쌍이다. (심지어 Array도 제한된 key-value + length 관리에 불과함.)
> 자바스크립트는 프로토타입베이스드 랭기지
Java는 Map이 유사하지만, 스키마 관리 및 타입 안전성(키가 String 이라도 value는 Object일 수 있다 이를 방지)을 위해 DTO를 활용한다.
- 생성: DTO(Java 세계) -> 변환기 -> JSON 문자열
- 해석: JSON 문자열 -> 뱐환기 -> DTO (Java 세계)(겍체로 만들어 준다)

Java에선 Jackson이란 도구(라이브러리)가 유명하고, Spring Boot에서 Web 의존성을 추가하면 바로 사용할 수 있다.
(즉, 딱히 별거 안해도 된다.)

변환할 때 DTO에서 getter 사용해서 읽어옴. @JsonProperty로 속성 이름(key) 지정 가능. 다른 객체(DTO)를 포함하고 있어도 됨.

### JSON 스키마로서의 DTO (class)

=> 프론트와 백 사이에서만 사용된다.
=> 우리가 다룰 DTO는..!
  프론트와 백이 서로 http를 통해 소통할 때 사용되는 http body가 json인! 컨텐트 타입이 application/json인 DTO만 다룰 것이다.
물론 DTO는 여러 곳에서 사용될 수 있다.
DTO(객체 인스턴스) class가 스키마 역할을 하는 것.





JavaScript Good Parts로 
