# Shopping Mall (feat. Dream Coding)
--------------------------------
- <b>Using : HTML/CSS, JavaScript, JSON Data</b>
- <b>Goals</b>
    1. How to know use HTML/CSS, JavaScript, json.
    2. Items scrolling
    3. Filtering data whatever we want.
    4. Extract the datas

- <b>Explain about project</b>
    - Web page
    ![](2022-05-28-19-43-37.png)
    - Extract the data we want
        1. Based on the type of 'Clothes'
        ![](2022-05-28-19-42-33.png)
        2. Based on the type of Colors
        ![](2022-05-28-19-44-38.png)

--------
- <b>Do myself</b>
    - My Idea for complate web page
        1. 정적인 페이지 만들기(HTML/CSS 만을 이용)
        ![](2022-05-28-19-51-01.png)
        2. JavaScript 를 이용하여 동적으로 데이터를 추출하는 기능 구현
    - Problems
        1. 정적인 웹페이지 구현까지는 구현했으나, 원하는 데이터 필터링하는 기능을 JavaScript 로 구현하지 못함.
    - Solve
        1. Dream Coding 강의 보면서 똑같이 구현.
--------------------------------------------------------
- <b>Learning about</b>
    - HTML

    | 태그 | 설명 | 문법 | 속성 |
    | --- | --- | --- | --- |
    | img 태그 | 이미지를 삽입  |  `<img src="" alt="" />`   | src : source 의 약자로 이미지 파일의 위치를 정하는 속성<br> alt : 대체 텍스트, 이미지를 찾지 못하는 상황에서 해당 텍스트를 출력<br> title : 말풍선을 표시, 이미지 위에 마우스 포인터를 갖다대면 해당 텍스트가 출력    |
    |section 태그|HTML 문서에 포함된 독립적인 섹션을 정의||
    |button 태그|버튼 생성|`<button type="button" onclick="alert('Hello World!')">클릭해 보세요!</button>`|type<br> button:클릭기능, submit:데이터 전송기능, reset:데이터 리셋기능|

    - CSS
    1. ``` :root{--color-black: #3f454d;} ``` - 변수 선언 : 이렇게 선언된 변수는 ```background-color: var(--color-black);``` 사용 가능.
    2.
    ```c
    body {
        height: 100vh;              // 윈도우 창 100% 차지
        background-color: var(--color-black);
        display: flex;              // 컨텐츠 정중앙에 위치하기 위함(1)
        flex-direction: column;     // 컨텐츠 정중앙에 위치하기 위함(2)
        justify-content: center;    // 컨텐츠 정중앙에 위치하기 위함(3)
        align-items: center;        // 컨텐츠 정중앙에 위치하기 위함(4)
    }
    ```
    3.
    ```c 
    transition: transform var(--animation-duration) ease; // transition 속성은 CSS 속성값이 변할 때 일정 시간을 두고 일어나게끔 하는 기능 
    transform: scale(1.1); // 상태의 크기, 회전등을 시킴
    ```
    4. ```overflow-y: scroll; // 스크롤 생성기능```

    - JavaScript
        1. 일단 데이터를 동적으로 불러오는 기능을 구현하는데 있어서 데이터를 JSON 타입으로 저장하고 불러올때 해당 JSON 데이터를 String 타입으로 가공해서 출력

        2. ```<script src="src/main_tutor.js" defer></script> // defer : 페이지가 모두 로드된 후 해당 외부 스크립트가 실행됨을 명시```

        3. .then() : 함수 실행이 끝나면 그 다음으로 할 일을 정해주는 역할

        4. fetch() : 서버와 비동기 요청방식 중 하나

        5. .innerHTML = 해당하는 HMTL 값 변경 가능

        6. addEventListener( => ) : 개발자가 정한 특정 이벤트를 주시하고 있다가 그 이벤트가 발생할 때 인자로 받은 함수를 실행. 'click', 'mousemove', 'mouseover' 등 다양한 이벤트 존재.

*각각마다의 자세한 기능설명은 따로 작성.*

--------
- <b>회고</b>
    다시 웹쪽으로 개발 진로를 정해서 공부시작과 동시에 간단한 프로젝트를 클론코딩 해봤는데 역시나 아직 많이 부족한 것 같다.
    HTML/CSS 는 물론이고 JavaScript 개념도 아직 많이 알고 있지 않아서, 혹은 너무 오래전에 했던 거라 많이 까먹어서 그런지 동적인 웹페이지를 구현하는데 있어서 많이 어려웠다.
    지금와서 보면 그렇게 어렵지 않은 기능구현인데 처음이라 생각하고 많이 배우고 많이 얻어가야하는 시간이었던 것 같다.