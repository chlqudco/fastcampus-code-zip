- 소개
	- 에어비엔비 처럼 지도에 숙소를 마킹하고 보여주는 앱 입니다.

- 기능
	- 지도에 이용가능 숙소 보여주기
	- 숙소 정보 공유하기
	- 숙소 상세보기

- 배우는 것
	- Naver Map API
	- ViewPager2
	- Coordinator Layout
	- Bottom Sheet Behavior 
	- 외부 공유 기능

---

- Naver Map API
	- 네이버 map api검색
	- 네이버 지도를 이용하기 위한 API
	- 이용신청 후 gradle 파일에 여러 글 쓰기
	- 여러 기능들은 문서 보던가 강의 보던가
	- API 키를 xml에 저장 후 manifest에 meta-data로 등록 
	- xml 에서 MapView를 직접 쓰거나 Fragment를 이용할 수 있음
	- Fragment 사용시 생명주기 관리가 알아서 됨
	- MapView를 직접 쓰면 커스텀이 좋지만 수명주기를 직접 관리해야 함
	- getMapAsync 해줘야함 
	- onMapReady를 통해 map을 다룰수 있음
		- maxZoom 과 minZoom을 통해 확대 축소정도 조절 가능
		- moveCamera 메소드를 통해 보이는 위치를 옮길 수 있음
		- CameraUpdate 객체를 생성하여 위경도 값을 넣어주고 넘겨주기  
	- 현위치 버튼 기능은 간단히 파라미터 값 지정으로 가능
		- isLocationButtonEnabled 값과 퍼미션 지정
		- 퍼미션은 외부 의존성 추가하는 방법도 있음
	- 마커를 찍기 위해 Marker 객체를 생성하고 원하는 파라미터를 지정해주기
		- 클릭 리스너도 달 수 있다

- ViewPager2
	- Viewpager 의 업그레이드 버전
	- Recycler View 기반으로 만들어짐, fragment 전환 효과
	- 페이지 전환마다 이벤트를 등록하려면 registerOnPagerChangeCallback 등록후 원하는 메소드 오버라이드 하기


- Coordinator Layout
	- 프레임 레이아웃에 기능이 추가된 버젼
	- 인터렉션이 중요한 레이아웃을 쓸 때 사용
	- 하나 이상의 뷰와 인터렉션을 할 수 있다.


- Bottom Sheet Behavior 
	- 하단에 숨어있다가 올라오는 느낌의 레이아웃을 구현하고 싶을 때 사용
	- 따로 layout 파일을 하나 만들어서 만들 수 있음
	- 만든 뒤 include 속성 이용해서 추가하고 싶은 파일에 추가
	- layout_behavior 속성과 peekheight 값을 줘야함   

- 외부 공유 기능
	- intent의 chooser 기능 사용
	- intent의 ACTION_SEND 속성 지정
	- 글을 붙이려면 Intent.EXTRA_TEXT 붙이기 

```
	val intent = Intent().apply{action = Intent.ACTION_SEND
			putExtra(Intent.EXTRA_TEXT, "공유 하고자 하는 내용")
			type = "text/plain" <- 타입을 받을 수 있는 애들이 목록?에 나옴}
	startActivity(Intent.createChooser(intent,null))

```

- Mock API
	- 마치 서버에서 내려준 json 파일인척? 하는 애
	- 작성한 json코드를 마치 서버에서 접근할 수 있게 해줌.


---

- 더 구현해보고 싶은 것
	- 뭔가 너무 허접하다.. 뭐가 문젤까..

---

- Tip
	- 다른 xml 파일을 포함하고 싶을땐 include 태그를 사용
	- 랜덤 이미지가 필요할 땐 picsum 사이트 이용
	- Glide에는 이미지 속성을 많이 줄 수 있음
		- centercrop 이라던지.. RoundedCorners 라던지..
	- dp를 px로 변환하려면 TypedValue 클래스를 이용하면 된다

---

- 동작 화면

- ![KakaoTalk_20220720_233224237_02](https://user-images.githubusercontent.com/68932465/180008983-7e2c782b-ba7e-4c7f-97a6-d31b7a3e3d81.jpg)
  ![KakaoTalk_20220720_233224237_01](https://user-images.githubusercontent.com/68932465/180008989-2e6dee24-c379-458b-923e-457e4bd0b90c.jpg)
  ![KakaoTalk_20220720_233224237](https://user-images.githubusercontent.com/68932465/180008993-79a77bd3-77fc-48d9-87a6-80e0fa2f26cf.jpg)


