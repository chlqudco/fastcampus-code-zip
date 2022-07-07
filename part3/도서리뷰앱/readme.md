- viewBinding
  - gradle 파일에 뷰바인딩 허용하기 
  - findViewById를 안해도 binding을 통해 접근 가능


- Retrofit
  - API를 쉽게 사용할 수 있도록 하는 라이브러리
  - retrofit 페이지에 사용법이 자세히 나와 있음
  - 1. Service 인터페이스 만들기
    - @GET(requesturl)
    - fun get어쩌구(@Query("요청 변수") key: String) : Call(Dto) <- 괄호 말고 꺽새인데 깃헙에 입력 안됨
  - 2. Dto data 클래스 만들기
    - 서버에서 내려오는 값을 변수에 저장하기 위한 데이터 클래스
    - 변수 이름 맘에 안들면 @SerializedName(변수) 써서 받아오기만 잘 하기
    - 원하는 항목만 받아올 수 있음, 꼭 다 안받아도 됨 
    - List 형식의 값이 있으면 해당 모델 만들기

  - 3. Model data 클래스 만들기
    - 2번에서 필요하면 만들기
    - 나머지 속성은 똑같
  
  - 4. 액티비티에서 Retrofit.Builder를 통해 빌더를 만들고 사용
  - 5. Service인터페이스와 4번에서 만든 빌더를 통해 api요청 하기
    - .enqueue와 콜백 메소드를 통해 body값에 접근 가능  

- Glide
  - url 이미지를 쉽게 등록? 하기 위한 라이브러리
  - 다른 활용 부분이 아주 많으니 홈페이지 가보기
  - Glide.with(context).load(url).into(view)

- 인터파크 Open API 이용
  - 현재는 지원이 중지됨
  - 요청 파라미터나 반환값에 무엇이 있는지 잘 확인해야함

- postman
  - API 요청의 결과값을 간단하게 테스트 해볼 수 있는 도구 

- 직렬화
  - 클래스를 Intent로 넘기려면 직렬화 해야 함
  - 1. gradle에 id 추가
  - 2. 클래스 위에 @Parcelize , 뒤에 : Parcelable 쓰면 직렬화 가능
  - 가져올땐 getParcelableExtra로 가져오기 

---

-인터파크 OPEN API
	-책 정보 읽어와!

-리사이클러 뷰
	-스크롤 뷰는 모든 컨텐츠? 들을 다 그리기 때문에 cost가 매우 높음
	-리사이클러뷰는 보이는 곳만 그림, 절약 굳
	-재료
		-그려질 뷰의 레이아웃
		-어댑터 클라스
	-리사이클러뷰에 레이아웃 매니저랑 어댑터 설정하면 끝
	-xml상에서 모양을 보고 싶으면 tools:listitem = "@layout/xml이름"

-Room DB
	-1. 의존성 2줄, plugin 추가하기
	-2. 추상 클래스 만들기 , 클래스 위에 @Database(entities = [클래스 이름::class], version = 1) 추가
		-클래스는 RoomDataase() 상속
	-3. 클래스 안에 Dao 상속받는 Dao함수 만들기
	-4. 데이터 클래스 만들고 위에 @Entity쓰기 
		-안에 변수들은 @PrimaryKey 나 @ColumnInfo(anme = "sadsd") 로 추가 
	-5. Dao 인터페이스 만드기, 위에 @Dao쓰기
		-원하는 쿼리의 함수 작성, 함수 위에 @Query("SELECT * FROM ㅁㄴㅇㅁㄴㅇ") 라던지, @Insert 같은거 추가
	-6. 메인에서 val DB = Room.databaseBulder(applicationContet, 디비클래스::class.java, "이름").build
	-7. DB작업은 쓰레드를 열고 해야됨 , Thread{db.Dao인터페이스().원하는함수}.start()


-Retrofit 라이브러리
	-API를 쉽게 사용하게 해줌
	-깃헙에 올라가있는 오픈소스 라이브라리
	-검색하면 사이트에 설명이 자세히 나옴
	-1. 의존성 추가하기
		-레트로핏 버젼이랑 컨버터-지슨
	-2. 인터페이스 만들기
		-@GET("/request주소 말고 그 뒷부분 주소")
		-fun 함수이름(
			@Query("key") apiKey: String, 이런 식으로 파라미터 넣기
		) : Call<데이터 클래스>
	-2.1 데이터 클래스 만들기
		-( 안에 내가 쓸 값 변수 선언
		 @SerializedName("서버에서 주는 이름") val 변수 : String)
	 
	-3. 메인액티비티 에서 레트로핏 불러오기
		-val retrofit = Retrofit.Builder().baseUrl("알아서;").addConverterFactory(GsonCo에이씨.create()).build()
		-val Service = retrofit.creat(인터페이스::class.java)
		-Service.함수로 알아서 잘 갖고오기, ㅈㄴ 복잡함

	-인터넷 권한 및 hppts인지 확인


-Glide 라이브러리
	-유알엘의 이미지 쉽게 적용
	-깃헙 페이지에 자세히 나타나있음
	-1. 의존성 추가
	-2. 바로 적용, Glide.with(컨텍스트).load(Url).into(이미지뷰)
	-http는 fail되므로 매니페스트에 useCleartextTraffic을 true로 주기



-OPEN API
	-남의 DB를 내가 쓸 수 있는 기능
	-요청 URL을 알아야함
	-필수 요청 변수를 알아야함
	-postman이란 크롬 확장프로그램으로 테스트 가능
	

-EditText 검색? 구현
	-edittext.setOnKeyListener {v, keyCode, event ->
		if(keyCode == KeyEvent.KeYcODE_ENTER && event.action == MotionEvent.ACTION_DOWN){
			할일 작성
			return@setOnKeyListener true
			}
		return@setOnKeyListent false
		}








