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
