

5. 전자 액자
   - Runtime Permission
     - 민감한? 정보나 기능을 다룰 때는 사용자의 권한을 받아와야 함 
     - 거절한 유저를 위해 교육용 뷰를 보여줘야 함
     - ContextCompat.checkSelfPermission(context, 권한)==PackageManager.PERMISSION_GRANTED으로 권한 있는지 체크
     - shouldShowRequestPermissionRational 함수로 교육용 팝업 띄워야 하는지 확인
     - 실제 권한 요청 : requestPermissions(권한 배열, 요청코드)
     - onRequestPermissionResult 함수를 오버라이드 하여 결과 처리
   - View Animation
     - 뷰.animate().속성().setDuration(초).start()
   - Content Provider
     - 이 앱에선 SAF를 이용 
     - intent.ACTIOC_GET_CONTENT 
   - LifeCycle 
     - 액티비티의 생명주기를 잘 알고 있어야 함
   - Timer
     - 일정 시간 마다 람다식 안의 내용 실행   

배우는것

1. 권한
2. 뷰 애니메이션
3. 컨텐츠 프로바이더
4. 라이프 사이클

개발 순서

1. 기본 xml 그리기
	-사진 추가하기 버튼, 전자액자 시작 버튼

2. 사진 추가 버튼에 권한 받는 기능
	-when {   check셀프퍼미션함수 호출 -> 권한이 있는지}
		교육용 팝업 띄우는 함수 -> {교육용 팝업 띄우기(AlertDialog)}
		else -> {권한 요청, requestPermissions(권한 배열, 요청코드)}

3. xml에 사진 칸 만들기, 리니어레이아웃에 이미지뷰 3개
	-레이아웃에 Ratio 주기
	-이미지 뷰에 scaleType 을 centerCrop으로 자르면서 1대1로

4. kt에서 리스트 형식으로 이미지뷰 다루기, mutableListof . apply{add(~~)}

5. onRequest어쩌구 함수로 결과 받아오기
	-when(요청코드로 내가 원하는건지 확인)
	-grandResults로 수락했는지 확인

6. 사진을 가져오는 함수 만들기
	-Intent로 간단하게 구현 가능(컨텐츠 프로바이더, SAF)

7. Uri저장하는 리스트 만들기

8. onActivity리절트 함수 구현
	-RESULTOK인지 먼저 확인
	-리퀘스트코드로 분기
	-사진 Uri 가져오고 두 리스트에 추가
	-6개 넣으면 예외처리

9. 새로운 액티비티 하나 만들기

10. 스타트포토프레임버튼 함수 만들기
	-인텐트로 9번 액티비티로 이동
	-UriList를 문자열 형태로 보내야됨
	-리스트의 사이즈도 같이 보내줘

11. 액자모드 kt파일 설정
	-리스트의 사이즈 만큼 Uri를 얻어오기
	-리스트를 하나 선언하고 거기에 얻어온 Uri넣기

12. 액자모드 xml파일 설정
	-두개의 이미지뷰를 넣고 바꾸는 형식
	-scaleType은 센터

13. 다시 액자모드 kt에서 두 이미지뷰 변수선언 하고
	-타이머를 열고 애니메이션을 설정함
	-현재 인덱스와 다음 인덱스를 가지고 복작복작

14. onStop일때 타이머 캔슬
	-onStart일때 다시 실행
	-onDestroy일때 타이머 캔슬
	-메인함수에 있는건 버려

15. 핸드폰 가로로 돌려
	-방향 랜드스케이프
	-툴바 없애

더 구현해볼 것

1. 모르겠는게?

![KakaoTalk_20220715_021703297_01](https://user-images.githubusercontent.com/68932465/179044191-c5be3410-1bbc-4b97-8cb2-e5790d97e09f.jpg)
![KakaoTalk_20220715_021703297](https://user-images.githubusercontent.com/68932465/179044200-967709cd-5125-441a-987e-44329be41ae6.jpg)


