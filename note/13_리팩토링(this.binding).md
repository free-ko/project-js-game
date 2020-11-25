# 리팩토링

- this.binding에 대해 알아 보겠습니다.
- 리팩토링 하는 과정에서 버그 이미지 눌렀을 때 사운드가 나오지 않았습니다.
- 즉 이벤트 클릭을 했음에도 진행이 안되고 있습니다.

<br>

```js

export class Field {
  constructor(carrotCount, bugCount) {
    ...

      // 우리는 addEventListener에 this.onClick을 등록했습니다.
      // 그래서 field에서 아이템이 클릭이 되면 this.onClick이 콜백함수가 호출되어집니다.
      // 다른 언어에서는 자연스럽지만 JS에서는 자연스럽지 않습니다.
      // 밑에 this.onClick 함수를 인자로 'click'으로 전달 할 때
      // 클래스 정보는 함께 전달되지 않습니다.
      // 즉 onClick에 포함된 클래스 정보는 콜백으로 전달되지 않습니다.
      // 그래서 onClick함수를 클래스와 바인딩 해줘야 합니다.
      // 이것을 this 바인딩이라고 합니다.
      // bindg 해주는 방법은 총 3가지가 있습니다.

      // 1. 직접적으로 this.onClick= this.onClick.bind(this);
      // 2. this.field.addEventListener('click', (event) => this.onClick(event));
      // 3. onClick = event => {};로 감싸기
      this.field.addEventListener('click', this.onClick)


onClick(event) {
...
      } else if (target.matches(".bug")) {

        // 클래스 안에서 이벤트가 작동될때 함수를 인자로 보내는 상황입니다.
        // onClick이라는 함수가 밑에서 작동이 되어야 합니다
        // 하지만 밑에 보시면 this.onItemClick를 할 때 아까는 class의 this라고 지칭이 되었지만
        // onClick 함수가 'click'으로 전달된 상황에서 무언가를 실행 할 때에는
        // this 안에 Field 정보가 없어서 undefined 상태 입니다.
        // 즉 this 안에 정보가 없기 때문입니다.
        // 그래서 우리는 binding을 해주어야 합니다.
          this.onItemClick && this.onItemClick('bug');
      }
  }
```
