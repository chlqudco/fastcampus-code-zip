1. BMI 계산기
   - LinearLayout
   - Intent
   - when 분기문
   - 람다 함수
   - Toast 메세지

2. 로또 번호 추첨기
   - ConstraintLayout
   - NumberPicker
   - Shape Drawable
   - apply , Set, List, Random

3. 비밀 다이어리
   - SharedPreference , android-ktx
     - getSharedPreferences(name,mode(ex : Context.MODE_PRIVATE))
     - 값 불러오기 : get자료형(key,디폴트값)
     - 값 저장하기 : preference.edit(true){ put자료형(key,value) }, true를 주면 commit=true 이므로 동작 완료 까지 멈춤, commit과 apply의 작동방식 차이 잘 알기 
   - Handler
     - 스레드 연결 도구 
     - val handler = Handler(Looper.getMainLooper())
     - handler.postDelayed(runnable, delay) 을 실행하면 러너블 객체를 delay이후에 실행함
     - handler.removeCallbacks(runnable) 을 실행하면 등록된 콜백 삭제
   - Theme
     - NoActionBar 적용 및 Manifest에 등록
   - AlertDialog
     - AlertDialog.Builder(context).setTitle(title).setMessage(msg).setPositive(Negative)Button(text) {dialog, which -> event }.create().show()
   - 커스텀 폰트 적용
     - .ttf 파일을 res/font폴더에 넣고 fontFamily=@font/이름 적용
   
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
   - Permission
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


