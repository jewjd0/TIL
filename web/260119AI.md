# 웹 개발 요약 노트

## 1. 웹이란?
- **웹(Web)**: 거미줄처럼 촘촘하게 엮인 정보 구조
- **구성 요소**:
  - HTML: 구조 정의
  - CSS: 스타일링
  - JavaScript: 동작/기능

## 2. HTML (HyperText Markup Language)
- **역할**: 웹 페이지의 의미와 구조 정의
- **Hypertext**: 다른 페이지로 연결하는 링크
- **Markup Language**: 태그로 문서 구조 명시 (ex. HTML, Markdown)
- **기본 구조**:
  ```html
  <!DOCTYPE html>
  <html>
    <head>
      <title>문서 제목</title>
    </head>
    <body>
      <!-- 내용 -->
    </body>
  </html>
  ```
- **태그 요소**: 여는 태그, 닫는 태그(없을 수도 있음), 내부 내용
- **예시**:
  ```html
  <body>
    <p>This is my page</p>
    <a href="https://www.google.co.kr/">Google로 이동</a>
    <img src="images/sample.png" alt="sample-img">
  </body>
  ```
- **속성**: 태그에 추가 정보 제공 (ex. href, src, alt)
  - 절대 경로: 전체 경로 지정 (주로 외부 링크)
  - 상대 경로: 현재 폴더 기준 (주로 내부 리소스)

## 3. 개발자 도구
- F12로 실행
- 문서 구조, 콘솔, 스타일 등 확인 가능
- 프론트/백엔드, 크롤링 등 다양한 용도

## 4. CSS (Cascading Style Sheet)
- **역할**: 웹 페이지의 디자인과 레이아웃 구성
- **스타일 적용 방법**:
  - 인라인(비추천)
  - 내부(Internal): `<style>` 태그
  - 외부(External): 별도 .css 파일 (권장)
- **기본 문법**:
  ```css
  h1 {
    color: blue;
    font-size: 30px;
  }
  ```
  - 선택자(selector), 선언(declaration), 속성(property), 값(value)

### CSS 선택자
- 전체 선택자: `*`
- 태그 선택자: `p`, `h1` 등
- 클래스 선택자: `.className`
- 아이디 선택자: `#idName` (문서 내 유일)
- 속성 선택자: `[attr=value]`
- 결합자(Combinators):
  - 자손: `.parent tag`
  - 자식: `.parent > tag`

### 명시도(Specificity)
- 인라인 > id > class > 태그
- 같은 명시도면 아래쪽 선언이 우선
- `!important`는 최우선 (가급적 사용 X)

### 네이밍 규칙
- kebab-case 권장 (ex. `.main-title`)
- BEM, OOCSS 등 방법론 참고

## 5. CSS Box Model
- 모든 요소는 사각형 박스
- 구성: content → padding → border → margin
- 방향: top, right, bottom, left
- 크기 지정: width, height (content 기준)
- `box-sizing`: content-box, border-box

## 6. Box Type
- **block**: 새 줄, width 100%, h1~6, p, div 등
- **inline**: 한 줄, width/height 적용 X, a, img, span 등
- **inline-block**: inline처럼 배치, block처럼 크기 지정

## 7. Position & z-index
- **position**: 요소의 위치 지정 (static, relative, absolute, fixed, sticky)
- **z-index**: 요소의 쌓임 순서(레이어)

## 8. 상속
- 일부 CSS 속성은 부모로부터 상속됨

## 9. Bootstrap
- 프론트엔드 프레임워크 (디자인/레이아웃 빠른 구현)

---

## 참고/팁
- 태그, 속성, CSS 속성은 필요할 때 검색 (MDN Web Docs 추천)
- 개발자 도구로 실시간 확인/테스트
- 클래스 여러 개 지정 가능 (공백으로 구분)
- 여러 클래스 적용 시, 아래쪽 선언이 우선

---

## 자주 묻는 질문
- **align: center**와는 다른 개념인가요? → 네, 정렬과는 별개로 박스 모델/배치 개념이 있음
- **클래스 여러 개 지정 가능?** → 네, 공백으로 구분
- **여러 클래스 지정 시 스타일 적용 순서?** → 아래쪽 선언이 우선, 명시도에 따라 다름

---

# 끝.