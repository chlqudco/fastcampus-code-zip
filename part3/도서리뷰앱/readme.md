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
