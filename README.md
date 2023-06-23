[![스타벅스](./img/logo_top.png)](https://storied-gumdrop-5ce02e.netlify.app)

[해당페이지로 이동](https://storied-gumdrop-5ce02e.netlify.app)

# 프로젝트 명 : Starbucks Clone Codding

## 제작 기간 : 3일

## 사용 언어 : HTML, CSS, Javascript

## 사용 기술

### 1. 검색최적화를 위한 오픈그래프
```html
og: type: 페이지의 유형(E.g, website, video.movie)
og: site_name: 속한 사이트의 이름
og: title: 페이지의 이름(제목)
og: description: 페이지의 간단한 설명
og: image: 페이지의 대표 이미지 주소(URL)
og: url: 페이지 주소(URL)
```

### 2. SEO (검색엔진 최적화)
```html
<meta property="og:image" content="./images/starbucks_seo.jpg" />
<meta property="twitter:image" content="./images/starbucks_seo.jpg" />
```

### 3. 사용폰트 : 나눔고딕
구글폰트 사용
```html
<link rel="preconnect" href="https://fonts.gstatic.com" />
<link href="https://fonts.googleapis.com/css2?family=Nanum+Gothic:wght@400;700&display=swap" rel="stylesheet" />
```

### 4. 아이콘 : Google Material Icons
```html
<link rel="stylesheet" href="https://fonts.googleapis.com/icon?family=Material+Icons" />
```

### 5. lodash를 활용하여 scroll함수 제어하기
```Javascript
<script src="https://cdnjs.cloudflare.com/ajax/libs/lodash.js/4.17.21/lodash.min.jsintegrity="sha512-WFN04846sdKMIP5LKNphMaWzU7YpMyCU245etK3g/2ARYbPK9Ub18eG+ljU96qKRCWh+quCY7yefSmlkQw1ANQ==crossorigin="anonymous" referrerpolicy="no-referrer"></script>
```

### 6. gsap을 이용해 애니메이션 효과주기
```Javascript
<script src="https://cdnjs.cloudflare.com/ajax/libs/gsap/3.11.5/gsap.min.js" integrity="sha512-cOH8ndwGg+K7pTvMrqYbmI8u8k6Sho3js0gOqVWTmQMlLIi6TbqGWRTpf1ga8ci9H3iPsvDLr4X7xwhC/+DQ==" crossorigin="anonymousreferrerpolicy="no-referrer"></script>    
```

### 7. Youtube API
```Javascript
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

### 8. ScrollMagic
```Javascript
<script src="https://cdnjs.cloudflare.com/ajax/libs/ScrollMagic/2.0.8/ScrollMagic.min.js"></script>
```
```Javascript
new ScrollMagic
  .Scene({ // 감시할 장면(Scene)을 추가
    triggerElement: spyEl, // 보여짐 여부를 감시할 요소를 지정
    triggerHook: .8 // 화면의 80% 지점에서 보여짐 여부 감시
  })
  .setClassToggle(spyEl, 'show') // 요소가 화면에 보이면 show 클래스 추가
  .addTo(new ScrollMagic.Controller()) // 컨트롤러에 장면을 할당(필수!)
```

### 9. Swiper Slider
스타벅스 프로모션 버튼을 누르면 나오는 슬라이드와 footer에 있는 Awards영역을 Swiper Slider를 사용

#### - 스타벅스 프로모션
```Javascript
new Swiper(".promotion .swiper", {
direction: "horizontal",
slidesPerView: 3, //한 번에 보여줄 슬라이드 개수
spaceBetween: 10, //슬라이드 사이 여백
centeredSlides: true, //1번 슬라이드가 가운데 보이기
loop: true,
autoplay: {
  delay: 5000,
},
pagination: {
  // 페이지 번호 사용 여부
  el: ".promotion .swiper-pagination", // 페이지 번호 요소 선택자
  clickable: true, // 사용자의 페이지 번호 요소 제어 가능 여부
},
navigation: {
  // 슬라이드 이전/다음 버튼 사용 여부
  prevEl: ".promotion .swiper-prev", // 이전 버튼 선택자
  nextEl: ".promotion .swiper-next", // 다음 버튼 선택자
},
});
```

#### - footer의 Awards 영역
```Javascript
new Swiper(".awards .swiper", {
direction: "horizontal",
slidesPerView: 5, //한 번에 보여줄 슬라이드 개수
spaceBetween: 30, //슬라이드 사이 여백
loop: true, //무한반복설정
autoplay: true, //자동실행
navigation: {
  // 슬라이드 이전/다음 버튼 사용 여부
  prevEl: ".awards .swiper-prev", // 이전 버튼 선택자
  nextEl: ".awards .swiper-next", // 다음 버튼 선택자
},
});
```

### 10. 출처에 있는 년도 해마다 자동으로 변경
```Javascript
const thisYear = document.querySelector('.this-year');
thisYear.textContent = new Date().getFullYear();
```
