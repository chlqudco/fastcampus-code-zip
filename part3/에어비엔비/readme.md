- Naver Map API
  - 네이버 지도를 이용하기 위한 API
  - 이용신청 후 의존성 추가
  - xml 에서 MapView를 직접 쓰거나 Fragment를 이용할 수 있음
    - Fragment 사용시 생명주기 관리가 알아서 됨
    - MapView를 직접 쓰면 커스텀이 좋지만 수명주기를 직접 관리해야 함
  - API 키를 xml에 저장 후 manifest에 meta-data로 등록 
  - onMapReady를 통해 map을 다룰수 있음
    - 그 전에 getMapAsync 해줘야함 
  - maxZoom 과 minZoom을 통해 확대 축소정도 조절 가능
  - moveCamera 메소드를 통해 보이는 위치를 옮길 수 있음
    - CameraUpdate 객체를 생성하여 위경도 값을 넣어주고 넘겨주기  
  - 현위치 버튼 기능은 간단히 파라미터 값 지정으로 가능
    - isLocationButtonEnabled 값과 퍼미션 지정
    - 퍼미션은 외부 의존성 추가하는 방법도 있음
  - 마커를 찍기 위해 Marker 객체를 생성하고 원하는 파라미터를 지정해주기

- ViewPager2



- Coordinator Layout
  - Frame 레이아웃의 진화버젼



- Bottom Sheet Behavior 
