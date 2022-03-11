- 작성중 컴퓨터 다운되어서 다시 작성^^

- Bottom Navigation View
  - 아이템 클릭에 따라 다른 프래그먼트를 보여줄 수 있음
  - 1.menu 폴더를 만들고 xml파일을 만들기
  - 2.item 태그에 id 와 icon, title 지정해주기
  - 3.색깔을 지정하기 위해 drawable폴더에 selector 파일 만들기
    - item 태그에 state와 color값 부여 
    - app:itemIconTint속성에 넣어주기
  - kt파일에서는 itemId값으로 분기해서 작업을 처리해줄 수 있음

- Firebase Storage
  - 1. 저장할 파일 이름 지정
  - 2. storage.reference.child와 같이 DB와 접근 방식이 같음
  - 3. 기록은 putFile()로 넣어주고 Complete리스너로 확인
  - 4. 가져오는 법은 downloadUrl 프로퍼티를 사용, 리스너 달기

- Floating Action Button
  - 최상위에 떠 있는 것처럼 보이는 버튼 
  - src속성으로 안에 drawable 이미지도 넣을 수 있음
  - tint와 backgroundTint 속성으로 색깔 변경

- 채팅 기능 구현
  - Firebase Realtime DB를 이용한 채팅 기능 
  - 채팅방 Model 을 만들고 DB에 저장
