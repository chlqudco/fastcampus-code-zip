- Motion 레이아웃
  - 컨스트레이아웃의 서브 클래스
  - 레이아웃 전환 ? 애니메이션을 쉽게 
  - 열고 닫는 시점의 Constraint Set으로 애니메이션 효과
  - 최상위 constraint 레이아웃을 모션 레이아웃 으로 바꾸면 xml폴더와 xml파일이 하나 생기
  - 원하는 state에서 원하는 id선택 후 연필 모양 눌러서 create Constraint 지정
  - 뷰를 내리거나 올리고 싶으면 tranlation좌표 값 넣기
  - 드래그 이벤트를 걸기 위해서는 swipe Handler등록
  - 서로 다른 xml의 모션?을 연동하기 위해서는 fragment kt 파일에서 작업
    - 모션레이아웃에 setTransition리스너 등록
    - 4개 오버라이드한 메소드중 change에서 상대방 모션레이아웃 가져와서 값 주기(모션레이아웃.progress)
    - 프래그먼트는 자기가 붙어있는 액티비티만 가져올 수 있음
  - 터치 이벤트 흘리기
    - 모션 레이아웃을 커스텀해서 영역을 지정해줘야 함 
  - 애니메이션 변하는 정도? 를 조절하려면  
    - 타이머 버튼 눌러서 Add속성 추가해서 원하는 값 바꾸기
    - 속성이 아주 많으니 강의나 Document 살펴보기
 
- Exoplayer
  - 구글이 만든 오픈소스 라이브러리
  - 오디오 및 동영상 재생 가능 및 여러 강력한 기능들 포함
  - 실제 유튜브에서 사용하는 라이브러리
  - 빌더를 만들고 play할 수 있음
    - 데이터소스팩토리, 미디어소스 등 준비과정이 필요함
  - 생명주기를 잘 관리해줘야 함 
  - 리스너를 달 수 있음
    - Event리스너를 통해 여러 메소드 구현 가능 

- Fragment
  - 얘도 앞에서 배움
  - 프래그먼트로 보여줄 xml파일 만들고 kt 파일(Fragment(R.layout.프래그먼트))도 만들기
  - 프래그먼트 담고있는 부모액티비티에서 supportFragmentManager.beginTransaction.replace(R.id.프래그먼트, 프래그먼트kt파일).commit
  - 액티비티의 onCreateView처럼 활동하는 onViewCreated함수 오버라이드 하기

- BottomNavigationView
  - 앞에서 배웠으니 간단하게
  - menu 디렉토리 만들고 menu xml파일 만들기, <item 태그에 id와 icon, title지정
  - 바텀내비의 menu 속성에 xml파일 지정
 

















