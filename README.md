# 반응형웹

## 도구설치

- VS-CODE 확장팩 설치
  - Live Server
    > HTML 보기위해 로컬 서버 작동
    >
    > 단축키 > ALT + L, O

## LESSON1 - 개념

## LESSON2 - 가변그리드

- 고정 크기의 마진과 패딩을 위해 calc 함수 사용
  ```css
  width: calc(100% - 100px);
  ```
- 가변패딩과(padding: y% x%;), 가변마진(margin: y% x%;)의 기준
  - width: 적용할 박스를 감싸고 있는 박스의 가로너비가 기준
  - height: 적용할 박스를 감싸고 있는 박스의 `가로너비`가 기준
  ```css
  margin: 10px 25%;
  padding: 5px 12%;
  ```
- 가변 폰트

  - 가변폰트의 단위는 em, rem(root em), vw, vh, vmin, vmax
  - em
    - em 을 width 나 height 에 쓰는 이유는? - 일반적인 웹사이트를 개발할 때는 px 를 많이 쓰지만, 픽셀은 모니터의 해상도를 기준으로 하는데 브라우저의 폰트 사이즈를 사용자가 변경했다면 그에 따라 레이아웃도 가변적으로 바뀌어야한다. 해서 반응형웹에서는 가변폰트 단위인 em 또는 rem 를 써서 폰트크기에 적절한 레이아웃 구성을 한다.
    - 참고 LINK :
      `https://webdesign.tutsplus.com/ko/tutorials/comprehensive-guide-when-to-use-em-vs-rem--cms-23984`
    - 폰트의 대문자 M 의 너비를 기준으로 하는 글자체 크기이다.
    - 1em 은 16px
    - 일반적으로 em 보다는 rem 을 쓴다.
    - rem 을 쓰는 이유는 em 은 상속을 받기때문에 상위요소의 영향을 받기 때문이다.
    - 가변폰트의 단위를 width 나 height 에 쓴다. 글자크기에 따라서 해당요소의 크기가 알맞게 가변적으로 변하게 하기 위함.
  - vw(view port width)
    - 뷰포트 화면 width 의 100%를 기준으로 한다.(데스크탑의 경우 브라우저의 너비기준)
  - vh(view port height)
    - 뷰포트 화면 height 의 100%를 기준으로 한다.(데스크탑의 경우 브라우저의 높이기준이며 텝높이 메뉴바도 포함이된다)
  - vmin(viewport minimum)
    - 뷰포트 화면의 width 와 height 중 제일 작은 것이 기준이 된다.
  - vmax(viewport maximum)
    - 뷰포트 화면의 width 와 height 중 제일 큰 것이 기준이 된다.

  ![](/imgs/2_1.png)

## LESSON3 - 미디어쿼리와뷰포트

- 미디어 유형

  - all
    > 모든장치
  - print
    > 인쇄장치
  - screen
    > 컴퓨터 화면 장치 또는 스마트 기기의 화면
  - tv
    > 영상과 음성이 동시에 출력되는 장치
  - projection
    > 프로젝터 장치
  - handheld
    > 손에 들고 다니는 소형 장치
  - speech
    > 음성 출력 장치
  - aural
    > 음성 합성 장치(화면을 읽어 소리로 출해 주는 장치)
  - embossed
    > 점자 인쇄 장치(화면을 읽어 종이에 점자를 찍어내는 장치)
  - tty
    > 디스플레이 기능이 제한된 장치
  - braille
    > 점자 표시 장치

- 조건문

  ```css
  @media (min-width: 320px) and (max-width: 768px);
  ```

  - width
    > 뷰포트 화면의 width
  - height
    > 뷰포트 화면의 height
  - device-width
    > 기기의 가로 width(해상도 width)
  - device-height
    > 기기의 세로 width(해상도 height)
  - orientation

    > 기기화면방향

    > portrait(세로)

    > landscape(가로)

  - aspect-ratio

    > 화면비율

    > 화면 비율(1)

    > 종횡비(16/9)

    > 해상도(1280/720)

  - device-aspect-ratio

    > 단말기 화면 비율

    > 화면 비율(1)

    > 종횡비(16/9)

    > 해상도(640/320)

  - color

    > 기기의 비트수(8bit 단위)

  - color-index

    > 기기의 색상수

  - monochrome

    > 기기가 흑백일 때 픽셀당 비트 수(1bit 단위)

  - resolution

    > 기기의 해상력

    > 300dpi/dpcm

  - scan

    > TV 의 스캔 방식

    > progressive/interlace

  - grid

    > 기기의 그리드/비트맵

    > 0: 비트맵 방식 / 1: 그리드 방식

- 주의사항

  - 기본적으로 CSS(Cascading style sheets)의 뜻을 살펴보면 우선순위가 있는 스타일 시트라는 의미이다.
  - 캐스케이딩(우선순위)를 결정하는 요소

    > 1. 중요도

    > 2. 명시도

    > 3. 코드의 순서

  - 그렇기 때문에 미디어 쿼리를 작성할 때 아래와 같은 순서대로 작성해야 한다.

    > min 문을 사용할 때는 크기(width)가 작은 순서대로 작성

    > max 문을 사용할 때는 크기(width)가 큰 순서대로 작성

  - 미디어 쿼리 desktop, tablet, mobile 분기처리
  - 기본적으로 아래와 같이 처리 할 수 있다.

    ```css
    /* All Device */
    모든 해상도를 위한 공통 코드를 작성한다. 모든 해상도에서 이 코드가 실행됨.

    /* Mobile Device */
    @media all and (max-width:767px) {
        사용자 해상도가 767px 이하일 때
    }

    /* Tablet Device */
    @media all and (min-width:768px) and (max-width:1024px) {
        사용자 해상도가 768px 이상이고 1024px 이하일 때
    }

    /* Desktop Device */
    @media all and (min-width:1025px) {
        사용자 해상도가 1025px 이상일 때
    }
    ```

  - 화면크기에 따른 분기처리

    ```css
    @media all and (min-width:768px) and (max-width:1024px) {
        뷰포트 너비가 768px 이상 그리고 1024px 이하이면 실행
    }

    @media all and (width:768px), (width:1024px) {
        뷰포트 너비가 768px 이거나 또는 1024px 이면 실행
    }

    @media not all and (min-width:768px) and (max-width:1024px) {
        뷰포트 너비가 768px 이상 그리고 1024px 이하가 ‘아니면’ 실행
    }

    @media all and (device-width:320px) and (device-height:480px) {
        스크린 너비가 320px 그리고 높이가 480px 이면 실행
    }

    @media all and (min-device-width:320px) and (min-device-height:480px) {
        스크린 너비가 최소 320px 이상 그리고 높이가 최소 480px 이상이면 실행
    }

    @media all and (orientation:portrait) {
        뷰포트의 방향이 세로 모드.
    }

    @media all and (orientation:landscape) {
        뷰포트의 방향이 가로 모드.
    }
    ```

- 뷰포트 속성
  - width
    > device-width, 양수 (뷰포트의 너비 지정)
  - height
    > device-height, 양수 (뷰포트의 높이 지정)
  - initial-scale
    > 양수, 기본값: 1, 1 보다 작을 경우 축소된 페이지, 1 보다 클 경우 확대된 페이지를 표시
  - user-scalable
    > yes, no - 뷰포트의 확대/축소 가능 여부
  - minimum-scale
    > 뷰포트의 최소 축소 비율, 기본값: 0.25
  - maximum-scale
    > 뷰포트의 최대 확대 비율, 기본값: 5.0
  - 웹 키드(web-kit)엔진 기반의 브라우저 뷰포트 영역(chrome, firefox)
    > 980px
  - 트라이던트 엔진 기반의 브라우저 뷰포트 영역(Explore)
    > 1024px
  - 뷰포트 확인 사이트
    > http://dnsdk300.dothome.co.kr/viewport
