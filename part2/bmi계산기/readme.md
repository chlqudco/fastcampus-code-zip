- 배운 내용
	- LinearLayout
	- TextView, EditText, Button
	- Intent
	- when 분기문
	- 람다 함수
	- Toast 메세지

---

- LinearLayout
	- 컴포넌트들을 선형으로 배치할 수 있다
	- 뷰가 쌓이는 방향을 가로(horizontal)나 세로(vertical)로 지정할 수 있다
	- 여러 개를 중첩하여 grid? 구조를 만들 수 있다
	- gravity 속성으로 위치를 조절할 수 있다

- 여백
	- 화면에서 띄우기 위해서는 margin이나 padding값을 줄 수 있다
	- margin은 컴포넌트 밖에 여백을 추가하는법
	- padding은 컴포넌트 안의 내용물을 줄여서 여백을 준다

- TextView
	- 말그대로 글자를 보여주는 컴포넌트
	- textStyle로 굵게 해줄 수 있다
	- 색깔도 내가 원하는 색으로 지정할 수 있다

- Edittext
	- 사용자의 입력을 받을 수 있는 컴포넌트
	- inputType 속성으로 입력값을 원하는 값만 받을 수 있다 

- Intent
	- 다른 액티비티를 실행하기 위해 사용함
	- 새로 만든 액티비티는 매니페스트에 등록해줘야함.(자동으로 해줌)
	- 인텐트에는 값을 담아서 보내줄 수도 있다
		-putExtra(이름, 값) 으로 주면 됨
	- 도착 액티비티에서 값을 가져오는 법
		- intent.get자료형Extra(이름, 디폴트값)

- when 분기문
	- c언어의 switch와 비슷함
	- 여러 분기 조건에 따라 처리를 할 수 있다

```

val intent = Intent(this, 원하는액티비티클래스::class.java)
intent.putExtra("name", "최병채")
startActivity(intent)

```

---

- Tip
	- values 폴더에 자주 사용하는 문자열이나 컬러값을 지정해 놓는 습관을 들이자
	- EditText가 빈값일 때의 예외처리를 잘 해야 한다
	- 뷰의 id를 헷갈리지 않도록 지어라

---

- 더 구현해보고 싶은 것
	- 사용자의 기록 저장
	- GUI적인 결과 보여주기
	- NumberPicker로 Edittext 대체하기

---

- 동작 화면
![KakaoTalk_20220714_150839705_01](https://user-images.githubusercontent.com/68932465/178912213-dbceef3f-6fbb-46a9-960d-7fb171d8654a.jpg)
![KakaoTalk_20220714_150839705](https://user-images.githubusercontent.com/68932465/178912222-da86aef8-ef71-4684-a74b-a49fe193d41f.jpg)
