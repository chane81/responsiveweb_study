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
    - 100vw == 100% width
  - vh(view port height)
    - 뷰포트 화면 height 의 100%를 기준으로 한다.(데스크탑의 경우 브라우저의 높이기준이며 텝높이 메뉴바도 포함이된다)
    - 100vh == 100% height
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

## LESSON4 - 플렉서블 박스

- 아직 W3C 의 기술 명세 확정단계가 아니다.
- 확정단계가 아니기때문에 브라우저 접두사(-webkit-)를 붙여야 안정적으로 제공이 가능하다.
- 가능한 브라우저 버전

  | 브라우저의 종류   | 브라우저 버전                         |
  | ----------------- | ------------------------------------- |
  | 익스플로러        | 11.0 ~                                |
  | 크롬              | 29.0 ~                                |
  | 사파리            | 7.0 (-webkit-)브라우저 접두사 필요    |
  | 파이어폭스        | 28.0 ~                                |
  | 오페라            | 20.0 ~                                |
  | 안드로이드        | 4.4 ~                                 |
  | iOS 사파리        | 7.0 (-webkit-)브라우저 접두사 필요    |
  | 익스플로러 모바일 | 지원 안 함                            |
  | 오페라 미니       | 지원 안 함                            |
  | 블랙 베리         | 10.0 ~ (-webkit-)브라우저 접두사 필요 |

- 기본 속성

  - display: flex, inline-flex

    - flex: 박스를 블록 수준으로 작동
    - inline-flex: 박스를 인라인 수준으로 박동

  - flex-direction: row(기본값), row-reverse, column, column-reverse

    - row: 박스를 가로로 왼쪽에서 오른쪽으로 배치
    - row-reverse: row 상태에서 배치를 reverse 함(오른쪽 -> 왼쪽 배치)
    - column: 박스를 세로로 위에서 아래로 배치
    - column-reverse: column 상태에서 배치를 reverse 함(아래쪽 -> 위쪽 배치)

  - flex-wrap: nowrap(기본값), wrap, wrap-reverse

    - nowrap: 한줄로 배치, 기본값
    - wrap: 요소들끼리 감싸며 돌게 된다. nowrap 의 경우는 요소들의 width 가 100% 가 넘어가도 해당줄에서만 표현되지만, wrap 는 100% 가 넘어가면 요소들을 다음줄로 넘긴다.
    - wrap-reverse: wrap 의 reverse 형태

  - flex-flow: flex-direction 과 flex-wrp 속성을 같이 쓰기 위한 속성

    - [flex-direction][flex-wrap]
    - `row nowrap`

  - justify-content: 주축 방향으로 다양하게 배치

    - flex-start: 기본값, 자식박스를 부모박스 주축 시작점으로 배치
    - flex-end: 자식박스를 부모박스의 끝점에서 배치
    - center: 자식박스를 부모박스의 중앙으로 배치
    - space-between: 첫번째와 마지막박스는 부모박스의 양쪽 끝으로 붙이고 나머지는 동일한 간격으로 배치
    - space-around: 박스간 동일한 간격으로 배치(이런 탓에 실제로 보면 첫번째 박스와 마지막 박스가 공간이 작은것 처럼보인다.)
    - space-evenly: 박스간 동일한 간격으로 배치(space-around 와 틀린점은 첫번째, 마지막 박스도 모두 공간이 동일한 간격이다.)

    - 그림: [flex-flow: row nowrap] 또는 [flex-flow: row wrap] 기준
      ![](/imgs/4_1.png)

  - align-items: 교차축 방향으로 다양하게 배치

    - stretch: 기본값
    - flex-start: 교차축의 시작점에 배치
    - flex-end: 교차축의 끝점에 배치
    - center: 교차축의 주앙에 배치
    - baseline: 교차축의 시작점에 배치되는 자식박스의 글자 베이스라인에 맞춰서 배치함

    - 그림: [flex-flow: row nowrap] 또는 [flex-flow: row wrap] 기준
      ![](/imgs/4_2.png)

  - align-self: 교차축 방향으로 개별 배치

    - auto: 부모박스의 align-items 속성값을 상속
    - stretch
    - flex-start
    - flex-end
    - center
    - baseline

  - align-content: `여러줄인 경우의` 교차축 방향으로 다양하게 배치

    - stretch
    - flex-start
    - flex-end
    - center
    - space-between
    - space-around
    - space-evenly

    - 그림: [flex-flow: row wrap] and [div width: 100vw] 기준
    - row 인데 수직으로 배치되는건 width 가 100%이고 wrap 속성때문에 아래로 내려갔기 때문
      ![](/imgs/4_3.png)

  - order: 0(기본값), 정숫값, 숫자 순서대로 엘리먼트가 강제 배치가 된다.

  - 플렉스 아이템의 크기 비율 조절하기

    - flex: [flex-grow][flex-shrink] [flex-basis]

      - [단일숫자]
      - 0 1 auto
      - 0 auto(0 1 auto 와 같음)
      - initial(0 1 auto 와 같음)
      - auto(1 1 auto 와 같음)
      - none(0 0 auto 와 같음)

      - 단일 숫자 사용시 예제

      ```css
        <style>
        #wrap {
            display: flex;
        }

        #wrap > div {
            width: 17rem;
            height: 25vh;
            border: 1px solid hotpink;
            margin: 0.3rem 0.3rem;
        }

        #wrap > div:nth-child(1) {
            flex: 1;
        }

        #wrap > div:nth-child(2) {
            flex: 2;
        }

        #wrap > div:nth-child(3) {
            flex: 1;
        }
      </style>
      ```

    - flex-grow: 플렉스 아이템 늘이기

      - flex-basis 값이 1 일 경우 flex-grow 사용은 남는 여백에 대한 비율을 잘라서 각 플렉스 아이템에 붙이는 것이다.
      - flex-basis 값이 0 일 경우 flex-grow 사용은 각 아이템에 대한 비율을 적용시키는 것을 의미한다.(여백없이)

    - flex-shrink: 플렉스 아이템 줄이기

      - 플렉스 아이템이 플렉서블 박스의 크기를 넘길경우 flex-shrink 에서 선언한 비율만큼 각 플렉스 아이템의 크기를 자른다.
      - flex-basis 값 1 이 디폴트이다.
      - flex-basis 값을 0 으로 할 경우 플렉스 아이템의 width 는 무시되고 순수 아이템 크기가 된다.

    - flex-basis: 기본 크기 설정
      - flex-basis 값이 1 일 경우 flex-grow 사용은 남는 여백에 대한 비율을 잘라서 각 플렉스 아이템에 붙이는 것이다.
      - flex-basis 값이 0 일 경우 flex-grow 사용은 각 아이템에 대한 비율을 적용시키는 것을 의미한다.(여백없이)
      - flex-basis 값에 퍼센트(%)를 주었을 경우 플렉서블 박스의 크기를 100%로 잡았을 때 각 아이템에 주어지는 크기 비율이다.
      - 단, 플렉스 아이템을 줄일 때 아이템안에 엘리먼트나 텍스트가 있을 경우 해당 텍스트의 길이만큼만 줄어들고, 그 이상 줄어들지는 않는다.
