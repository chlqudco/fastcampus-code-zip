- 소개
	- 멜론 처럼 음악을 재생할 수 있는 앱입니다.
	- 사용자의 핸드폰이 아닌 인터넷에서 음원을 받아옵니다.

- 기능
	- 음악 재생 기능

- 배우는 것
	- Custom Seekbar
	- Constraintlayout Group 
	- mapper

---

- Custom Seekbar
	- 시크바에 여러 속성을 추가해서 다양하게 꾸밀 수 있음
	- 채워지는 곳의 색깔 : progressTint
	- 조절 하는거 : thumb
		- 없애기 : clickable = false
	- drawable xml 파일로 프로그래스 막대?를 꾸밀 수 있음
		- progressDrawable 속성에 지정
	- 높이를 강제로 조절할 수 있음
		- maxHeight랑 minHeight
	- 1초마다 업데이트 하는건 핸들러의 postDelayed 함수를 이용하면 좋다

- Constraintlayout Group 
	- 그룹을 나눠서 동시에 보이거나 안보이게 할 수 있음
	- app:constraint_referenced_idx 에 id들을 욱여넣기  
	- 특정 버튼에 클릭리스너로 Group을 조작할 수 있음
		- 그룹id.isVisible로 간단하게 가능

- mapper
	 - 서버에서 가져온 Entity를 우리가 사용할 Model로 바꾸는 작업을 해줌

---

- 더 구현해보고 싶은 것
	- mocky 말고 내 핸드폰의 음악을 가져오는 앱
---

- Tip
	- 이미지뷰 안의 icon 색깔은 tint 속성으로 바꿔봐라
	- drawable에 최상위를 layer-list 태그를 통해 여러 값을 지정해보자
---

- 동작 화면

- ![KakaoTalk_20220721_175454138](https://user-images.githubusercontent.com/68932465/180237146-3b558604-981a-4ca4-bbb3-780af6eaa2c7.jpg)
  ![KakaoTalk_20220721_175447331_29](https://user-images.githubusercontent.com/68932465/180237154-97875926-c7b5-41bb-9d68-ca99240de305.jpg)

