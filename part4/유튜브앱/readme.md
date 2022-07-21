- 소개
	- 유튜브 처럼 동영상을 재생하는 앱 입니다.

- 기능
	- 동영상 재생

- 배우는 것
	- Motion Layout
	- Exoplayer

---

- Motion Layout
	- 컨스트레이아웃의 서브 클래스
	- 사용자의 모션에 따라 UI의 크기나 모양변환이나 애니메이션을 쉽게 구현해줌
	- 열고 닫는 시점의 Constraint Set으로 애니메이션 효과
	- 최상위 constraint 레이아웃을 모션 레이아웃 으로 바꾸면 xml폴더와 xml파일이 하나 생김
	- 애니메이션 효과 넣는 법
		- 원하는 state에서 원하는 id선택 후 연필 모양 눌러서 create Constraint 지정
		- xml파일에서 constraint set 에 직접 제약 걸기
		- timetable 에서 원하는 속성을 지정
	- 드래그 이벤트를 걸기 위해서는 swipe Handler등록
		- 맨 오른쪽
	- 같은 레이아웃 내의 서로 다른 뷰를 연동하기 위해서는 fragment kt 파일에서 작업
		- 모션레이아웃에 setTransition리스너 등록
		- 4개 오버라이드한 메소드중 change에서 상대방 모션레이아웃 가져와서 값 주기 	
		- (모션레이아웃.progress)
		- 프래그먼트는 자기가 붙어있는 액티비티만 가져올 수 있음
	- 터치 이벤트 흘리기
		- 모션 레이아웃을 커스텀해야 함
		- 터치 이벤트와 인터럽트터치이벤트를 오버라이드 해야함, 코드 확인
		- 내가 원하는 영역을 터치했는지 체크하기
	- 애니메이션 변하는 정도? 를 조절하려면  
		- 타이머 버튼 눌러서 Add속성 추가해서 원하는 값 바꾸기
		- 속성이 아주 많으니 강의나 Document 살펴보기


- Exoplayer
	- 구글이 만든 오픈소스 라이브러리
	- 오디오 및 동영상 재생 가능 및 여러 강력한 기능들 포함
	- 실제 유튜브에서 사용하는 라이브러리
	- 빌더를 만들고 play할 수 있음
		- 데이터소스팩토리, 미디어소스 등 준비과정이 필요함
	- 생명주기를 잘 관리해줘야 함 
	- 리스너를 달 수 있음
		- Event리스너를 통해 여러 메소드 구현 가능 

---

- 더 구현해보고 싶은 것

---

- Tip
	- 뷰를 강제로 내리거나 올리고 싶으면 tranlation좌표 값 넣기
	- Fragment가 자신이 붙어있는 액티비티 가져오려면 activity as MainActivity 속성 쓰면 됨
	- 그 반대는 supportFragmentManager.fragments.find{it is 원하는프래그먼트}

---

- 동작 화면
 
-  ![KakaoTalk_20220721_175454138_02](https://user-images.githubusercontent.com/68932465/180175369-899da341-8d5e-49ac-a7bd-05d20dc74c45.jpg)
  ![KakaoTalk_20220721_175454138_03](https://user-images.githubusercontent.com/68932465/180175376-0dec9bda-060a-4fe7-a8b8-8e7f82cce0db.jpg)


