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

---
-Firebase Auth
	-계정 생성 기능
	-1. 의존성 추가
		-tmplementation 'com.google.firebase:firebase-auth-ktx'
	-2. 여러 방법으로 로그인이 가능함	

	-로그인은 보통 별도의 액티비티에서 실행

	-접근 방법 : var auth = Firebase.auth

	-회원 가입 방법
		-auth.createUserWithEmailAndPasseord(이메일, 비번)..addOnCompleteListener(this){ task ->
			if(task.isSuccessful){
				회원 가입 성공 메세지 출력 
			}else{
				오류 메시지 출력
			}
	
	-로그인 방법
		-auth.sigbInWithEnmailAndPassword(이메일, 비번).addOnCompleteListener(this){ task ->
			if(task.isSuccessful){
				메인 화면으로 진입
			}else{
				오류 메시지 출력
			}
		}

	-매번 로그인 하기 귀찬흥니까
		-매인 액티비티에서 auth.currentUser == null 일때만 로그인 액티비티 실행하기


-Firebase Realtime DB
	-실시간 DB연동 가능
	-설정 가서 json다시 받아서 다시 붙여넣기
	-의존성 추가
	- 값을 가져올때는 리스너를 달아야함

-AlertDialog
	-AlerDialog.Builder(this).setTititle("").setView(뷰를 넣을수도 있음).setPositiveButton("화긴"){_,_->  }.setCancleable(false)<-뒤로가기 못하게.show()



-CardStackView
	-깃헙에서 가져온 라이브러리

