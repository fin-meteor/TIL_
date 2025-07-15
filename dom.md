# DOM (Document Object Model) 상세 설명

## 1. 정의  
DOM은 Document Object Model의 약자로, 웹 문서(HTML, XML 등)의 구조와 내용을 프로그래밍적으로 표현하는 객체 모델이다.  
브라우저는 HTML 문서를 읽어 들여, 이를 메모리 내에 트리 구조로 변환하며, 각 구성 요소는 노드(node)라는 객체 단위로 표현한다.

## 2. 구조  
- DOM은 문서의 모든 요소를 노드로 표현한다.  
- 노드 종류에는 요소 노드(Element Node), 텍스트 노드(Text Node), 속성 노드(Attribute Node) 등이 있다.  
- 노드들은 부모-자식 관계를 가지며 트리 형태로 구성된다.  
- 예를 들어, `<body>` 요소는 자식 노드로 `<h1>`, `<p>` 요소를 가질 수 있다.

## 3. 동작 원리  
- 브라우저가 HTML 문서를 파싱하면, 각 태그와 텍스트를 객체화하여 DOM 트리를 만든다.  
- 이 트리는 메모리상에 존재하며, 자바스크립트가 이 객체들을 조작해 웹 페이지를 동적으로 변경할 수 있다.

## 4. DOM 조작  
- 자바스크립트를 통해 DOM 노드를 선택, 생성, 삭제, 수정할 수 있다.  
- 주요 API:  
  - `document.getElementById()`, `document.querySelector()` 등으로 요소 선택  
  - `element.textContent`, `element.innerHTML`로 내용 변경  
  - `element.setAttribute()`, `element.style`로 속성 및 스타일 변경  
  - `document.createElement()`, `parentNode.appendChild()`로 노드 생성 및 추가  
  - 이벤트 핸들러 등록으로 사용자 인터랙션 처리

## 5. 표준과 호환성  
- DOM은 W3C(World Wide Web Consortium)에서 표준으로 제정한 인터페이스이다.  
- 표준화 덕분에 다양한 브라우저에서 일관된 방식으로 DOM을 지원한다.  
- 초기에는 브라우저별 차이가 있었으나 현재는 대부분 표준을 준수하는 편이다.

## 6. 활용 예  
- 사용자 입력에 따른 실시간 폼 검증  
- 버튼 클릭 시 메뉴 표시/숨기기  
- 페이지 내 콘텐츠 동적 갱신 (예: 뉴스 피드, 댓글)  
- 애니메이션 및 인터랙티브 UI 구현

## 7. DOM 트리 예시  

```html
<html>
  <body>
    <h1>Welcome</h1>
    <p>This is a sample DOM tree.</p>
  </body>
</html>
```

- 트리 구조:  
  - html (루트 노드)  
    - body  
      - h1 (텍스트 노드: "Welcome")  
      - p (텍스트 노드: "This is a sample DOM tree.")  
