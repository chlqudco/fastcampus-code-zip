- 소개
	- 본인이 설정한 비밀번호를 통해 본인만의 다이어리를 만들어주는 앱

- 기능
	- NumberPicker를 이용한 비밀번호 검증
	- 비밀번호 변경
	- 다이어리 작성

- 배우는 것
	- SharedPreference
	- Custom Font 사용
	- Handler
	- Theme
	- AlertDialog

---

- SharedPreference
	- Preference라는 xml 파일을 다른 앱과 공유할 수 있다
	- 여기선 로컬DB 같은 느낌으로 사용
	- 사용자의 비밀번호를 기기에 저장해서 앱이 종료후에도 유지하도록 함
	- getSharedPreferences(name,mode(ex : Context.MODE_PRIVATE))
		- name은 파일의 이름
		- mode는 공유 여부
	- 값 불러오기 : get자료형(key,디폴트값)
	- 값 저장하기 : preference.edit(true){ put자료형(key,value) }, true를 주면 commit=true 이므로 동작 완료 까지 UI 가멈춤
	- commit과 apply의 작동방식 차이 잘 이해하기 

- Thread
	- 코틀린이면 코루틴을 써야지! 그러나 그 배경에는 쓰레드가 있다
	- 개념 정리는 summary 레포에 있으니 간단하게 작성
	- 백그라운드 작업을 하기 위해 쓰레드를 사용한다. UI가 멈추면 안되므로
	- Runnable 객체를 사용해 구현한다

- Handler
	- 쓰레드를 관리 해주는? 연결 해주는? 도구 
	- val handler = Handler(Looper.getMainLooper())
		- 메인쓰레드에 연결되는 핸들러 선언
	- handler.postDelayed(runnable, delay) 을 실행하면 러너블 객체를 delay이후에 실행함
	- handler.removeCallbacks(runnable) 을 실행하면 아직 실행되지 않고 등록되어 있는 러너블 삭제
	- 왜 쓰레드로 감싸지 않는지 개념이 부족해서 잘 모르겠다

- Theme
	- NoActionBar를 쓰면 화면 위의 보라색 거슬리는 액션바가 사라짐
	- 액티비티마다 내가 원하는 테마를 지정할 수도 있음


- AlertDialog
	- 화면에 메세지?를 보여줄 수 있는 여러 도구 중 하나
	- 약간 경고창에 잘 어울림
	- 성공 실패 버튼을 붙일 수 있다는 장점이 있다
	- AlertDialog.Builder(context).setTitle(title).setMessage(msg).setPositive(Negative)Button(text) {dialog, which -> event }.create().show()


- 커스텀 폰트 적용
	- .ttf 파일을 res/font폴더에 넣고 fontFamily=@font/이름 적용
	- font폴더는 만들면 됩니다
---

- 더 구현해 볼 것
	- 여러 노트를 쓸 수 있도록 해주기
	- 실제 노트처럼 줄 쳐져 있도록 하기

---

- Tip
	- NumberPicker는 lazy로 초기화 하면서 apply를 통해 min, max 값을 지정해주면 편하다
	- editText에는 text가 변경될 때마다 불리는 리스너가 있다.
		- 너무 빈번하게 불릴 가능성이 크니 쓰레드를 사용하자

---
- 실행 화면
- ![KakaoTalk_20220714_222844520_01](https://user-images.githubusercontent.com/68932465/179001208-584732ea-69f0-4f8f-98bf-0ca2232a40da.jpg)
   ![KakaoTalk_20220714_222844520](https://user-images.githubusercontent.com/68932465/179001213-ff0579f5-3893-4eb4-a5a4-2f74b1a6c834.jpg)

