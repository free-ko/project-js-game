# 게임 마크업 된 코드를 CSS로 적용했습니다.

<br>

```css
:root {
  /*
여기에는 공통적으로 사용할 width, height, color, font-size를 지정해서 사용하는게 좋습니다.
*/
}

body {
  text-align: center;
}

button {
  border: none;
  outline: none;
  cursor: pointer;
}

.game {
  display: flex;
  flex-direction: column;
  width: 800px;
  height: 500px;
  margin: auto;

  /* background의 position과 size를 한 꺼번에 적용할 수 있습니다. */
  background: url("./img/background.png") center/cover;
  border-radius: 20px;
}

.game__header {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 20px;
}

.game__button {
  width: 60px;
  height: 60px;
  background-color: wheat;
  border: 4px solid black;
  font-size: 24px;
  transition: transform 300ms ease-in;
}

.game__button:hover {
  transform: scale(1.1);
}

.game__timer {
  width: 100px;
  background-color: white;
  text-align: center;
  border: 5px solid black;
  border-radius: 20px;
  font-size: 32px;
  margin-top: 8px;
}

.game__score {
  text-align: center;
  width: 50px;
  height: 50px;
  margin-top: 8px;
  font-size: 46px;
  border-radius: 50%;
  border: 3px solid black;
  background-color: darksalmon;
  color: white;
}

.game__field {
  position: relative;
  width: 100%;
  height: 100%;
  margin-top: 40px;
}

.pop-up {
  display: block;
  width: 400px;
  height: 140px;
  padding: 20px;
  /* 6자리 + 숫자 = 숫자는 백그라운드에 opacity를 표현 합니다.
  단 이렇게 작성하면 백그라운드만 투명도가 적용 됩니다. 
  예를들어 밑에 처럼 코드를 작성 하지 않고 따로 opacity: 0.7;을 하게 되면 pop-up 하위에 있는 코드들 까지고 opacity가 적용됩니다.
  */
  background-color: #00000090;
  border-radius: 20px;
  color: white;
  text-align: center;
  margin: auto;
  transform: translateY(-150%);
}

.pop-up--hide {
  display: none;
}

.pop-up__refresh {
  width: 60px;
  height: 60px;
  font-size: 24px;
  background-color: wheat;
  border: 2px solid black;
  border-radius: 50%;
}

.pop-up__message {
  display: block;
  font-size: 38px;
}
```
