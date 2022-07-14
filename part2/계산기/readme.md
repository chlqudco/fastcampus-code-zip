- 소개
	- 삼성의 기본 계산기 앱을 따라하는 앱입니다.
- 기능
	- 하나의 연산자만 적용되는 계산기
	- 계산 기록 저장 및 열람
	- 계산 기록 삭제

- 배우는 것
	- TableLayout
	- LayoutInflater
	- Thread
	- Room DB 
	- 확장 함수
	- data class

---


- TableLayout
	- 격자구조에서 유용하게 사용할 수 있는 레이아웃
	- 한줄을 추가하려면 TableRow 태그를 써야함
		- 가중치를 통해 똑같은 높이를 갖게 할 수 있음
	- 바깥으로 삐져나가지 않게 하기 위해 shrinkColums = "*" 속성 지정


- LayoutInflater
	- 작게작게 뷰를 xml 파일로 쪼개서 사용할 수 있는데, 이 때 xml 파일을 메모리에 올려줄 수 있게 도와주는 친구
	- 반복적으로 쓰는 뷰를 잘라내서 사용?
	- 쉽게 말해 레이아웃을 동적으로 생성해서 사용함
	- xml 파일로 item 이던 뭐던 뷰를 만들었는데 그걸 동적으로 가져와서 사용가능하게 해줌
	- val 변수이름 = LayoutInflater.from(context).inflate(xml파일, null, false) 으로 생성 후 view 에 addView 하면 끝


- Thread
	- 계산 기록을 백그라운드 쓰레드로 저장하기 위해 쓰레드를 사용
	- 잠깐 UI작업을 하기 위해 runOnUiThread 사용
	- Thread(Runnable{ 할일 }).start() 로 쉽게 백그라운드에서 할일을 지정할 수 있다
	- Runnable 안에서 runOnUiThread {  } 열면 Main 쓰레드를 사용함	

- ScrollView
	- 뷰가 길어지면 스크롤 할 수 있는 기능을 자동으로 제공해줌
	- 안에 레이아웃 넣어야 돼!!


- Room DB 
	- 로컬 DB에 데이터를 저장할 수 있도록 도와주는 도구
	- 사용법은 역시나 summary에 자세히 정리, 여기선 생략
	- 어떤 형식으로 저장할 것인지 잘 생각하세용
	- model 패키지를 새로 만들고 모델이 될 data class 를 만들자
		- @Entity 어노테이션 주면 됨
		- 각 변수에도 적절한 어노테이션을 달아주세요

- 확장 함수
	- 기존 클래스에 메소드를 추가하는 것
	- ex) fun String.isNumber(): Boolean{} 
	- 마치 이 클래스에 원래 있었던 내장 함수 인양 사용 가능


- data class
	- Model 클래스에 자주 쓰는 클래스 형태
	- 4개의 함수가 자동으로 생성됨

- SpannableStringBuilder
	- 문자열 중간의 특성을 바꿀 수 있음. 맞나?
	- 코드로 문자열을 꾸밀 수 있다고 이해하면 되나?
	- setSpan(뭘 바꿀껀지, 시작부분, 어디까지 적용할건지, 마지막은 뭔지 설명 없음)
	- ex) setSpan(ForegroundColorSpan(getColor(R.color.green)), text.length -1, text.length, Spannable.SPAN어쩌구 )
	- 마지막에 text 속성값 재지정

---

- 더 구현해보고 싶은 것
	- 완벽한 후위수식 계산기 구현

---

- Tip

- drawable
	- 버튼의 ripple 속성을 유지하기 위해 바깥에 ripple을 씌움, 뭔소리야;
		- ripple은 버튼 눌렀을 때 퍼지는? 속성? 을 의미
		- 색상 속성 지정 필수
		- 배경을 지정하려면 item 태그로 감싸야 함
		- item 태그안은 원래 하던 대로 작성


- button
	- stateListAnimator = "@null" 속성 지정하면 그림자 사라짐. 2D 느낌
	- AppcompatButton 으로 박꾸고 background를 @null 로 하면 투명 버튼 만들 수 있음

- 레이아웃.removeAllViews() 를 하면 안에 있는 모든 뷰들을 없애줌

---

- 동작 화면
- ![KakaoTalk_20220715_001423350_01](https://user-images.githubusercontent.com/68932465/179016765-2fbb6481-e5fb-4d62-ae4c-da6904d71e19.jpg)
   ![KakaoTalk_20220715_001423350](https://user-images.githubusercontent.com/68932465/179016771-907a68b2-a89d-44d4-86bf-418ef9d8124d.jpg)

   
