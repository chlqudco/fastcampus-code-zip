- 소개
	- 기본적인 녹음기 입니다. 사용자의 음성 크기를 GUI 적으로 보여줍니다

- 기능
	- 목소리 녹음 기능
	- 녹음 한 음성 재생 기능

- 배우는 것
	- MediaRecorder
	- MediaPlayer
	- CustomView

---


- MediaRecorder
	- 내부적인 state diagram에 따라 잘 작업?해줘야 함
	- format 과 encoder 설정은 안드로이드 doc에 자세히 나와있음
	- MediaRecorder 선언 후 녹음을 시작할 때마다 초기화 해줘야 함
	- 녹음 특성상 외부저장소에 저장하는 것이 유리함
	- 이번 프로젝트에서는 externalCacheDirectory에 임시 저장
	- 사용하지 않을 때는 메모리에서 해제하는 습관을 항상 들여야 한다

- MediaPlayer
	- 녹음한걸 재생하려면 플레이어를 써야함  
	- 마찬가지로 적절한 state관리를 해줘야 함 


- CustomView
	- 이미지버튼을 클래스로 만들기 위해 AppCompatImageButton상속 받아야 함
	- context와 attributeset을 인자로 받아야 함

- enum class
	- 상수 값처럼 값을 저장하는 클래스?
	- 설명이 없어서 코틀린 summary에 정리
	- 이 프로젝트에서는 상태값 처리를 위해 enum을 사용함
	- enum 값에 따라 하는 일? 처리하는 로직을 다르게 함 

---

- 더 구현해보고 싶은 것
	- 녹음 파일 저장 및 열람 기능
	- 잡음 제거 방식 조사
	- 음성 변조 기능
	- 자동 text 변환 AI 결합

---

- Tip
	- 이미지 버튼 안의 벡터에셋이 너무 작다 싶으면 scaleType 과  padding 속성으로 조절가능
	
---

- 동작 화면 

- ![KakaoTalk_20220715_023043875_01](https://user-images.githubusercontent.com/68932465/179046369-7a171955-ddcf-491d-aa81-350196517cab.jpg)
