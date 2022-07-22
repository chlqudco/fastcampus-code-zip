- 소개
	- 사용자는 원하는 키워드로 위치 검색을 합니다. 결과 목록중 원하는 것을 클릭하면 지도에 어느 위치인지 표시해주는 앱입니다.
- 기능
	- 장소 검색 기능
	- 장소 지도 표시 기능
	- 내 위치 보여주기 기능

- 배우는 것
	- Tmap POI
	- Coroutine
	- Google Map Api

---

- Tmap POI
	- POI = Point of Interest
	- 티맵은 장소 검색 기능?을 제공해 줌
	- 반대로 위도 경도를 통해 위치정보를 가져올 수도 있음
  
- Coroutine
	- 대놓고 설명 안한다고 언급
	- 자세한 내용은 summary에..
  
- Google Map Api
	- 검색 결과를 보여주기 위해 Google map 사용 
	- 얘도 구글 API 에 가서 설정을 해야 함
	- api 키를 메니페스트에 metadata 로 등록해야 함
	- 의존성 추가 후 xml파일에서 fragment 생성 후 구글맵 지정
	- OnMapReadyCallback을 상속받고 오버라이드 해야함
	- 사용법은 그냥 사용서 보고 보기
	- Floting Action Button으로 내 위치 불러오기 기능 구현
		- 기다릴 시간과 거리를 지정할 수 있다.
		- LocationListener를 통해 받아 온다
---

- 더 구현해보고 싶은 것

---

- Tip
	- 함수 선언 뒤에 with(binding) 을 쓰면 편하게 접근 가능
	- ::변수.isInitialized를 쓰면 매번 재생성 안한다?
---

- 동작 화면

- ![KakaoTalk_20220721_175447331_29](https://user-images.githubusercontent.com/68932465/180379562-5987bbc5-06f1-4cbc-8214-f962ed2993d5.jpg)
  ![KakaoTalk_20220721_175447331_28](https://user-images.githubusercontent.com/68932465/180379568-98db8921-ad18-48e9-8e87-28125eb0f447.jpg)
  ![KakaoTalk_20220721_175447331_27](https://user-images.githubusercontent.com/68932465/180379574-5edf2866-a8e9-47db-97a0-afcbccebf7f4.jpg)
