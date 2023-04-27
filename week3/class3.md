## Jackson ObjectMapper

⚠️ 실습있음

Jackson ObjectMapper를 사용해서 DTO를 JSON(문자열)으로 변환하거나, JSON(문자열)을 DTO로 변환할 수 있다. <br>
<br>
먼저, DTO를 위한 class를 만든다. <br>
ex. <br>
JSON 스키마 <br>
{ <br>
  "id": "1234", <br>
  "title": "제목", <br>
  "content": "테스트" <br>
} <br>
<br>
<br>
String DI를 통해 컨트롤러에서 Jackson ObjectMapper를 얻는다.<br>
스프링이 등록된 객체(Bean)를 관리하고 있고, 생성자에 명시하면 받아서 사용할 수 있다.<br>
내가 사용하고 있다 = 의존하고 있다.<br>
의존하고 있다 = 의존관계가 있다.<br>




