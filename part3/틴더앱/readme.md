- 소개
	- 틴더 앱의 사용자 호불호 기능을 오마주 한 앱

- 기능
	- Firebase Auth를 이용한 회원가입 및 로그인
	- CardView를 이용한 사용자 호불호 관리
	- 서로 좋아하는 매치 리스트 보기

- 배우는 것
	- Firebase Auth
	- Facebook LogIn
	- Firebase Realtime DB
	- github 오픈소스 라이브러리 이용
	- CardView

---

- Firebase Auth
	- 로그인 기능 구현
	- 이메일, 페이스북 등등 여러 로그인 기능을 도와줌
	- 의존성 추가
	- Firebase.auth 로 쉽게 가져올 수 있음
	- 로그인에 대한 다양한 메소드를 제공함, 편리하게 사용 가능
	- 로그인 메소드에 리스너를 달아서 성공 실패 여부 반환
	- 회원가입도 메소드를 통해 쉽게 사용 가능
	- auth.currentUser 프로퍼티를 통해 현재 로그인 되어 있는지 확인 가능
	- facebook 로그인도 구현 했지만 너무 길어지니 생략
	- auth.currentUser.uid를 통해 uid를 관리하자, 중복되지 않는 값

	-계정 생성 기능
	-1. 의존성 추가
		-tmplementation 'com.google.firebase:firebase-auth-ktx'
	-2. 여러 방법으로 로그인이 가능함	

	-로그인은 보통 별도의 액티비티에서 실행

	-접근 방법 : var auth = Firebase.auth

	-회원 가입 방법

```
		-auth.createUserWithEmailAndPasseord(이메일, 비번)..addOnCompleteListener(this){ task ->
			if(task.isSuccessful){
				회원 가입 성공 메세지 출력 
			}else{
				오류 메시지 출력
			}
```
	
	-로그인 방법

```
		-auth.sigbInWithEnmailAndPassword(이메일, 비번).addOnCompleteListener(this){ task ->
			if(task.isSuccessful){
				메인 화면으로 진입
			}else{
				오류 메시지 출력
			}
		}
```

	-매번 로그인 하기 귀찮으니까
		-매인 액티비티에서 auth.currentUser == null 일때만 로그인 액티비티 실행하기


- Facebook LogIn
	- Firebase Auth를 통해 Facebook 로그인도 할 수 있다.
	- 중간 과정이 상당히 힘들다..
	- Facebook For Developers 홈페이지로 가야 한다
	- 앱 ID와 비밀번호를 받아와서 Firebase에 넣어줘야 함
	- facebook 의존성을 추가하면 전용 버튼과 함수를 사용할 수 있게 된다
	- callbackManager를 통해 로그인을 관리하고 있다
	- credential을 받아온 뒤 firebase에게 전달하며 로그인을 한다

- Firebase Realtime DB
	- 실시간 데이터베이스 연동이 가능함
		- DB값이 바뀌면 바로바로 리스너를 통해 액션을 취함
	- Firestore 는 이거와 다르게 업그레이드 된 기능 느낌?
		- 엄연히 기능이 다름
	- Firebase에서 제공하는 데이터베이스 기능 사용
	- json 형식으로 저장이 됨
	- 따라서 값을 저장하기 위해 Map 형식으로 저장
	- 1. 의존성 추가하기
	- 2. Firebase.database.reference 를 통해 최상위 참조를 가져올 수 있음
		- child(항목이름)을 쓰면 없으면 만들고 있으면 걔 선택
	- 3. map형식으로 값을 담고 updateChildren을 통해 값 넣기 가능
	- 4. DB에서 값을 가져오는 방법 : 리스너를 달기
		- snapshot을 통해 데이터를 넣을 수 있다.
		- 값이 있는지 체크 : snapshot.child("").value == null
		- 1. SingleValueEvent 사용 (코드 사용하는 당장 불러옴)
		- 2. addChildEventListener (일회성이 아님)사용
			- 변경되는 모든 사항이 이 리스너를 탐

	- 실시간 DB연동 가능
	- 설정 가서 json다시 받아서 다시 붙여넣기
	- 의존성 추가
	- 값을 가져올때는 리스너를 달아야함


- github 오픈소스 라이브러리 이용
	- 깃허브 검색창에 원하는 기능을 검색 
	- readme에 사용법이 있으면 그대로 따라하기 
	- Issue나 다른 카테고리에 질의응답이나 정보가 있음

- CardView
	- 진짜 카드 모양으로 보여주는 뷰
	- cradCornerRadius 속성을 통해 얼마나 깎을지 정할 수 있음

---

- 더 구현해보고 싶은 것

---

- Tip
	- AlertDialog 에는 EditText도 붙일 수 있다.
		- setView 함수에 넣고싶은 뷰 넣기
		- 취소 못하게 하는 법 : setCancleabale(false)

---

- 동작 화면

- ![KakaoTalk_20220718_014854240_03](https://user-images.githubusercontent.com/68932465/179416226-8534758a-01f4-4386-9dde-73cac4eec3e9.jpg)
   ![KakaoTalk_20220718_014854240_04](https://user-images.githubusercontent.com/68932465/179416228-a4543e8b-cb9b-4a70-add9-a6db0494455d.jpg)
   ![KakaoTalk_20220718_014854240_02](https://user-images.githubusercontent.com/68932465/179416229-4d48e995-df9b-460b-8fa3-07e63a599ad3.jpg)
   ![KakaoTalk_20220718_014854240_01](https://user-images.githubusercontent.com/68932465/179416230-6944ad14-29db-4313-916d-4a5ba7287852.jpg)
   ![KakaoTalk_20220718_014854240](https://user-images.githubusercontent.com/68932465/179416231-2438d0e8-c259-459f-b4ed-a39923839913.jpg)

