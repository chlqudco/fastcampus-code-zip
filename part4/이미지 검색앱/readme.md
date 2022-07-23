- 소개
	- API를 통해 원하는 이미지를 검색하고 무료로 다운로드 할 수 있는 앱입니다.

- 기능
	- 원하는 이미지 검색
	- 이미지 다운로드
	- 이미지 배경화면으로 지정

- 배우는 것
	- Unsplash API(무료 이미지 API)
	- ShimmerLayout
	- WallpaperManager
	- 사진 다운로드

---

- Unsplash API(무료 이미지 API)
	- 회원가입 하고 api 사용신청하기
	- 가이드라인을 잘 준수해야함
	- 하면 안되는거 다 하는 앱이라 배포는 하지 말기
	- 이런 비동기 작업은 코루틴으로 하는거 잊지 말기

- ShimmerLayout
	- Loading Shimmer
	- 페이스북이 만든 로딩창 멋있게 보여주는 방법!
	- 어떻게 보여질지 에 대한 item xml을 작성해야 함. 걍 다 뷰로 작성하면 됨
		- 왠만하면 회색이 좋은가?
	- 뭐야 왜 2개만 넣지? 눈 속임인가 그냥

- WallpaperManager
	- 배경화면으로 지정하기 위해 도와주는 애
	- SET_WaLLPAPer 권한을 써놓으면 됨
	- setBitmap 함수로 지정하면 끝

- 사진 다운로드
	- shared store에 저장하기 위해 mediaStore api를 사용해야 함
	- 28 이하 버젼 이전에는 권한을 받아야함
	- 결국 글라이드를 쓰는구만
	- 글라이드로 다운받고 파일 이름 지정
	- CollectionUri를 지정?해야 함
	- 나머지 저장하기 위한 정보들을 지정
	- 이게 이렇게까지 복잡할 이유가 있나??

---

- 더 구현해보고 싶은 것

---

- Tip
	- 코루틴 다루는 법이 강사마다 다달라서 헷갈린다.
	- 사진은 썸네일 이미지를 미리 보여주면 UX가 증가
	- layoutParams 속성을 뭐 여차여차 해서 미리 공간을 할당받기?
	- 로딩 할 때 placeHolder를 지정할 수 있다. 이것도 마찬가지로 UX증가
	- EditText 앞에 drawable 넣고 싶으면 drawableStart에 지정, drawablePadding도 지정하면 좋음
	- TextView에 shadow 속성을 이용하면 글자가 더 잘 보일 가능성이 있다
	- Edittext 키보드 없애는 기능을 매우 이상하게 구현함. inputMethodManager?
	- 알림 언제 끝날지 모를땐 snackbar의 Length.Indefinite 속성 사용
	- 스낵바에 setAction을 하면 버튼 처럼 클릭 가능
---

- 동작 화면

- ![KakaoTalk_20220721_175447331_22](https://user-images.githubusercontent.com/68932465/180491207-f5bc10bf-1ed8-44ac-9611-5f1099f36b93.jpg)
  ![KakaoTalk_20220721_175447331_21](https://user-images.githubusercontent.com/68932465/180491214-3b66d901-8481-4a43-b874-88a34d7bc267.jpg)
  ![KakaoTalk_20220721_175447331_20](https://user-images.githubusercontent.com/68932465/180491217-451e1f7c-9dd5-47cf-b062-757e792ce8aa.jpg)
  ![KakaoTalk_20220721_175447331_18](https://user-images.githubusercontent.com/68932465/180491220-2e3fb045-f415-4b41-a386-714a7dd0f58f.jpg)
