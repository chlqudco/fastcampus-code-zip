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
   - Room DB 
   - Thread
   - data class
   - SpannableStringBuilder
     - 문자열 중간의 특성을 바꿀 수 있음 
