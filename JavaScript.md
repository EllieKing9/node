
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
    
  var는 block scoping의 대상
  let이나 const는 block scoping의 대상이 됨
    var x = 1
    if (true) {
      var x = 2
    }
    console.log(x) // 2가 출력
  ```
  
■ closure
  closure = function + environment
  ```
  함수가 호출 될 때 마다 closure가 생성
  Debugging 해보면서 보기를
  ```

■ prototype
  
