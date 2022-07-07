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

---
-바텀 내비게이션 뷰
	-아래에 아이콘 클릭에 따라 프래그먼트를 바꾸는? 거
	-들어가는 아이콘은 메뉴 xml파일을 만들면 됨
		-<item 태그 안에 id와 title, icon지정/>
	-셀렉터 : 상태마다 다른? 모양을 표출해줌
		-드로어블에 xml파일 만들고 으음.. 색깔과 state_checked="true"랑 false 두가지 지정
		-내비 뷰에 지정 : app:itemIconTint로 지정
	-글자 색깔 : app:itemTextColor로 지정
	-리플 효과 삭제 : app:itemRippleColr= "@null"

	-코틀린에서 조작
		-변수.setOnNavigationOtemSelectedListener{
			when(it.itemId){
				R.id.이름 ->
			}
			return true
		}

-Firebase Storage




-Fragment
	-앵간하면 프레임레이아웃으로 만듬
	-클래스에서 쉽게 뷰 연결하는법
		-class 이름: Fragment(R.layout.이름)
	-코틀린에서 메인엑티비티에서 클래스 생성 쳐 하고 쓰셈 
	-화면 전환 
		-supportFragmentManager.beginTransaction().apply{
			replace(R.id.프레임레이아웃이름, 프래그먼트 변수)
			commit()
		}
	-생명주기 관리를 잘해줘야함
	-onViewCreated안에서 평소처럼 쓰면 됨


-문자열을 날짜 형식으로 바꾸기
	-val format = SimpleDateFormat("MM월 dd일")
	-val date= Date(변수)
	- 변수.text = format.format(date).toString


--?? 리얼 타임 DB쓸때는 데이터 클래스에 빈 생성자가 필요하다고?? 왜?
	-constructor(): this(아무값 변수 할당)


-FloatingActionButton
	- 떠 있는 모습을 갖게 하는 버튼
	- 배경 바꾸는법 : 백그라운드틴트
	-안에 이미지 넣는법 = src
		-app:tint로 색깔변경


-채팅 기능 구현
	-Firebase 리얼타임 DB를 이용해 구현
	-채팅 목록은 리사이클러뷰로





