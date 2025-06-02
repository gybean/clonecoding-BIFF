# Self Review

1. 파일 구조 및 구성
- [x] 역할별로 디렉토리 분리 (`/css`, `/lib`, `/font`, `/img`)
- [ ] 인라인 스타일, 스크립트 제거 -> 외부 파일로 분리 예정
- [x] 파일/폴더 네이밍 일관성 유지

---

2. HTML 리뷰
- [x] 의미론적 태그(`header`, `main` ,`section` , `footer`)를 적절히 사용
```html
  <header class="header">
    ...
    <h1 class="logo">
      <a href="#"><img src="img/2025_top_logo.svg" alt="2025 부산국제영화제 로고"></a>
    </h1><!-- .logo end -->
    ...
  </header>
```
- [x] heading 태그는 순차적으로 구조화 진행 (`<h1>`, `<h2>`, `<h3>` ..)
- [x] 모든 이미지에 `alt` 속성 적용
- [x] `h1`을 한 번만 사용

---

3. CSS 리뷰
- [x] 중복 스타일 최소화 및 공통 클래스 추출
- [x] 반응형 웹 완성 (미디어 쿼리 사용)
- [ ] 초기값, 공통된 요소 하나의 페이지에서 모두 작성 → reset.css, common.css분리하여 정리 예정

---

4. JavaScript 리뷰
- [ ] 자바스크립트와 제이쿼리 구분을 위해 변수명 앞에 $ 추가함
- [x] 메뉴 토글, 스크롤 애니메이션 등 기능 구현 완료
- [x] 코드 모듈화 완료 (기능별 함수 분리)
```
let lastScrollBar = 0;
            let headerHeight = $('.header').outerHeight();

            $(window).on('scroll', function(){
                let scrollBar = $(this).scrollTop();

                console.log(headerHeight);

                if(lastScrollBar > scrollBar) {
                    $('.header .bottom').addClass('fixed');
                } else {
                    $('.header .bottom').removeClass('fixed');
                };

                if(scrollBar <= headerHeight) {
                    $('.header .bottom').removeClass('fixed');
                };

                lastScrollBar = scrollBar;
            });
```
- Scroll Up : 헤더 발생

---

5. UX/UI 측면
- [x] 인터랙션 요소에 호버 및 포커스 스타일 제공
- [ ] 모바일 환경에서 메뉴가 터치로 작동함 -> 부분 작동 추후 개선 필요
- [x] 디자인 시각적 계층 구조 명확함
- [ ] 링크 태그에 알맞은 링크 추가

--- 

6. 개선 계획 (To-Do)
- [ ] 자바 스크립트 파일 분리
- [ ] 헤더 패밀리사이트 스와이퍼 데모 사이트 이용하여 재정비
- [ ] 모바일 환경 체크 및 보완
