## javascript 공부

### prototype

### 함수와 메서드의 차이
#### 함수
- Sales.is = function() {}
- new 연산자로 인스턴스를 생성하면 함수는 인스턴스에 할당되지 않는다.
- obj.is : undefined
#### 메서드
- Salse.prototype.get = function() {}
- new 연산자로 인스턴스를 생성하면 메서드는 인스턴스에 할당된다. 인스턴스.get()으로 호출 가능
  - 여기서 할당이란 Sales.prototype.get이 생성한 인스턴스에 복사 개념으로 할당되는 것이 아니라,
  인스턴스의 get에서 Salse.prototype.get이 호출될 수 있도록 하는 메거니즘을 의미한다.
  :: 이게 복사랑 뭐가 다르지?
  따라서 인스턴스를 생성한 후, get() 코드를 변경하고 인스턴스.get()을 호출하면 변경된 코드가 실행됩니다.
  :: Salse.prototype.get이 아니라 새로운 연산자라는 건가?
- obj.get : function() {}
