- 소개
	- 실시간 지하철 도착정보를 알려주는 앱입니다.

- 기능
	- 지하철 도착 시간 제공
	- 역 즐겨찾기 기능

- 배우는 것
	- 서울 열린데이터 광장 open api
	- MVP
	- Jetpack Navigation
---

- 서울 열린데이터 광장 open api
	- 여러 open api를 제공해줌
	- 우리는 그 중에 실시간 지하철 도착정보 api를 가져올예정

- MVP
	- 모델 뷰 프레젠터 형식의 아키텍처
	- 다양한 형태로 구현이 가능하다
	- presenter 패키지를 만들고 baseView와 basePresenter 인터페이스를 만든다.
	- data 패키지를 만들고 룸과 레트로핏을 이용하는 코드를 정리

- Jetpack Navigation
	- 싱글 액티비티 구조를 위한 도구
	- 구글이 권장하는 개발 방향
	- 3가지 요소가 있다.
	- 자세한 정리는 summary에 많이 해둠
	- defalutNavHost 속성을 줘

---

- 더 구현해보고 싶은 것

---

- Tip
	- koin의 scope를 처음으로 사용함

---

- 동작 화면

- ![KakaoTalk_20220727_155043212_02](https://user-images.githubusercontent.com/68932465/181180911-a5a3c104-78cf-4bf2-84c4-bbada7aef3e1.jpg)
  ![KakaoTalk_20220727_155043212_01](https://user-images.githubusercontent.com/68932465/181180914-66e5109e-75ee-4feb-b03d-6599b6237b7a.jpg)
  ![KakaoTalk_20220727_155043212](https://user-images.githubusercontent.com/68932465/181180919-ab6d5db8-90f3-4781-935b-1a7b0585aa8c.jpg)
