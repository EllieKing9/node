
# JavaScript

■ 실행 모델 => offloading, non-blocking IO
  ```
  event loop: callback queue ---> call stack -> main thread
  다음 콜백(callback)를 처리하려면 지금 처리하고 있는 콜백이나 콜스택이 완전히 끝나야 함
  ```
  
■ scope, hoisting
  ```
  lexical scope
    하위(아래)에서는 위에 있는 변수나 함수를 참조 할 수 있음
    inner scope 에서는 outer scope의 변수를 binding 할 수 있음
    outer scope 에서는 inner scope의 변수를 binding 하지 못함 (ReferenceError)
  hoisting
    변수: 선언은 해당 스코프의 위로 끌어 올라가서 hoisting, 초기화 부분은 그대로
    함수: 선언과 그 내용이 한 덩어리로 해당 스코프의 위로 같이 끌어 올라가서 hoisting
    
  var는 block scoping의 대상이 안됨 : hoisting O 
    var x = 1
    if (true) {
      var x = 2
    }
    console.log(x) // 2가 출력
    
  let이나 const는 block scoping의 대상이 됨 : hoisting X
  ```
  
■ closure
  closure = function + environment
  ```
  함수가 호출 될 때 마다 closure가 생성
  Debugging 해보면서 보기를
  ```
■ debugging
  ```
  // VS Code Debugger
  > .vscode 폴더에서 launch.json 파일 생성
    Add configuration 클릭 > {} Node.js: Launch via npm 선택
  > package.json 파일 수정
    "scripts": {
      "debug": "node src/name.js"
      ..
    }
  > 브레이크 포인트 찍고 VS Code 왼쪽 패널에서 Run & Debug 
  ```

■ prototype ==> class
  ```
  //__proto__
  
  funtion Student(name) {
    this.name = name
  }
  
  const you = new Student('J')
  console.log(you)
  
  $node src/main.js
  Student { name: 'J' }
  
  -------------
  
  class Student {
    constructor(name) {
      this.name = name
    }
    
    greet() {
      return `Hu, ${this.name}.`
    }
  }
  
  const you = new Student('J')
  console.log(you.greet())
  
  $node src/main.js
  Hi, J
  
  ```
  
■ TC39 - ECMA script (https://tc39.es)
■ node.green (https://node.green/): node 버젼별로 지원하는 ECMA script 확인 가능 

■ Modern JavaScript
  ```
  //let, const vs var
  
  //Spread syntax(...)
    - object merge
      const privateData = {
        name: 'nname',
        email: 'n@email.com`,
      }
      const publicData = {
        age: 22,
      }
      const user = {
        ...privateData,
        ...publicData,
      }
      
    -------------
    object merge    
      ...overrides
    
    object rest
    
    array merge
    
    array rest
  
  // functional approach
  ```


