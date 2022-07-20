- 소개
	- 당근마켓을 조금 따라한 중고거래 앱입니다. 원하는 아이템을 올린 사용자와 채팅을 할 수 있습니다 

- 기능
	- 아이템 등록
	- 실시간 채팅

- 배우는 것
	- Bottom Navigation View
	- Firebase Storage
	- Floating Action Button
	- 채팅 기능 구현
	- Fragment
---

- Bottom Navigation View
	- 하단에 탭을 넣어서 화면을 이동할 수 있게 해주는 기능
	- 아이템 클릭에 따라 다른 프래그먼트를 보여줄 수 있음
	- 1.menu 폴더를 만들고 xml파일을 만들기
	- 2.item 태그에 id 와 icon, title 지정해주기
	- 3.색깔을 지정하기 위해 drawable폴더에 selector 파일 만들기
		- item 태그에 state와 color값 부여 
		- app:itemIconTint속성에 넣어주기
		- 글자 색깔 : app:itemTextColor로 지정
	- 셀렉터 : 상태마다 다른? 모양을 표출해줌
		- 드로어블에 xml파일 만들고 으음.. 색깔과 state_checked="true"랑 false 두가지 지정
	- kt파일에서는 itemId값으로 분기해서 작업을 처리해줄 수 있음
	- 들어가는 아이콘은 메뉴 xml파일을 만들면 됨
		- <item 태그 안에 id와 title, icon지정/>
		- 내비 뷰에 지정 : app:itemIconTint로 지정
	- 리플 효과 삭제 : app:itemRippleColor= "@null"

	- 아래에 아이콘 클릭에 따라 프래그먼트를 바꾸는 작업
	- 코틀린에서 조작

```
		- 변수.setOnNavigationOtemSelectedListener{
			when(it.itemId){
				R.id.이름 -> supportFragmentManager.beginTransaction().apply{ replace(R.id.컨테이너, 원하는 프래그먼트) commit()}
			}
			return true
		}

```

- Firebase Storage
	- 이미지나 파일을 업로드 할수 있는 저장소 기능
	- storage-ktx 의존성을 추가해야 함
	- 1. 저장할 파일 이름 지정
	- 2. storage.reference.child와 같이 DB와 접근 방식이 같음
	- 3. 기록은 putFile()로 넣어주고 Complete리스너로 확인
	- 4. 가져오는 법은 downloadUrl 프로퍼티를 사용, 리스너 달기

- Floating Action Button	
	- 최상위에 떠 있는 것처럼 보이는 버튼 
	- src속성으로 안에 drawable 이미지도 넣을 수 있음
	- tint와 backgroundTint 속성으로 색깔 변경
	- 배경 바꾸는법 : 백그라운드틴트
	- 안에 이미지 넣는법 = src
		- app:tint로 색깔변경

- 채팅 기능 구현
	- Firebase Realtime DB를 이용한 채팅 기능 
	- 채팅방 Model 을 만들고 DB에 저장


- Fragment
	- 독립적인 수명주기를 갖고 있는 친구
	- 재사용성이 굉장히 높다
	- 항상 액티비티 위에서만 존재할 수 있다
	- 앵간하면 프레임레이아웃으로 만듬
	- 클래스에서 쉽게 뷰 연결하는법
		- class 이름: Fragment(R.layout.이름)
	- 코틀린에서 메인엑티비티에서 클래스 생성 쳐 하고 쓰셈 
	- 생명주기 관리를 잘해줘야함
	- onViewCreated안에서 평소처럼 쓰면 됨
	- 화면 전환 

```
		- supportFragmentManager.beginTransaction().apply{
			replace(R.id.프레임레이아웃이름, 프래그먼트 변수)
			commit()
		}
```

---

- 더 구현해보고 싶은 것
	- 모든 화면 UI 수정
	- 채팅방 꾸미기
	- 이 모든건 당근마켓 클론 코딩에서 할 예정

---

- Tip

	- 문자열을 날짜 형식으로 바꾸기
		- val format = SimpleDateFormat("MM월 dd일")
		- val date= Date(변수)
		- 변수.text = format.format(date).toString

	- 리얼 타임 DB쓸때는 데이터 클래스에 빈 생성자가 필요
		- 이렇게 하면 클래스 자체를 받아올 수 있음
		- constructor(): this(아무값 변수 할당)

---

- 동작 화면

-   ![KakaoTalk_20220720_204241495_02](https://user-images.githubusercontent.com/68932465/179974272-9242cfaa-ceda-40bf-be50-ef24e06dd3c4.jpg)
   ![KakaoTalk_20220720_204241495_03](https://user-images.githubusercontent.com/68932465/179974273-93eebcc3-1b01-4300-a14c-1f1dc250bc11.jpg)
   ![KakaoTalk_20220720_204241495_01](https://user-images.githubusercontent.com/68932465/179974267-a44d17b9-ce76-4f64-9c54-9c6d4ea44def.jpg)
 ![KakaoTalk_20220720_204241495](https://user-images.githubusercontent.com/68932465/179974259-056b417e-b242-46d4-a7f1-c1da6ad33e7c.jpg)
