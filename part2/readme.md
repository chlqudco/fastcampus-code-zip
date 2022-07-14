
4. 계산기
   - TableLayout
     - 격자 형태로 뷰를 배치할 수 있는 레이아웃
     - TableRow
   - drawable
     - ripple 태그
   - LayoutInflater
     - 레이아웃을 동적으로 생성해서 붙이는 느낌
     - 내가 아는건 리사이클러뷰 인데 리사이클러 뷰를 안쓰고도 비슷한 구현  
     - LayoutInflater.from(context).inflate(xml파일, null, false) 으로 생성 후 view 에 addView 하면 끝
   - Room DB 
     - @Entity와 @PrimaryKey 등의 어노테이션으로 간단히 테이블 구현
     - @Dao 와 @Query등을 통해 테이블 접근 
     - @Database를 통해 진짜 DB 클래스 생성
   - Thread
   - data class
     - Model 클래스에 자주 쓰는 클래스 형태
   - SpannableStringBuilder
     - 문자열 중간의 특성을 바꿀 수 있음 
   - 확장 함수
     - 기존 클래스에 메소드를 추가
     - ex) fun String.isNumber(): Boolean{} 

5. 전자 액자
   - Runtime Permission
     - 민감한? 정보나 기능을 다룰 때는 사용자의 권한을 받아와야 함 
     - 거절한 유저를 위해 교육용 뷰를 보여줘야 함
     - ContextCompat.checkSelfPermission(context, 권한)==PackageManager.PERMISSION_GRANTED으로 권한 있는지 체크
     - shouldShowRequestPermissionRational 함수로 교육용 팝업 띄워야 하는지 확인
     - 실제 권한 요청 : requestPermissions(권한 배열, 요청코드)
     - onRequestPermissionResult 함수를 오버라이드 하여 결과 처리
   - View Animation
     - 뷰.animate().속성().setDuration(초).start()
   - Content Provider
     - 이 앱에선 SAF를 이용 
     - intent.ACTIOC_GET_CONTENT 
   - LifeCycle 
     - 액티비티의 생명주기를 잘 알고 있어야 함
   - Timer
     - 일정 시간 마다 람다식 안의 내용 실행   


6. 뽀모도로 타이머
   - CountDownTimer
     - 말그대로 타이머, 초기값과 2개 메소드 오버라이드 해야함 
   - SoundPool
     - 오디오파일 재생 및 관리 클래스
     - 짧은 파일에 적합
   - SeekBar
     - 손잡이로 조절하는 바 ?
     - setOnSeekBarChangeListener로 리스너를 달 수 있고, 3개의 메소드 오버라이드 해야함

7. 녹음기
   - MediaRecorder
      - state diagram에 따라 잘 작업?해줘야 함
      - format 과 encoder 설정은 안드로이드 doc에 자세히 나와있음
      - MediaRecorder 선언 후 녹음을 시작할 때마다 초기화 해줘야 함
      - 녹음 특성상 외부저장소에 저장하는 것이 유리함
      - 이번 프로젝트에서는 externalCacheDirectory에 임시 저장
      
   - MediaPlayer
      - 녹음한걸 재생하려면 플레이어를 써야함  
      - 마찬가지로 적절한 state관리를 해줘야 함 
      
   - CustomView
      - 이미지버튼을 클래스로 만들기 위해 AppCompatImageButton상속 받아야 함
      - context와 attributeset을 인자로 받아야 함

   - getter setter
      - 사실 setter만 배움, 변수 아래 set(value) { } 를 하면 괄호 안의 내용이 실행
      - field = value 를 통해 값 이식하는거 잊지 말길

8. 심플 웹 브라우저

   - Web View
      - 인터넷 권한 필수
      - http 쓰려면 보안 문제 때문에 usesCleartextTraffic true로 줘야 함
      - webview.webViewClient = WebViewClient() 줘야 외부 웹브라우저로 이동 안함 
      - webview.settings.자바스크립트허용 = true로 줘야 js도 됨
      - 주소창으로 쓰는 edittext의 imeOptions값을 적절히 주면 다양한 동작 가능
        - actionDone을 주면 키보드가 내려감
        - kt에서 edittext의 OnEditor액션리스너를 통해 actionDone인지 확인하면 바로 웹페이지 로딩 가능
        - 키보드 처리등을 위해 false를 반환해줘야 함
      - 


   - Content Loading Progress bar
     - 사용자한테 시각적으로 Feedback을 주는것은 매우 중요함, 가만히 있으면 안좋음 
     - 끝나는 시점을 알고 있으므로 style에 Progressbar.Horizontal 지정, 자세한건 Determined progressbar 검색
     - Web크롬클라이언트의 onProgressChanged 함수를 통해 progress 값 관리 가능
     - Web뷰클라이언트의 메소드 오버라이드를 토애 보여주고 사라지기 구현
     
     
   - Swiperefreshlayout
     - 당겨서 새로고침
     - 의존성 추가 해줘야 함 
     - kt에 연결해서 이벤트 핸들링을 해주기, setonRefresh리스너 등록
     - 로딩창? 을 없애려면 isrefreshing에 flase를 주기

