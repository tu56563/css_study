# CSS (Cascading Style Sheet)
## CSS 작성 전 준비사항
* html 문서 준비(태그 작성 완료 상태)
* html, css 파일 별도 폴더 관리
* 최상위 폴더 html 파일 배치
* 하위 폴더명 css, styles 으로 css파일 배치
* ex) index.html, index.css
## CSS 외부스타일시트와 내부스타일시트
* name.css 외부파일로 분리해서 html에 link로 연결하는 **외부스타일시트**
* html파일 내에서 head태그 안에 style태그로 구분해서 작성하는 **내부스타일시트**
* 외부스타일시트 장단점 :
- 장점 : 1개의 css 파일로 여러개의 html을 관리할 수 있다.
- 단점 : 파일명 또는 파일 위치를 정확히 관리하지 않으면 파일 관리가 어려울 수 있다. 
* 내부스타일시트 장단점 :
- 장점 : html파일 내에 작성하여 태그와 한꺼번에 보기 편하다.
- 단점 : 2개이상의 html파일을 동시에 디자인관리하는것이 불가능하다.
## CSS 선택자
1. 태그선택자 : `<h1></h1>` -> `h1 {속성:값;}`
2. 클래스선택자 : `<h1 class="a"></h1>` -> `.a{속성:값;}`
3. 아이디선택자 : `<h1 id="b"></h1>` -> `#b{속성:값;}`
4. 자손선택자 : `<h1><em><span></span></em></h1>` -> `h1 em span {속성:값;}`
5. 자식선택자 : `<h1><em><em></em></em></h1>` -> `h1 > em {속성:값;}`
## CSS 디자인하기
* CSS 작성 전 HTML이 미리 디자인이 되어있으면 안된다.
* **HTML을 디자인 초기화하는 작업이 CSS 디자인 전 반드시 선행되어야 한다!!!**
* 초기화 CSS `reset.css` 공통파일(날짜나 프로젝트명 표기금지!)
# CSS 글자 표현 속성
## font-family
* 로컬글꼴(설치글꼴제공) 또는 웹 글꼴을 연결할 수 있다.
* "메인대표글꼴", "후보글꼴" (후보제한없음)
* 후보글꼴은 메인글꼴과 모양이 비슷한 글꼴로 연결해야 한다.
* 글꼴이름에 한글 or 공백이 있으면 "" 필요 ex)"맑은 고딕","Noto Sans KR"
## font-size
* 웹 글꼴 평균 16px
* 사용 단위 px, %, em, rem
* 절대값 : px, 상대값 : %, em, rem(권장)
# 선택자 우선 순위
* #아이디(3) > .클래스(2) > 태그 (1)
1. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box .a .b p {}` 3+2+2+1 = 8
* `#box #a .b p {}` 3+3+2+1 = 9
* `#wrap #box .a {}` 3+3+2 = 8
* `#wrap .a .b p {}` 3+2+2+1 = 8
2. 다음 중 우선 순위가 가장 높고 낮은 선택자는?
* `#box a b {}`
* `#box a .b {}`
* `#wrap #box a p {}`
* `#wrap #box .a .b {}`
## color
* 영문명 직접 입력 ex) 테스트용으로 주로 밝은색을 사용한다.
* aqua, lime, yellow, coral, ...
* 헥사코드 입력 최소값0 ~ 최대값F RGB 코드 기준
* RGB 웹 색상 기준으로 색상을 섞을 수록 밝아진다.
* #Hex #000000 => #000, #FF00CC => #F0C
* rgba(red, green, blue, alpha) *최대색상 255
## box css
### display
* `block, inline, inline-block`
* 특정 태그가 화면에 어떻게 표시될지 지정하는 속성
* `block` : 새로운 행, 크기, 여백 인식
* `inline` : 내용만큼 크기 인식(그 외 크기인식 불가능)
* `inline-block` : 내용만큼 크기인식 (크기 추가설정 가능), 옆으로 정렬
### box-sizing
* `box-sizing:border-box`
* 요소의 너비와 높이를 계산할 때 테두리, 여백(padding)까지 포함해서 계산하는 속성
* 속성 미적용 시 : w100+h100+padding-top20 = 100x120
* 속성 적용 시 : w100+h100+padding-top20 = 100x100
### width, height
* 요소의 너비와 높이
* 절대값px, 상대값%, 화면 상대값 vw, vh
* 상대값 처리는 0~100% 사이 값만 사용한다.
## form요소와 속성
### `<form action="#" method=""></form>`
* action : 폼 데이터를 제출할 서버 스크립트 지정
* method : 폼 데이터를 제출하는 방법
* fieldset, legend : 정보 컨트롤 요소 들을 용도에 맞게 그룹으로 묶을 경우 사용&form의 자식 요소로 배치, 그룹제목&fieldset의 자식으로 배치
### `<input type="" name="">`
* type : 입력 필드의 종류
* name : 서버(action)전송 시 입력한 데이터 구분 명칭
* readonly : 읽기전용 설정
* autofocus, autocomplete : 페이지 로딩 시 해당 컨트롤 자동 포커스 설정, autocomplete : 검색기능 자동완성 설정
* value : 미리 제시된 텍스트(활성화 시 제거안됨)
* placeholder : 미리 제시된 텍스트(활성화 시 제거됨)
* value와 placeholder의 차이점 : value 활성화시 제거 불가능, placeholder 활성화 시 제거 가능
* maxlength : 최대글자 수 지정
### `<textarea></textarea>`
* rows, cols : 행, 열
* 사용용도 및 주의사항 : 띄어쓰기, 엔터치기가 그대로 적용되어 결과가 이상해질수있음
### input의 입력양식과 선택양식
* text, url 등의 사용자가 직접입력가능한 입력양식
* radio 등의 사용자의 입력이 아닌 선택으로 들어가는 선택양식
* `name` : 입력양식(데이터구분용), 선택양식(데이터구분(개별데이터X, 그룹데이터구분용))
* `value` : 입력양식(초기값), 선택양식(개별데이터구분용)
## CSS Layout
### float, flex
* `float` : 형제 관계에 해당하는 block or inline tag 왼쪽, 오른쪽 정렬할 때 사용
* 예 : ul-li*3개 정렬 `ul li {float:left}`
* `flex` : 정렬하고자 하는 아이템의 부모한테 flex를 먼저 설정한다.
* 예 : ul-li*3개 정렬 `ul {display:flex}`
* flex 설정 시 기본값 : 메인축(수평) 교차축(수직)
* `display: flex` : 정렬대상의 부모 설정 속성값, 설정 시 해당 부모 기준 자식까지(자손X) flexible box layout으로 처리하겠다
* `flex-direction` : container에 적용하는 속성으로 container안의 item의 메인축 방향을 설정합니다.
* row(왼쪽->오른쪽 수평축 (기본값))
* row-reverse(오른쪽->왼쪽) column(위->아래 수직축 변경) 
* column-reverse(아래->위)
* `flex-wrap` :  container에 적용하는 속성으로 container 내부 items 줄바꿈처리를 설정합니다.
* wrap(기본값(자동 줄바꿈) ex) 1 2 3) 
* wrap-reverse(행 기준 역방향으로 자동 줄바꿈 처리) 
* nowrap(줄바꿈하지 않음(한 줄 처리) 가변너비에 따라 자동으로 % 크기 변경)
* `flex-flow` : container에 적용하는 속성으로 flex-direction과 flex-wrap을 묶음으로 처리할 수 있습니다.
* 예 ) `flex-direction:column` + `flex-wrap:nowrap` 일 경우, `flex-flow:column nowrap` 이라고 작성 가능
* `justify-content` : container에 적용하는 속성으로 메인축의 정렬방법을 설정합니다.
* flex-start(items의 시작점 container의 시작점으로 정렬) 
* flex-end(items의 시작점 container의 끝점으로 정렬)
* center(items을 메인축 기준 container에서 가운데 정렬) 
* space-between(items을 container의 start, end 양끝 items을 배치하고 나머지는 고르게 정렬) 
* space-around(items을 container안에서 균등한 여백을 포함하여 정렬)
*  `align-content` : container에 적용하는 속성으로 교차축의 아이템이 2줄 이상일 경우 정렬방법입니다. (flex-wrap:wrap 적용한 상태로 확인)
* stretch(기본값(교차축 기준으로 아이템 늘리기)) 
* flex-start(container의 start지점 기준 item 정렬) 
* flex-end(container의 end 지점 기준 item 정렬) 
* center(container의 가운데 위치 기준 item 정렬) 
* space-between(container의 start, end 에 양쪽 끝 맞추고 나머지 item 균등하게 정렬) 
* space-around(container에서 모든 item 균등하게 정렬)
*  `align-items ` : container에 적용하는 속성으로 교차축의 아이템이 1줄 일 경우 정렬방법입니다.
* stretch((기본값) 교차축 방향 시작지점에 맞춰서 정렬(start와 거의 차이 없음)) 
* flex-start(교차축 기준 container의 시작지점에 맞춰서 정렬(왼쪽 / 위)) 
* flex-end(교차축 기준 container의 종료지점에 맞춰서 정렬(오른쪽/아래)) 
* center(교차축 기준 container의 가운데지점에 맞춰서 정렬(수직중앙, 수평중앙)) 
* baseline(교차축 기준 container의 시작지점에 맞춰서 정렬(왼쪽 / 위))
* `align-self` : item에 적용하는 속성으로 container에 적용하는 align-items보다 우선순위가 높습니다. flex box의 교차축을 정렬합니다.
* order : item에 적용하는 속성으로 아이템의 정렬 순서 설정
* order:-1(ex 예시 숫자 중 가장 작은 수로 첫번째 정렬된다.)
* order:0(ex 예시 숫자 중 두번째 큰 수로 첫번째 정렬된다.)
* order:1(ex 예시 숫자 중 가장 큰 수로 첫번째 정렬된다.)
* `flex` : item에 적용하는 속성으로 증가/감소/기본의 묶음 속성입니다.