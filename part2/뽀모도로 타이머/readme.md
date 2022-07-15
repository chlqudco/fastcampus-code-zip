- 소개
	- 유명한 뽀모도로 타이머를 모방한 타이머 앱

- 기능
	- 설정한 시간에 따라 타이머가 실행됨


- 배우는 것

	- CountDownTimer
	- SoundPool
	- SeekBar

---

- CountDownTimer
	- 말그대로 카운트 다운을 하는데 유용한 컴포넌트이다
	- 인자로 총 재생시간, 기준시간?이 필요함
	- 기준시간 마다 onTick 함수가 호출됨
	- 총 재생시간이 끝나면 onFinish 함수가 호출됨


- SoundPool
	- 오디오를 재생하고 관리하는 클래스
	- 비교적 빠른 속도로 재생해준다
		- 크기가 큰 파일은 추천되지 않음
	- val soundPool = SoundPool.Builder().build()로 구현
		- 여러 속성값을 지정해 줄 수 있음
	- 원하는 음악을 가져오는 방법
		- val musicId = soundPool.load(context, R.raw.음악, 우선순위(1) )
	- 재생 방법
		- soundPool.play(id, 1F, 1F, 우선순위, 반복여부(-1 : 평생반복), 재생속도)
	- 생명주기 관리를 꼭 해줘야 한다.
		- 관리 안하면 mp3가 되어버림
		- autoResume과 autoPause를 이용하면 편리함

 
- SeekBar
	- 음.. 뭔가 클릭을 통한 값을 선택할 수 있는 컴포넌트?
	- max 값을 지정하면 범위를 내맘대로 커스텀 가능
	- Seekbar 리스너를 통해 3개의 콜백을 오버라이드 할 수 있다
	- onProgressChanged
		- 시크바 값이 변경되었을 때 호출
		- fromUser 인자를 통해 사용자가 변화시킨것인지 체크 해줘야 됨, 신기함	
	- onStopTrackingTouch
		- 시크바에서 손을 떼었을 때 발생할 이벤트 정의
	- thumb 속성을 통해 클릭하는 곳의 모양을 바꿀 수 있다
	- tickMark 속성으로 마크를 내가 원하는 drawable 파일로 지정 가능


- Vector Asset
	- 코드를 통해 그림을 그리는 것
	- 하나의 파일로 다중 밀도를 지원해줌
	- 복잡한 이미지는 그리지 못함? cpu를 많이 잡아 먹음

---

- 더 구현해보고 싶은 것

---

- Tip
	- 앱 시작할 때 흰색화면 다른 색갈로 지정하는 법
		- 액티비티에 백그라운드 지정하지 말고 테마 파일에서 windowBackground 에 원하는 컬러 넣기
	
	- 액션바 위에 있는 statusBar도 색깔 바꾸면 통일성 높아짐

---

- 동작 화면


- ![KakaoTalk_20220715_023043875](https://user-images.githubusercontent.com/68932465/179046367-47212e5a-0545-4a14-9052-dcbee7119845.jpg)

