# ResponsiveGridTemplate
Grid를 이용한 반응형 구조를 만들어 보았습니다

### 구현 과정
- 기본 설정을 가로 너비 500px 이하일 때 1열로 설정하였고 미디어쿼리를 사용해 500px 이상일 때 2열, 850px 이상일 때 4열로 만들었습니다.
 	- 첫 번째 아이템이 두 칸을 차지하는 템플릿을 만들고 싶었는데 500px 이하일 때는 모두 한칸으로 나오는게 보기 좋으므로 해당 사항 없고 500px 이상일 때 부터 두 칸을 차지해 주기 위해 500px 이상일 때에 grid-column: 1/3; 값을 주었습니다.
- 한 카드 안에 아이템들을 정렬하기 위해 flex를 사용하였고 flex-direction: column;을 이용해 수직으로 정렬하였습니다.
- 이미지를 나오게 하기 위해 padding-bottom: 60%;를 사용하였고 background-size: cover;를 통해 꽉 차게 만들고 background-position: center center;를 통해 정 가운데가 나오게끔 만들었습니다.
- 카드 안에 있는 문자 부분에 다시 flex를 주고 수직 정렬 시킨 다음에 justify-content: space-between;으로 간격을 만들고 가운데 p 부분의 윗부분과 h1 부분의 사이를 일정하게 만들기 위해 p 태그에 따로 flex-grow: 1; 값을 주어 나머지 영역을 모두 사용하게 하여 h1 밑 부분과 p 윗 부분의 간격을 모든 카드 동일하게 만들었습니다.
- 선택되는 효과를 좀 더 내기 위해 hover 시 position의 top 값을 -2로 변경 시켰고 box-shadow를 통해 그림자를 주었습니다.
  - 여기서 실수!
   - position: relative;, top: -5px 를 .card:hover 값에 주고 .card 에 transition을 주고 왜 안되지 하는 실수를 했다.
   - transition 은 변하는 값에 애니메이션을 주는 속성이므로 .card에는 값을 주지 않고 .card:hover에만 값을 주니 먹힐 리가 없다. 변하기 전 값을 미리 설정해 주고 변하는 값을 설정하고 변하기 전 부분에 transition을 주어야한다!
