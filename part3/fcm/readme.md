
### PendingIntent 오류 수정법 : 마지막 인자에 FLAG_IMMUTABLE 넣어줘야함

- 소개
	- Firebase의 Cloud Messaging 서비스를 이용해 푸시 알람을 받아 보는 연습을 한다.

- 기능
	- 일반 알람, 확장형 알람, 커스텀 알람 을 받는다. 

- 배우는 것
	- firebase
	- firebase fcm
	- notification

---

- firebase
	- 앱이나 웹을 보다 쉽게 운영하기 위한 플랫폼
	- 활용도가 매우 높은 서비스를 제공하고 있다
	- 기기마다 Token을 갖고 있어야 함 
	- 구글 클라우드 프로젝트의 하위? 개념이다
	- 프로젝트에 속한 앱은 동일한 서비스를 제공해야만 한다
	- google-services.json 은 건들지 말자
	- 구글이 하란대로 의존성 잘 추가 하자

- firebase fcm
	- 자세한 개념은 공식문서 읽기
	- 두가지 유형이 있다. 알림메세지, 데이터 메세지
	- 알림메세지는 테스트 툴로 매우 쉽게 부를 수 있다.
		- 포그라운드에선 안오니 앱 종료하고 테스트 하기
		- 서버 구현 없이 noti를 보낼땐 유용하기도 함
		- Firebase 콘솔을 통해 A/B 테스트도 가능

- 앱에서 FCM 받기
	- 추가적으로 firebase_messaging-ktx 의존성도 추가
	- 토큰을 가져오려면 FirebaseMessaging.getInstance.token
		- 뒤에 컴플리트리스너 붙여서 안전하게 가져와라
	- FirebaseMessagingService를 상속받고 onMessageReceived 콜백을 오버라이드 해야함
		- 모든 메세지는 20초 이내에 처리되어야 함
		- 매니페스트에 service태그로 등록해야 함
		- intent-filter를 안에 넣어야 됨. 코드는 프로젝트 확인
	- onNewToken은 필수 오버라이드
		- 사용자의 토큰은 갱신될 수 있음, 따라서 토큰이 갱신될 때마다 서버에 갱신해줘야함
	- 메세지 수신 될 때마다 처리할 일은 onMessageReceived안에 구현


- 알림 메세지
	- 구현이 쉽지만 대응하기 힘들다
	- A/B 테스팅을 제공해서 마케팅에 도움이 될 수 있음

- 데이터 메세지
	- 백그라운드던 포그라운드던 앱 자체적으로 처리하기 때문에 구현은 많지만 여러 케이스에 대응하기 좋다
	- 대부분 경우 데이터 메세지를 보낸다
	- 커스텀 타입으로는 정말 많은 방식의 알람을 만들 수 있다
	- RemoteView를 사용하기 때문에 구현하기 복잡함
	- 배경색은 건들지 마세용

- 데이터 메세지 테스트
	- https://firebase.google.com/docs/reference/fcm/rest/v1/projects.messages/send
	- parent는 projects/json에 있는 프로젝트id
	- 나머지는 아래 예시 확인

```
projects/part3-pushalarm

{
  "message": {
    "token": "fb1lVQ2rTaiMt1sIiPagpU:APA91bFPoNze6FPsweWpzIDvxV8g908S1lHzxnIczfrsb2HvFn_E7EcAqX6QkkS-VnO2lqXKrRgxQjmAebg6izNGlcO48B-E_dr9TZSDRi3VGT9NhP2B717HUIayjtO1Q3iqdMkMtACD",
    "data": {
      "type": "NORMAL",
      "title": "일반 알림",
      "message": "일반이지롱!"
    }
  }
}

```

- notification
	- 기능이 굉장히 자주 업데이트 되고 제약이 추가되므로 주의해
	- 단순한 핸드폰 위의 알림창 뿐만 아닌 여러 기능 제공
	- 8.0 이상부터는 알림은 채널에 포함되어야 함
		- 그 이하 버전은 만들면 안됨. 아주 귀찮네
		- 왠만하면 앱을 시작할 때 채널을 만드는걸 권장함
		- 채널의 중요도도 설정해야 함
	- 여러 속성들을 지정 가능, docs 살펴보기
	- 알림 클릭에 대한 이벤트도 걸 수 있음, pendingIntent 이용
		- pendingIntent로 앱을 실행시키는건가? 아닌데. 뭐라 말해야 되지?
	- setAutoCancle로 클릭하면 사라지게 만들기

---

- 더 구현해보고 싶은 것
	- 여기서 말고 실제 서비스에 적절한 알림과 이벤트를 주는 서비스를 구현해 보고 싶다.

---

- Tip
	- RTL
		- 아랍어 같은 경우 글자가 왼쪽부터 시작되니 left right 속성 대신 start end 속성을 쓰는 습관을 들이자

	- Firebase docs에 자세한 설명이 있음
		- 하지만 문서를 읽을 때는 영어로 읽는걸 추천
---

- 동작 화면
   
- ![KakaoTalk_20220716_230301336](https://user-images.githubusercontent.com/68932465/179362428-4a9215b3-b76d-491f-b023-5a8120034f70.jpg)
![KakaoTalk_20220717_004949693](https://user-images.githubusercontent.com/68932465/179362430-c78015bb-3c97-483c-b25a-e819ed962db9.jpg)
