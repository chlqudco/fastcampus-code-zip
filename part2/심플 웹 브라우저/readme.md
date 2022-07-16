- 소개
	- 웹뷰를 이용한 간단한 인터넷 브라우저 앱입니다
	
- 기능
	- 인터넷 브라우저 기능
	- 뒤로가기, 앞으로 가기, 홈으로 가기

- 배우는 것

	- Web View
	- Content Loading Progress bar
	- Swiperefreshlayout

---

- Web View
	- 인터넷 권한 필수
	- http 쓰려면 보안 문제 때문에 usesCleartextTraffic true로 줘야 함
	- webview.webViewClient = WebViewClient() 줘야 외부 웹브라우저로 이동 안함 
	- webview.settings.자바스크립트허용 = true로 줘야 js도 됨
	- 주소창으로 쓰는 edittext의 imeOptions값을 적절히 주면 다양한 동작 가능
		- actionDone을 주면 키보드가 내려감
		- kt에서 edittext의 OnEditor액션리스너를 통해 actionDone인지 확인하면 바로 웹페이지 로딩 가능
		- 키보드 처리등을 위해 false를 반환해줘야 함
	- 뒤로 가기 : goBack
		- onBackPress와 연동하면 높은 UX를 얻을 수 있다
		- canGoBack으로 뒤로 갈 수 있는지 확인
	- 앞으로 가기 : goForward
	- webViewClient와 webChromeClient의 차이를 잘 알자
	- onPageFibished 함수에는 진짜 주소가 인자로 전달됨
	- 자동으로 http 추가해 주는 기능 만들기
		- URLUTil.isNetworkUrl 로 있는지 확인 후, 없으면 추가해서 load하기

- Content Loading Progress bar
	- 사용자한테 시각적으로 Feedback을 주는것은 매우 중요함, 가만히 있으면 안좋음 
	- 끝나는 시점을 알고 있으므로 style에 Progressbar.Horizontal 지정, 자세한건 Determined progressbar 검색
	- Web크롬클라이언트의 onProgressChanged 함수를 통해 progress 값 관리 가능
	- Web뷰클라이언트의 메소드 오버라이드를 통해 보여주고 사라지기 구현


- Swiperefreshlayout
	- 당겨서 새로고침할 수 있게 해줌
	- 의존성 추가 해줘야 함 
	- kt에 연결해서 이벤트 핸들링을 해주기, setonRefresh리스너 등록
	- 로딩창? 을 없애려면 isrefreshing에 flase를 주기
		- webView랑 연동하기 위해 따로 클래스를 만들기 까지 함
		- webView의 onPageFinished 함수를 오버라이드 하기 위해

---

- 더 구현해보고 싶은 것


---

- Tip

	- 액션바 사이즈로 레이아웃 크기 지정
		- height = ?attr/actionBarSize
	
	- 버튼의 background 속성으로 ?attr.selectableItemBackground 속성을 주면 리플 이펙트란게 생김
		- 근데 왜 배경이 투명해지는겨?
	
	- EditText의 전체 선택 자동으로 해주는 속성
		- selectAllOnFocus에 true 주기
	
	- statusBar windowLightStatusBar 속성 지정하면 검정?컴포넌트로 보임

---

- 동작 화면

- ![KakaoTalk_20220715_023043875_02](https://user-images.githubusercontent.com/68932465/179046374-8768ab5b-f1fb-4794-8e81-2b68daf7ad0e.jpg)
