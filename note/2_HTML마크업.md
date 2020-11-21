# 필요한 파일들 세팅 하기

- index.html
- styles.css
- main.js

<br>

## index.html

- font-awsome 이용
- Header 파트 부분 (게임 시작 버튼, 타이머, 스코어)
- 벌레와 당근들이 표시될 게임 필드
- 팝업

<br>

```html
<!DOCTYPE html>
  <body>
    <!-- Game -->
    <section class="game">
      <!-- Game__Header -->
      <header class="game__header">
        <button class="game__button">
          <i class="fas fa-play"></i>
        </button>
        <span class="game__timer">00:00</span>
        <span class="game__score">9</span>
      </header>
      <!-- Game__Field -->
      <section class="game__field"></section>
    </section>

    <!-- Pop-up -->
    <section class="pop-up pop-up--hide">
      <button class="pop-up__refresh">
        <i class="fas fa-redo"></i>
      </button>
      <span class="pop-up__message">Hello</span>
    </section>
  </body>
</html>
```
