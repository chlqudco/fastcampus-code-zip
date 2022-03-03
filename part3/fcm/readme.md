 - firebase
   - 앱이나 웹을 보다 쉽게 운영하기 위한 플랫폼
   - Firebase docs에 자세한 설명이 있음
   - 문서를 읽을 때는 영어로 읽는걸 추천
   
 - firebase fcm
   - fcm : firebase cloud messaging

   - 알림 메세지
     - 구현이 쉽지만 여러 케이스에 대응하기 어렵다
     - 서버 구현 없이 noti를 보낼땐 유용하기도 함
     - Firebase 콘솔을 통해 A/B 테스트도 가능 
   
   - 데이터 메세지
     - 앱 자체적으로 처리하기 때문에 구현은 많지만 여러 케이스에 대응하기 좋다
     - 대부분 경우 데이터 메세지를 보낸다

   - 토큰을 가져와서 사용

   - FirebaseMessagingService를 상속받고 onMessageReceived 콜백을 오버라이드
   - onNewToken은 필수 오버라이드
     - 사용자의 토큰은 갱신될 수 있음, 따라서 토큰이 갱신될 때마다 서버에 갱신해줘야함
   - 메세지 수신 될 때마다 처리할 일은 onMessageReceived안에 구현

   - 매니페스트에 service와 intent-filter를  추가해야함
   
   - 20초 이내에 처리 해야 함 

 - notification
   - 단순한 핸드폰 위의 알림창 뿐만 아닌 여러 기능 제공
   - 8.0 이상부터는 알림은 채널에 포함되어야 함
   - 채널의 중요도도 설정해야 함
   - 여러 속성들을 지정 가능, docs 살펴보기
   - 클릭에 대한 이벤트도 걸 수 있음, pendingIntent 이용
