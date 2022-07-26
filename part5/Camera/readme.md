- 소개
	- 말 그대로 카메라 앱입니다! 디자인 패턴을 사용하지 않습니다

- 기능
	- 사진 찍기
	- 화면 줌 인-아웃
	- 플래시 켜기
	- 찍은 사진 확인하기

- 배우는 것
	- CameraX
	- Camera Flash
	- Zoom In & Out

---

- CameraX
	- Jetpack에 속하는 Camera2 기반의 라이브러리
	- 하드웨어적? 보일러플레이트 코드를 줄임
	- 얘도 그냥 docs가서 봐
	- 그래들에 의존성을 넣어야 함
	- Application 클래스에서 CameraXConfig.Provier를 상속해야 함
		- getCameraXConfig 함수를 오버라이드 해서 카메라2config를 반환
	- 미리보기 화면을 위해 PreviewView를 사용할 수 있다
	- 당연히 카메라 권한을 요청 해야 함
	- 카메라프로바이더와 디스플레이매니저, 디스플레이ID, 카메라Executor 를 변수로 저장해 놓기
		- 디스플레이 매니저는 회전값 받아오는 역할
		- 리스너를 등록해서 감지 가능
	- 함수를 하나 만들어서 다양한 속성을 넣어보자


- Camera Flash
	- 간단하게 구현할 수 있음
	- 권한을 추가해야 함. 퍼미션은 안받아도 됨
	- enableTorch에 불리언값만 주면 됨


- Zoom In & Out
	- 제스터 디텍터를 이용해 구현함
	- Arctic Fox 책에서 본거랑 똑같음
	- zoomRatio 값을 가져와서 scaleFactor 값을 곱한 다음 적용함


---

- 사진 저장 기능
	- 옵션을 지정한 후 takePicture 함수 내에 이미지세이브콜백을 구현 해야 함

---

- 더 구현해보고 싶은 것

---

- Tip


---

- 동작 화면

- ![KakaoTalk_20220721_175447331_04](https://user-images.githubusercontent.com/68932465/180816710-ce0ce386-55aa-4f1d-83d7-041c457eb7be.jpg)
  ![KakaoTalk_20220721_175447331_03](https://user-images.githubusercontent.com/68932465/180816713-7dc8310a-7db2-4358-8afc-391a53bdb557.jpg)
