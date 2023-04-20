# Collection Pattern
> 그룹명은 복수형으로 사용하기 때문에 collection(items)이 아니라 element(item)를 지정할 때도 복수형이 쓰인다<br/>
> posts/1 => 복수형으로 그룹명을 지정하고 그 아래에서 개별 아이템을 지정<br/>
> post/1 => 흔히하는 실수<br/>
> ? : searchQuery<br/>
> /posts/{id}/edit == /edit?post_id={post_id}

Q. 솔직히 이해가 잘 가지 않는다 url을 깔끔하게 규칙에 따라 만든다는 것일까
   추후 학습 필요

<br>

# Collection Pattern 적용
## CRUD
1. Create
2. Read
3. Update
4. Delete

<br>

### CRUD 특성에 따른 구분
1. Command  : Create, Update, Delete : 상태가 변한, 안전 X
2. Query    : Read : 상태가 변하지 X. 안전. 분산, 캐시 등이 수월

### HTTP Method
> Collection Pattern과 HTTP Method를 이용해 CRUD를 표현할 수 있다.
1. GET -> Read
2. POST -> Create
3. PUT, PATCH -> Update
4. DELETE -> Delete

### 게시물
1. GET/post
   : 게시물 목록(Read, Collection) => List (습관적인 표현 중 하나)
2. GET/posts/{id}
   : 게시물 상세(Read, Element) => Detail (정해진 것은 아니나 통상적, 습관)
3. POST/posts
   : 게시물 생성 (Create) => POST ID는 서버에서 생성함
4. PUT 또는 PATCH/posts/{id}
   : 게시물 수정 (Update, Element)
5. DELETE/posts/{id}
   : 게시물 삭제 (Delement, Element)

종종 Bulk update, Bulk delete 등을 하기도 함. 이럴 때는 Collection을 활용하고, API 스펙 문서에 정확히 기록.<br>
Q. Bulk update가 먼데<br>
A. 전체 업데이트<br>

### 댓글
> 바로 comments로 시작하는 경우
1. GET/comments                        : 전체 댓글 목록  
2. GET/comments?post_id={post_id}      : 특정 게시물에 대한 댓글 목록
3. GET/comments/{id}                   : 댓글 상세
4. POST/comments                       : 댓글생성 => 어떤 게시물? (Body에 Post ID 정보를 담아야)
5. POST/comments?post_id={post_id}     : 특정 게시물에 대한 댓글 생성
6. PUT 또는 PATCH/comments/{id}         : 댓글 수정
7. DELETE/comments/{id}                : 댓글 삭제

### 로그인/로그아웃
> 로그인/로그아웃을 리소스로 표현하기 위해 세션 도입 <br> 굉장히 추상적
1. POST/session      : 세션 생성 (로그인)
2. DELETE/session    : 세션 파괴 (로그아웃) <br>
+α)
3. GET/session       : 세션 확인 (내 장보 확인)
4. GET/users/me  : User ID를 me라고 쓰면, 현재 사용자의 User ID로 처리하게 정하고, API 스펙 문서에 기록.
   Q. 세션에 저장된 로그인 정보 아이디를 me로 대신 표현한다? 

Q. POST/accesstoken ?