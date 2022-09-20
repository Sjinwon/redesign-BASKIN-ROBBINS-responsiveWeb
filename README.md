[![BaskinRobbins](./favicon.ico)](https://sjinwon.github.io/redesign-BASKIN-ROBBINS-responsiveWeb/)

# BaskinRobbins Web Redesign

### 제작기간 : 5일

### 사용언어 : html css javasctript

<br>

## ✔ 디자인컨셉
기존의 배스킨라빈스의 기존 웹 보다는 심플함을 강조했다. 메인상단의 gif를 통해 31가지의 맛을 느낄 수 있음을 재미있는 요소로 표현했다.

<br>

## ✔ fonts 
페이지에서 사용할 'BMJUA','RixInooAriDuriR' 폰트를 지정한다.

``` css
@font-face {
  font-family: 'BMJUA';
  src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_one@1.0/BMJUA.woff') format('woff');
  font-weight: normal;
  font-style: normal;
}
@font-face {
  font-family: 'RixInooAriDuriR';
  src: url('https://cdn.jsdelivr.net/gh/projectnoonnu/noonfonts_2207-01@1.0/RixInooAriDuriR.woff2') format('woff2');
  font-weight: normal;
  font-style: normal;
}
```

<br>

## ✔ Slick Slide
다음 플러그인으로 slick slide를 사용했다.

``` html
  <link rel="stylesheet" href="./css/slick-theme.css">
  <link rel="stylesheet" href="./css/slick.css">

  <script defer src="./js/slick.js"></script>
```
### 사용법은 간단하다.

1. Slick 홈페이지의 오른쪽 상단에 get it now를 클릭 후 다운로드

    기본적으로 Slick Slider는 jQuery 기반으로 만들어진 라이브러리라 jQuery가 필요하다.

    slick-theme.css 의 기본 다음 및 이전 화살표 버튼은 횐색바탕에 투명색으로 설정이 되어 있어 배경화면이 흰색인 경우 잘 안 보이기에 상황에 맞게 수정이 필요하다.

``` html
  <link rel="stylesheet" type="text/css" href="/plugin/slick/slick.css"/>
  <link rel="stylesheet" type="text/css" href="/plugin/slick/slick-theme.css"/>

  <script type="text/javascript" src="/js/jquery.js"></script>
  <script type="text/javascript" src="/plugin/slick/slick.js"></script>
```

2. Slick Slider의 기본 HTML 구성은 아래의 코드처럼 div의 형태로 구성되어 있는 html 문서를 슬라이더 형태로 변경을 해준다.

    만약 div 형태가 아닌 다른 태그는 아래 써둔 slide 옵션을 조정하면 된다.

    더 자세한 옵션은 slick의 도큐먼트(https://github.com/kenwheeler/slick/)를 참고하자.

``` html
<!-- stlye 은 slick 영역 확인용 -->
	<div style="padding:300px 100px; background-color: skyblue;">
	  	<div id="slider-div"  >
		    <div>1</div>
		    <div>2</div>
		    <div>3</div>
		    <div>4</div>
		    <div>5</div>
		    <div>6</div>
	  	</div>
	</div>
```

3. Slide Option
``` html
<script>
  		$(function(){
			$('#slider-div').slick({
				slide: 'div',		//슬라이드 되어야 할 태그 ex) div, li 
				infinite : true, 	//무한 반복 옵션	 
				slidesToShow : 4,		// 한 화면에 보여질 컨텐츠 개수
				slidesToScroll : 1,		//스크롤 한번에 움직일 컨텐츠 개수
				speed : 100,	 // 다음 버튼 누르고 다음 화면 뜨는데까지 걸리는 시간(ms)
				arrows : true, 		// 옆으로 이동하는 화살표 표시 여부
				dots : true, 		// 스크롤바 아래 점으로 페이지네이션 여부
				autoplay : true,			// 자동 스크롤 사용 여부
				autoplaySpeed : 10000, 		// 자동 스크롤 시 다음으로 넘어가는데 걸리는 시간 (ms)
				pauseOnHover : true,		// 슬라이드 이동	시 마우스 호버하면 슬라이더 멈추게 설정
				vertical : false,		// 세로 방향 슬라이드 옵션
				prevArrow : "<button type='button' class='slick-prev'>Previous</button>",		// 이전 화살표 모양 설정
				nextArrow : "<button type='button' class='slick-next'>Next</button>",		// 다음 화살표 모양 설정
				dotsClass : "slick-dots", 	//아래 나오는 페이지네이션(점) css class 지정
				draggable : true, 	//드래그 가능 여부 
				
				responsive: [ // 반응형 웹 구현 옵션
					{  
						breakpoint: 960, //화면 사이즈 960px
						settings: {
							//위에 옵션이 디폴트 , 여기에 추가하면 그걸로 변경
							slidesToShow:3 
						} 
					},
					{ 
						breakpoint: 768, //화면 사이즈 768px
						settings: {	
							//위에 옵션이 디폴트 , 여기에 추가하면 그걸로 변경
							slidesToShow:2 
						} 
					}
				]

			});
  		})
  		
  		
  		
  		
	</script>
```

### 사용 예
``` html
<div class="slider-area">
          <div id="slider-div">
            <div class="cont">
              <div class="contbox">
                <div class="cont__main-img">
                  <img src="./image/event1.png" alt="event1">
                </div>
                <div class="cont__sub-img">
                  <img src="./image/ONLINE EVENT.gif" alt="online event">
                </div>
                <div class="cont__typo">
                  <p>KT 멤버십 고객이라면 누구나 파인트 30% 할인!</p>
                  <span>상시진행</span>
                </div>
              </div>
            </div>
            <div class="cont">
              <div class="contbox">
                <div class="cont__main-img">
                  <img src="./image/event2.png" alt="event2">
                </div>
                <div class="cont__sub-img">
                  <img src="./image/ONLINE EVENT.gif" alt="online event">
                </div>
                <div class="cont__typo">
                  <p>현대카드 M포인트 50% 사용</p>
                  <span>상시진행</span>
                </div>
              </div>
            </div>
            <div class="cont">
              <div class="contbox">
                <div class="cont__main-img">
                  <img src="./image/event3.png" alt="event3">
                </div>
                <div class="cont__sub-img">
                  <img src="./image/ONLINE EVENT.gif" alt="online event">
                </div>
                <div class="cont__typo">
                  <p>기아 멤버스 최대 50% 제휴 혜택</p>
                  <span>상시진행</span>
                </div>
              </div>
            </div>
```

<br>

## ✔ Youtube API
Iframe Player API를 통해 youtube 동영상을 제어할 수 있다.

- 유튜브 영상이 출력될 위치에 요소를 지정(생성)한다.

``` html
<!-- in HEAD -->
<script defer src="./js/youtube.js"></script>

<!-- in BODY -->
<div id="player"></div>
```

- onYouTubePlayerAPIReady 함수 이름은 Youtube IFrame Player API에서 사용하는 이름이기 때문에 다르게 지정하면 동작하지 않습니다! 그리고 함수는 전역(Global) 등록해야 한다.

- 플레이어 매개변수(playerVars)에서 더 많은 옵션을 확인할 수 있다.

``` javascript
// Youtube IFrame API를 비동기로 로드합니다.
var tag = document.createElement('script');
tag.src = "https://www.youtube.com/iframe_api";
var firstScriptTag = document.getElementsByTagName('script')[0];
firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

function onYouTubePlayerAPIReady() {
  // <div id="player"></div>
  new YT.Player('player', {
    videoId: 'An6LvWQuj_8', // 재생할 유튜브 영상 ID
    playerVars: {
      autoplay: true, // 자동 재생 유무
      loop: true, // 반복 재생 유무
      playlist: 'An6LvWQuj_8' // 반복 재생할 유튜브 영상 ID 목록
    },
    events: {
      // 영상이 준비되었을 때,
      onReady: function (event) {
        event.target.mute(); // 음소거!
      }
    }
  });
}
```