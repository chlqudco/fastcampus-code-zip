- 소개
	- 전엔 인터파크 API를 이용했지만 서비스 중단 이후로 네이버 API로 바꿈
	- 검색 키워드를 통해 도서 목록을 검색하고, 간단한 후기를 남길 수 있는 앱
 
- 기능
	- 도서 검색 기능
	- 후기 작성 기능

- 배우는 것
	- viewBinding
	- Retrofit
	- Glide
	- Open API 이용
	- postman
	- 직렬화
	- Recycler View

---

- viewBinding
	- gradle 파일에 뷰바인딩 허용하기 
	- findViewById를 안해도 binding을 통해 접근 가능


- Retrofit
	- API 및 네트워크 작업을 쉽게 사용할 수 있도록 하는 라이브러리
	- retrofit 페이지에 사용법이 자세히 나와 있음
	- 깃헙에 올라가있는 오픈소스 라이브라리
	- 1. 의존성 추가하기
		- 레트로핏 버젼이랑 컨버터-지슨
	- 2. Service 인터페이스 만들기
		- @GET("/request주소 말고 그 뒷부분 주소")
		- fun 함수이름(@Query("key") apiKey: String, 이런 식으로 파라미터 넣기) : Call<데이터 클래스>

	- 3. 모델 데이터 클래스 만들기
		- @SerializedName("서버에서 주는 이름") val 변수 : String)

	- 4. Dto 클래스도 만들기
		- 실제 반환에 대한 정보 받기
	 
	- 5. 메인액티비티 에서 레트로핏 불러오기
		- val retrofit = Retrofit.Builder().baseUrl("알아서;").addConverterFactory(GsonCo에이씨.create()).build()
		- val Service = retrofit.creat(인터페이스::class.java)
		- Service.함수로 알아서 잘 갖고오기
		- 당연히 싱글톤으로 할거면 이렇게 안하지

	- 인터넷 권한 및 https인지 확인


- Glide
	- url 이미지를 쉽게 등록? 하기 위한 라이브러리
	- 다른 활용 부분이 아주 많으니 홈페이지 가보기
	- Glide.with(context).load(url).into(view)
	- 유알엘의 이미지 쉽게 적용
	- 깃헙 페이지에 자세히 나타나있음
	- 1. 의존성 추가
	- 2. 바로 적용, Glide.with(컨텍스트).load(Url).into(이미지뷰)
	- http는 fail되므로 매니페스트에 useCleartextTraffic을 true로 주기


- Naver Open API 이용
	- 인터파크가.. 종료됨..ㅠㅠ
	- 기능이 많이 약하긴 한데 검색은 제공 하니 걍 씀


- Open API
	- 남의 DB를 내가 쓸 수 있는 기능
	- 요청 URL을 알아야함
	- 필수 요청 변수를 알아야함
	- postman이란 프로그램으로 테스트 가능
	- 보통 xml이나 json으로 결과값을 반환해줌
	- 파라미터 값을 잘 알아서 적절한 결과값을 받자

- postman
	- API 요청의 결과값을 간단하게 테스트 해볼 수 있는 도구


- 직렬화
	- 클래스를 Intent로 넘기려면 직렬화 해야 함
	- 1. gradle에 id 추가, kotlin-parcelize
	- 2. 클래스 위에 @Parcelize , 뒤에 : Parcelable 쓰면 직렬화 가능
	- 가져올땐 getParcelableExtra로 가져오기 


- Recycler View
	- 스크롤 뷰는 모든 뷰들을 다 그리기 때문에 cost가 매우 높음
	- 리사이클러뷰는 보이는 곳만 그림, 절약 굳
		- 또한 뷰홀더를 재사용함
	- 재료
		- 그려질 뷰의 레이아웃
		- 어댑터 클라스
	- 리사이클러뷰에 레이아웃 매니저랑 어댑터 설정하면 끝
	- xml상에서 모양을 보고 싶으면 tools:listitem = "@layout/xml이름"
	- onCreateViewHolder
		- 미리 만들어놓은 뷰홀더가 없으면 만들기
	- onBindViewHolder
		- 뷰홀더 안에 데이터 넣기
	- diffUtil과 같이쓰면 좋다
		- 들어있는 컨텐츠가 같은지, 아이템이 똑같은 아이템인지 비교해줌
	- 뷰홀더에 리스너를 달기 위해 어댑터 클래스의 생성자에 고차함수를 인자로 넣는다
		- 어댑터에서 못하는 작업이 있기 때문

---

- 더 구현해보고 싶은 것
	- 디자인 고치기
	- 태그 나오는것들 없애기
	- 검색어 클릭하면 바로 검색되는 기능

---

- Tip

	-EditText 검색? 구현

```
	edittext.setOnKeyListener {v, keyCode, event ->
		if(keyCode == KeyEvent.KEYCODE_ENTER && event.action == MotionEvent.ACTION_DOWN){
			//할일 작성
			return@setOnKeyListener true
		}
		return@setOnKeyListent false
	}
```

	- api key같이 전역적으로 쓰이는 것은 따로 xml 파일로 빼놓아라

	- Room DB는 버젼 컨트롤을 세심하게 해야 한다
		- 필요하다면 버젼을 옮기는 migration 코드를 넣어줘야 한다
		- 그냥 CREATE TABLE 하는 코드임
---

- 동작 화면

- ![KakaoTalk_20220717_231140182_01](https://user-images.githubusercontent.com/68932465/179402462-49aeee8f-f043-42c5-8b36-bba43dc8c923.jpg)
  ![KakaoTalk_20220717_231140182](https://user-images.githubusercontent.com/68932465/179402465-646d04db-a6d8-4487-9cc5-c8e4d7c46b3e.jpg)


