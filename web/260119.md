# 웹
## 웹
  - **거미줄처럼 촘촘하게 엮인 구조**
  - 구성 요소:
    - JavaScript : 동작/기능
    - CSS : 요소 스타일링
    - HTML : 구조 정의
## HTML (HyperText Markup Language)
  - 웹 페이지의 의미와 구조 정의
  - **Hypertext** : 웹 페이지를 다른 곳으로 연결하는 링크
  - **Markup Language** : 태그 등을 이용해 문서나 데이터의 구조 명시
    - ex. HTML, Markdown
    - 기능이 없고 구조를 보여주는 게 목적
    - 글씨 크기, 색 이런거 없고 어떻게 마킹할건지만 나와있음
    - 태그를 마크업이라고 부름 h1, h2, p 등등
  - **기본 구조**:
    ```html
    <!DOCTYPE html> <!-- html로 작성되었다는 표시 -->
    <html> <!-- 전체 페이지의 콘텐츠 감싸는 태그 -->
      <head> 
      <!-- 문서에 관한 설명, 설정 등 -->
      <!-- 사용자에겐 보이지 않음 -->
        <title>문서 제목</title> 
      <!-- 탭에서 표시되는 제목 -->
      </head>
      <body> 
      <!-- 페이지에 표시되는 모든 콘텐츠 -->
      </body>
    </html>
    ```
### 태그 요소 
  - 여는 태그
  - 닫는 태그 (없는 태그도 존재)
  - 내부 내용
  - 예시 코드
    ```html
    <body>
      <p>This is my page</p>
      <a href="https://www.google.co.kr/">Google로 이동</a>
      <!-- 닫는 태그 없는 태그 -->
      <img src="images/sample.png" alt="sample-img">
    </body>
    ```
### 속성
  - **태그에 추가 정보 제공**
    - href, scr, alt, id, class 등
  - **요소 이름과 속성 사이 공백 필요**
  - **하나 이상의 속성: 공백으로 구분**
  - 절대 경로 
    - 어디 있던 그 장소로 이동할 수 있게 해줌
    - 웹 하이퍼링크 등
  - 상대 경로 
    - 현재 폴더 기준 이동
    - 폴더 내 리소스 파일 등
  - 예시 코드
    ```html
    <!-- 하나 이상의 속성 공백으로 구분 -->
    <div class="box content-box">content-box</div>
    <!-- 절대 경로 사용 -->
    <a href="https://www.google.co.kr/">Google로 이동</a>
    <!-- 상대 경로 사용 -->
    <img src="images/sample.png" alt="sample-img">
    ```
- 태그, 속성들은 사용하면서 찾아보는 편이 편하다. 다 못외움
  - 링크: [MDN Web Docs (즐겨찾기 해두기)](https://developer.mozilla.org/ko/docs/Web/HTML)
  - 자주 사용되는 것들은 교재에 기록되어있으니 참고할 것

### 개발자 도구
  - F12 (웹페이지에서)
  - 문서 구조 확인 가능
  - 콘솔 확인 가능
  - 프론트, 백, 데이터 수집(크롤링) 에 모두 사용됨
  - 수업은 크롬 기준이지만 다양한 곳에서 개발자 도구 사용해보는 것 추천

  
## CSS
> - Cascading Style Sheet (계단식 스타일 시트)
>   - 웹 페이지의 디자인과 레이아웃을 구성하는 언어 
- 이쁘게 만드는것만이 디자인이 아님. 보기 편하게 만드는 것
- 기본 태그 스타일들이 css로 미리 정의되어 있다. 
  - user agent stylesheet라고 정의되어 있음
  - 정의 안되어있으면 아무리 마크업 써둬도 그대로 안보임
- 레이아웃은 해상도, 웹 브라우저 등에 따라 다름
- html은 그냥 태그를 적을 뿐
  - symentic tag 
    - 의미를 가진 태그
  - ex. div, span 
    - 의미없고 오직 영역만 나눔
    - 화면을 못볼 때, 컴퓨터 기준, 크롤링 기타등등
    - 무조건 화면을 눈으로 볼 거라고 생각하지 말것. 
    - 전처리할 때 symentic tag 의미 알아야 전처리가 편함
### 웹 스타일링
  - 양식
    ```css
    h1{
      color: blue;
      font-size: 30px;
    }
    ```
  - h1 -> 선택자(selector)
  - color: blue; -> 선언(declaration)
  - color, font-size -> 속성(Porperty)
  - blue, 30px -> 값(Value)
  - key - vlaue 와 헷갈리지 말것
### CSS 적용 방법
- ~~인라인 스타일 (안씀)~~
  - 명시도 1000
  - 혼자 독자적으로 다른 스타일 적용
  - 문서 관리에 있어서 너무 불편
  - 프로그래밍에서 그냥 클래스 만들지 다 일일히 변수 안만드는것처럼 안씀
- 내부(internal) 스타일 시트
  - head 태그 내부 style태그에 작성
  - 스타일 길면 길수록 잘 안보이고 유지보수도 불편
  - 문서마다 다 스타일 작성해줘야함
  - 같은 양식 사용하는데 html 문서 다르면 다 각각 작성해야한다...
- **외부(external) 스타일 시트**
  - css 파일 생성 후 html link태그를 사용해 불러오기
- 명시도
  - 얼마나 잘 보이는지? 얼마나 구체적으로 지목하는지
  - 1-0-0, 0-1-0, 0-0-1 이런식으로 표현.
  - 그냥 그대로 100점이라고 인식해도 무방
### CSS 선택자(selector)
  - 잘 선택해야 함
  - 기본 선택자
    - 전체(*) 선택자
      - 전체선택
    - 요소(tag) 선택자
      - ex) p 태그 일괄적용
    - 클래스(class '.'(dot)) 선택자
      - 같은 클래스 지정하면 같은 스타일 적용
    - 아이디(id '#') 선택자
      - 고유값 **(문서 안에 하나만 존재!!)**
      - 인라인 스타일 대신 id 지정해서 적용
    - 속성(attr) 선택자
  - 결합자 (Combinators)
    - 자손 결합자 (" "(공백))
      - 안에 포함된 것들 중 하나
      - green 클래스 있는 곳 안의 li태그들
    - 자식 결합자 (">")
      - 직계 자식
  ```css 
  h2 { /* 타입 선택자 */
      color: orange;
  }
  .green { /*클래스 선택자*/
    color: green;
  }

  #purple { /*id 선택자*/
    color: purple;
  }
  
  .green>span { /* 자식 결합자 */
    font-size: 50px;
  }
    
  .green li { /* 자손 결합자 */
    color: brown;
  }
  ```
### 명시도
  - 결과적으로 요소에 적용할 CSS 선언을 결정하기 위한 알고리즘
  - 동일 요소 2개 이상 CSS 규칙 존재할 경우 가장 높은 명시도 가진 selector 승리.
  - 같은 명시도면 가장 아래 작성된 게 높음
  - Importance
    - !important
    - 모든 걸 무시하고 얘를 적용
    - 알고만있고 쓰지마세요
  - **인라인 스타일 > id 선택자 > class 선택자 > 요소 선택자**
    - 이래서 인라인 쓰지말라고 하는거
    - 요소에 마우스 커서두고 호버해두면 vscode가 점수표기해줌
  - id -> 고유요소 -> 정확하게 집음
  - 선택자 이름 규칙
    - **kebab-case** (띄어쓰기 대신 - (하이픈) )
  - 방법론
    - BEM 방식
      - __ 사용하는게 js에선 좀 곤란
    - OOCSS 방식
      - 객체처럼 사용?
  - id, class에서 쓰면 안되는 이름
    - html, css측면에선 딱히없다
    - 근데 가독성 측면, js에서 동작하게 하려면 그거 규칙 따라야함 (언어로 시작, 특수문자 제한 등)
  - css의 모든 속성을 외우려고 하지 마라
    - 자주 사용되는 속성은 그리 많지 않고 그거는 하다보면 알게 됨
    - 점점 안쓰는 애들도 그냥 남겨둬서 자료가 방대함
    - 그냥 필요할 때 검색하서 알아내기
### CSS Box Model
  - 모든 HTML 요소를 사각형 박스로 표현하는 개념
  - 원: 네모 박스를 깎아낸 것 
    - css 깎아서 온갖 도형 만들수있다..
  - 내용(content), 안쪽 여백(padding), 테두리(border), 외부 간격(margin)으로 구성
    - content 
      - 콘텐츠 표기 영역
    - padding
      - 콘텐츠 주위 공백 영역
    - border
      - 콘텐츠와 패딩을 감싸는 테두리 영역
    - margin
      - 해당 박스와 다른 요소 사이의 공백. 가장 바깥쪽 영역
      - 요소와 요소 사이의 공백
  - 방향별로 top, right, left, bottom으로 나눔
  - shortcut 지원
    - 상하 좌우 순으로 작성
    - auto: 자동 가운데정렬
  - 박스의 크기
    - 개발자 도구 -> 마우스 포인터 같이 생긴 inspector 가면 영역 표시해줌
    - 개발자 도구를 애용합시다. 적용하고 말고를 개발자 도구에서 따로 시험해볼 수 있다!
    - width, height
      - padding, margin 빼고 콘텐츠 영역을 지정
      - 값을 내용 크기보다 작게 적으면 내용이 밖으로 튀어나감
      - 실제 박스의 크기는 마진 패딩 다 더해야함
    - box-sizing
      - 박스의 사이즈 직접지정
      - content-box
      - border-box
### Box Type
  - block
    - 항상 새로운 행으로 나뉨
    - width, height로 너비 , 높이 지정
    - width는 기본적으로 100%
    - h1~6, p, div
  - inline
    - 새로운 행으로 나뉘지 않음
    - width, height 사용불가
    - 수직 방향
      - padding, margin, border 적용, 다른 요소 밀어내기 불가
    - 수평 방향
      - padding, margin, border 적용, 다른 요소 밀어내기 가능
    - a, img, span
  - display
    - inline, block의 중간
### CSS Position
  - normal flow 에서 다른 위치로 배치
  - 다른 요소 위에 올리기, 특정 위치에 고정시키기
### CSS 상속
### z-index
  - html의 요소는 기본적으로 3d
  - 높이? 레이어 순서? 지정 가능
### Bootstrap
  - 프론트엔드 프레임워크


# &nbsp;
# 기타 혼잣말
## 질문
- align: center 랑은 다른 개념인가요?
- 클래스 여러개 지정 가능? 공백으로 구분하고
- 클래스 여러개 지정하면 위에있는거 먼저적용하고 아래거 겹치는 걸 덮어쓰는 방식으로 스타일이 결정되는건가?
## 잡설
- box none 면 none가 적용되는듯
- 깃 라이브 다시보기. 확실하게 익히기

