- Firebase Auth
  - 로그인 기능 구현
  - 이메일, 페이스북 등등 여러 로그인 기능을 도와줌
  - 1. 의존성 추가
  - 2. Firebase.auth 로 쉽게 가져올 수 있음
  - 3. 로그인에 대한 다양한 메소드를 제공함, 편리하게 사용 가능
  - 4. 로그인 메소드에 리스너를 달아서 성공 실패 여부 반환
  - 5. 회원가입도 메소드를 통해 쉽게 사용 가능
  - 6. auth.currentUser 프로퍼티를 통해 현재 로그인 되어 있는지 확인 가능
  - 7. facebook 로그인도 구현 했지만 너무 길어지니 생략

- Firebase Realtime DB
  - Firebase에서 제공하는 데이터베이스 기능 사용
  - 1. 의존성 추가하기
  - 2. Firebase.database.reference 를 통해 최상위 부모를 가져올 수 있음
  - 3. map형식으로 값을 담고 updateChildren을 통해 값 넣기 가능
  - 4. DB에서 값을 가져오는 방법 : 리스너를 달기 (이해가 잘 안감)
    - 1. SingleValueEvent 사용 (한번만 불러옴)
      - snapshot을 통해 데이터를 넣을 수 있다. 
    - 2. addChildEventListener (일회성이 아님)사용
  


- github 오픈소스 라이브러리 이용
  - 깃허브 검색창에 원하는 기능을 검색 
  - readme에 사용법이 있으면 그대로 따라하기 
  - Issue나 다른 카테고리에 질의응답이나 정보가 있음
