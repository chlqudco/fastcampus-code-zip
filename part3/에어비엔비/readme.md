- Naver Map API
  - 네이버 지도를 이용하기 위한 API
  - 이용신청 후 의존성 추가
  - xml 에서 MapView를 직접 쓰거나 Fragment를 이용할 수 있음
    - Fragment 사용시 생명주기 관리가 알아서 됨
    - MapView를 직접 쓰면 커스텀이 좋지만 수명주기를 직접 관리해야 함
  - API 키를 xml에 저장 후 manifest에 meta-data로 등록 
  - onMapReady를 통해 map을 다룰수 있음
    - 그 전에 getMapAsync 해줘야함 
  - maxZoom 과 minZoom을 통해 확대 축소정도 조절 가능
  - moveCamera 메소드를 통해 보이는 위치를 옮길 수 있음
    - CameraUpdate 객체를 생성하여 위경도 값을 넣어주고 넘겨주기  
  - 현위치 버튼 기능은 간단히 파라미터 값 지정으로 가능
    - isLocationButtonEnabled 값과 퍼미션 지정
    - 퍼미션은 외부 의존성 추가하는 방법도 있음
  - 마커를 찍기 위해 Marker 객체를 생성하고 원하는 파라미터를 지정해주기


- ViewPager2
  - Viewpager 의 업그레이드 버전
  - Recycler View 기반으로 만들어짐, fragment 전환 효과
  - 페이지 전환마다 이벤트를 등록하려면 registerOnPagerChangeCallback 등록후 메소드 오버라이드 하기

- Coordinator Layout
  - Frame 레이아웃의 진화버젼
  - 인터렉션이 중요한 레이아웃을 쓸 때 사용  


- Bottom Sheet Behavior 
  - 하단에 숨어있다가 올라오는 느낌의 레이아웃
  - 따로 layout파일을 하나 만들어서 만들 수 있음
    - 만든 뒤 include 속성 이용
    - layout_behavior 속성과 peekheight 값을 줘야함   

- 외부 공유 기능
  - intent의 chooser 기능 사용
  - intent의 ACTION_SEND 속성 지정
  - 글을 붙이려면 Intent.EXTRA_TEXT 붙이기 
  
---
- 네이버 지도 API
	-네이버 map api검색
	-1. 그래들에 뭐 여러문장 추가
	-xml에 MapView 추가
	-매니페스트에 메타데이터 추가
	-kt 파일에서 생명주기마다 따라서 써줘야함
	-변수.getMapAsync()로 관리? 가져옴?	
	-여러 기능들은 문서 보던가 강의 보던가

- 뷰페이저 2
	-리사이클러 뷰 기반?



- 프레임 레이아웃




- 코디네이터레이아웃
	- 프레임 레이아웃에 기능이 추가된 버젼
	-인터렉션이 중요한? ui를 쓸때 사용하면 좋음??
	-


- 바텀시트비헤이비어? 다이얼로그?
	-xml에서 <include 



- 레트로핏
	-API를 쉽게 이용하기 위함.
	-json 을 쉽게 쓰기 위해 앵간하면 같이 의존성에 추가



- 글라이드




- 목 API
	-서버 인척 하는 거?
	-작성한 json코드를 마치 서버에서 접근할 수 있게 해줌.



-공유하기 기능
	-val intent = Intent().apply{action = Intent.ACTION_SEND
			putExtra(Intent.EXTRA_TEXT, "공유 하고자 하는 내용")
			type = "text/plain" <- 타입을 받을 수 있는 애들이 목록?에 나옴}
		-startActivity(Intent.createChooser(intent,null))
		


  
