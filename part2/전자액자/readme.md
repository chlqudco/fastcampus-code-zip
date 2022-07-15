- 소개
	- 선택한 사진들을 전자액자 형태로 전환하며 보여주는 앱

- 기능
	- 사진 불러오기
	- 사진 변환하며 보여주기

- 배우는 것
	- 가로 화면으로 그리기
	- 권한
	- 뷰 애니메이션
	- 컨텐츠 프로바이더(SAF)
	- 라이프 사이클

---

- Permission
	- 민감한? 정보나 기능을 다룰 때는 사용자의 권한을 받아와야 함 
	- 매니페스트에 어떤 권한을 사용하는지 적어줘야 함
	- 이미 권한이 부여되어 있는지 확인해야 함
		- ContextCompat.checkSelfPermission(context, 권한)==PackageManager.PERMISSION_GRANTED
	- 거절한 유저를 위해 교육용 뷰를 보여줘야 함
	- 거절한 이력이 있어서 교육용 팝업 띄워야 하는지 확인
		- shouldShowRequestPermissionRational(권한)
	- 실제 권한 요청
		- requestPermissions(권한 배열, 요청코드)
	- 결과 처리
		- onRequestPermissionResult 함수 오버라이드


- View Animation
	- 뷰에 애니메이션을 줘서 부드럽게 전환하는 효과를 낼 수 있음
	- 뷰.animate().속성().setDuration(초).start()


- Content Provider
	- 개념 적인 것은 summary에 정리
	- 다른 앱에 저장 된 사진을 가져오는 개념이므로 컨텐츠 프로바이더 사용
	- 이 앱에선 그 중에서 SAF라는 기능을 사용
	- 같은 SAF를 이용하는 기능은 사용자에게 같은 화면을 보여주므로 사용자 친화적임
		- intent.ACTIOC_GET_CONTENT , intent.type = "image/*" 하면 이미지만 가져오도록 함
		- 이미지의 반환값은 Uri
		- 이미지뷰에 등록하고 싶으면 imageView.setImageURI() 로 등록
	- 선택한 걸 받아오려면 onActivityResult 함수를 오버라이드


- LifeCycle 
	- 개발할 때 액티비티의 생명주기를 잘 알고 있어야 함
	- onCreate, onStart, onResume 순서로 호출 뒤에 액티비티가 러닝된다
	- onPause, onStop, onDestroy 호출 뒤에 액티비티가 종료된다
	- onStop 상태 뒤에 다시 실행 될 때는 onRestart가 호출 된 뒤 onStart, onResume이 호출 된다.
	- 각 함수에 대한 설명은 공식문서 확인

- Timer
	- 일정 시간 마다 람다식 안의 내용 실행 해주는 객체
	- timer(몇초마다){ 여기 안은 쓰레드 입니다.  }
	- UI를 바꾸려면 runOnUiThread로 바꾸기
	- 액티비티 생명주기에 잘 동화되어야 함
	- onStop 일때 timer.cancle 해줘야 함
	- onDestroy가 되는 경우에도 timer.cancle
	- onstart가 된다면 새로운 타이머를 생성

---

- 더 구현해보고 싶은 것
	- 디자인 수정

---

- Tip
	- 레이아웃에 Ratio 속성을 주면 비율대로 레이아웃을 설정할 수 있다.
		- H, 3:1 을 주면 가로 세로 3:1
	- Uri를 넘길 때는 String으로 넘기고 받는 쪽에서 Uri.parse로 바꾸면 된다
	- 가로 화면으로 보고 싶을 때 매니페스트에 screenOrientation에 landscape값 주면 됨
---

- 동작 화면

- ![KakaoTalk_20220715_021703297_01](https://user-images.githubusercontent.com/68932465/179044191-c5be3410-1bbc-4b97-8cb2-e5790d97e09f.jpg)
   ![KakaoTalk_20220715_021703297](https://user-images.githubusercontent.com/68932465/179044200-967709cd-5125-441a-987e-44329be41ae6.jpg)


