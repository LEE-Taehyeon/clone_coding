# clone_coding
-----
* Using : HTML/CSS, JavaScript, Canvas
* Goals
    1. Know how to use HTML/CSS, JavaScript and Canvas.
    2. Items scrolling
    3. Image saving
* Explain
    1. Make to Canvas.
-----
* Learning about
    - CSS
        - Reset.css : [Reset.css](https://meyerweb.com/eric/tools/css/reset/) 의 코드를 복사해서 'reset.css' 파일을 만들고 붙여넣기 후, 기존 코드에 ```@import "reset.css";``` 추가하여 사용.<br></br>
        1. Canvas 사용법
        ```
        <canvas id="jsCanvas" class="canvas"></canvas>
        ```
        - <i>참고
        [JavaScript_Canvas](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API/Tutorial)</i>
    
        2. box-shadow : 해당 box 에 그림자를 줄 수 있는 property
        3. 컨텐츠 중앙정렬 : 해당 css 속성들을 작성하면 중앙정렬이 가능하다.
        ```
        display: flex;
        flex-direction: column;
        align-items: center;
        ```
        4. transition : CSS transitions allows you to change property values smoothly, over a given duration.

    - JavaScript
        1. var / let / const 의 차이
            |  var  |  let  |  const  |
            | --- | --- | --- |
            |  function-scope  |  block-scope   |  block-scope   |
            |  재선언 가능  |  재선언 불가능   |  재선언 불가능   |
            |  -  |  재할당 가능   |  재할당 불가능   |
            |  function-scope  |  ``` let a = "test1"; \` let a = "test2; -> 불가능.  a = "test3"; ```   |  ``` const a = "test1"; const a = "test2; -> 가능. a = "test3"; ```   |


        2. 버튼을 통한 이미지 저장.
            ```
                function handleSaveClick() {
                    const image = canvas.toDataURL();
                    const link = document.createElement("a");
                    link.href = image;
                    link.download = "PaintJS[🎨]";
                    link.click();
                }
            ```
        3. ``` const canvas = document.getElementById("jsCanvas"); ``` getElementById("") 로 넘어온 요소에 값이 있으면 해당 값, 없으면 null 즉 if()문의 조건으로 사용 가능.

        4. JavaScript 를 이용해 html 동적으로 만들기 - 여기서는 innerText 사용.
            ```
            function handleModeClick() {
                if (filling === true) {
                    filling = false;
                    mode.innerText = "Fill";
                } else {
                    filling = true;
                    mode.innerText = "Paint";
                }
            }
            ```
--- 
* 문제점
    1. ``` <script src="./src/app.js"></script> ``` 를 index.html ``` <head></head> ``` 에 포함시키니 정상적으로 app.js 를 불러오지 못했다.
* 해결책
    1. 이유는 브라우저의 동작방식을 이해하면 알 수 있다.
        - HTML 을 읽기 시작 -> HTML 파싱 -> DOM 트리 생성 -> Render 트리 생성(Rendering : 흰화면만 오래띄우는 경우) -> Display 표시
        - 이때, 브라우저가 HTML 태그들을 읽어나가는 중 ```<script>``` 를 만나면 파싱을 중단하고 JavaScript 코드를 파싱한다. 완료가 되면 그 후 HTML 파싱이 계속된다.
        이로 인해, HTML 사이에 script 태그가 위치하면 두가지 문제가 발생.
            1. HTML 을 읽는 과정에서 script 를 만나면 중단 시점이 생기고 그만큼 display 에 표시되는 것이 지연.
            2. DOM 트리가 생기기도 전에 JavaScript 가 생성되지도 않은 DOM 의 조작을 시도할 수 있다.

    <b><i>따라서 ```<script></script>``` 태그는 body 태그 최하단에 위치시키거나, ```<script defer src="script.js"></script>``` defer 을 이용하여 head 에 선언하는게 좋다. </i></b>
