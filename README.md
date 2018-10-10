# 반응형웹

## 도구설치

-   VS-CODE 확장팩 설치
    -   Live Server
        > HTML 보기위해 로컬 서버 작동
        >
        > 단축키 > ALT + L, O

## LESSON1 - 개념

## LESSON2 - 가변그리드

-   고정 크기의 마진과 패딩을 위해 calc 함수 사용
    ```css
    width: calc(100% - 100px);
    ```
-   가변패딩과(padding: y% x%;), 가변마진(margin: y% x%;)의 기준
    -   width: 적용할 박스를 감싸고 있는 박스의 가로너비가 기준
    -   height: 적용할 박스를 감싸고 있는 박스의 <font color="red">가로너비</span>가 기준
    ```css
    margin: 10px 25%;
    padding: 5px 12%;
    ```
-   가변 폰트

    -   가변폰트의 단위는 em, rem(root em), vw, vh, vmin, vmax
    -   em
        -   em 을 width 나 height 에 쓰는 이유는? - 일반적인 웹사이트를 개발할 때는 px 를 많이 쓰지만, 픽셀은 모니터의 해상도를 기준으로 하는데 브라우저의 폰트 사이즈를 사용자가 변경했다면 그에 따라 레이아웃도 가변적으로 바뀌어야한다. 해서 반응형웹에서는 가변폰트 단위인 em 또는 rem 를 써서 폰트크기에 적절한 레이아웃 구성을 한다.
        -   참고 LINK :
            `https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984`
        -   폰트의 대문자 M 의 너비를 기준으로 하는 글자체 크기이다.
        -   1em 은 16px
        -   일반적으로 em 보다는 rem 을 쓴다.
        -   rem 을 쓰는 이유는 em 은 상속을 받기때문에 상위요소의 영향을 받기 때문이다.
        -   가변폰트의 단위를 width 나 height 에 쓴다. 글자크기에 따라서 해당요소의 크기가 알맞게 가변적으로 변하게 하기 위함.
    -   vw(view port width)
        -   뷰포트 화면 width 의 100%를 기준으로 한다.(데스크탑의 경우 브라우저의 너비기준)
    -   vh(view port height)
        -   뷰포트 화면 height 의 100%를 기준으로 한다.(데스크탑의 경우 브라우저의 높이기준이며 텝높이 메뉴바도 포함이된다)
    -   vmin(viewport minimum)
        -   뷰포트 화면의 width 와 height 중 제일 작은 것이 기준이 된다.
    -   vmax(viewport maximum)
        -   뷰포트 화면의 width 와 height 중 제일 큰 것이 기준이 된다.

    ![](/imgs/2_1.png)
