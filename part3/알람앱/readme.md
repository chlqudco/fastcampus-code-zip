- 소개
	- 말그대로 알람 앱입니다. 다양한 기능은 없습니다

- 기능
	- 매일 설정한 시간에 알람이 울리게 하는 기능

- 배우는 것
	- AlarmManager
	- Broadcast receiver
	- Background 작업
	- TimePicker

---

- AlarmManager
	- 알람(따르릉 알람만 말하는게 아님)을 등록하도록 도와주는 도구
	- 실제 시간, 부팅 시간 기준등 여러 사용법이 있음 
	- set, inExactRepeating 등.. 여러 기준이 있다
	- RTC_WAKEUP은 절대 시간 기준
	- REALTIME_WAKEUP은 부팅 시간 기준


- Broadcast receiver
	- 직역하면 방송 수신기..?
	- 폰이 켜졌는지, 인터넷 연결됐는지, 배터리 부족한지 등등 시스템에서 일어나는 작업을 캐치해서 작업할 수 있도록 해줌
	- 무한반복으로 물어보면 자원 낭비, 안드로이드에서 알아서 broadcast 해줌
	- 뿐만 아니라 다른 앱에 전송도 가능
	- 상속받는 클래스는 onReceive 메소드를 필수 오버라이드 해야함
		- pendingIntent가 수신될때 실행되는 메소드   

- Background 작업
	- Thread, Handler, 코루틴은 즉시 실행해야 함
		- 앱 사용 중에 백그라운드 쓰레드에서 해야 하는 작업
	- WorkManager는 Deferred(지연된) 작업
		- 예약된 작업을 실행하는 것. 종료되어도 실행?
	- AlarmManager는 정시에 실행해야 하는 작업 
		- 반복된 시간, 지정된 시간에 작업이 일어나도록 pendingIntent를 사용

- pendingIntent
	- 인텐트를 즉시 실행하는 것이 아닌 보류해 두었다가 실행하는 인텐트
	- 알람이 등록되어 있는지 확인하기 위해 등록되어 있는 펜딩인덴트가 있는지 확인
		- pendingIntent == null 이면 등록되어 있지 않은 상황
	- 취소하는법 - pendingIntent.cancle()

- TimePicker
	- 시간을 선택 할 수 있도록 Custom된 Dialog
	- TimePickerDialog(context, 리스너, 초기화 시간, 초기화 분, 24시간 형식 쓸건지  )
	- 현재 시간 가져오려면 Calendar클래스 사용

---

- 더 구현해보고 싶은 것
	- 진짜 알람 앱 처럼 여러 알람 등록 가능하게 하기

---

- Tip
	- 무조건 2자리 숫자로 나타내기 = "%02d".format(조건문)
	- 현재 시간 가져오기 = Calendar.getInstance().get(Calendar.HOUR_OF_DAY) 등등
	- 클래스를 간단하게 sharedpreference에 간단하게 String으로 저장하면 편함
	- View의 tag 속성에는 아무거나 저장할 수 있다

---

- 동작 화면

- ![KakaoTalk_20220717_023150899_01](https://user-images.githubusercontent.com/68932465/179381739-781be749-152d-43ee-bb99-423caeee2336.jpg)
![KakaoTalk_20220717_023150899](https://user-images.githubusercontent.com/68932465/179381741-7cf7f772-3a17-41ed-ad2f-bceb89fb87d5.jpg)
