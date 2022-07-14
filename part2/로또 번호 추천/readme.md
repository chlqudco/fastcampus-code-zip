- 소개
	- 로또 번호 무료 추천기이다. 사용자가 좋아하는 숫자를 넣을 수 있다

- 기능
	- 내가 원하는 번호 추가하기
	- 로또 번호 6개 랜덤으로 불러오기
	- 초기화

- 배우는 것
	- ConstraintLayout
	- NumberPicker
	- Shape Drawable
	- Random
	- Collection
---

- ConstraintLayout
	- 제약을 이용해 컴포넌트를 배치하는 레이아웃
	- 서로의 뷰에 제약을 줌으로써 배치된다
	- Android-summary에 상세 정리
	- 공식문서를 보면서 다양한 속성을 익히자
	- 서로 연결하면 체인이 생김

- NumberPicker
	- 숫자를 고를 수 있도록 하는 컴포넌트

- Random
	- 코틀린 문법에서 랜덤으로 숫자를 고르는 방법 제공
	- seed 인자를 받음
		- 진짜로 무작위로 뽑는게 아닌 seed 를 기준으로 알고리즘을 돌림
		- seed 가 같으면 항상 같은 숫자만 나옴
		- 따라서 진짜 랜덤값을 위해 시간값을 줌
	- val random = Random(시간) 으로 객체 생성
	- 값을 뽑을 때는 random.nextInt() 사용
	- nextInt 안에 값을 넣으면 0부터 해당 범위 -1 까지만 뽑음

- Shape Drawable
	- xml로 정의한 그림? 모양? 객체를 만듬
	- bitmap을 이용하면 이미지 파일을 여러개 들고 있어야 함
	- xml로 되어있기 때문에 수정이 쉽고 용량이 매우 작음
	- 최상위 태그는 shape로 지정 후 shape 속성으로 원하는 모양 지정
	- solid 속성으로 색칠 가능
	- size 속성으로 크기 지정 가능
	- 코드에서 불러오기
		- ContextCompat.getDrawable(this,R.drawable.이름)

- 코틀린의 Collection
	- 자료구조!
	- List, Set, Map이 있다
	- mutable이 붙은 것은 수정이 가능한 객체
	- 안붙은 애는 immutable 이라 수정이 불가능하다
	- List
		- 잘 알고 있는 배열임
		- 인덱스를 이용한 접근
	- Set
		- 중복된 원소가 존재할 수 없는 자료구조
	- Map
		- 키과 밸류 쌍으로 값을 담는 자료구조
	- 강력한 내장함수들이 많이 있다.
		- 너무 많으니 공식문서를 확인하도록
---

- 더 구현해보고 싶은 것
	- API를 이용한 지난 로또 결과 보여주기
	- 현재 번호가 1등에 당첨된적이 있는지 보여주기
	- 넘버피커가 돌아갈 때 소리 나오기
	- 내 번호 기능 추가하기

---
- 실행 화면
- ![KakaoTalk_20220714_221613134](https://user-images.githubusercontent.com/68932465/178991329-b696bc8b-15d6-4118-b48b-a40c1ff42374.jpg)
