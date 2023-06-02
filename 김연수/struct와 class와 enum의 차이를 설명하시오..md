# struct와 class와 enum의 차이를 설명하시오.


<br />


### 💡구조체와 클래스의 공통점 <br />


   클래스와 구조체는 프로그램의 코드를 조직화 하기 위해 일반적으로 사용한다. OOP를 위한 필요 요소이기도 하다.


- 값을 저장하기 위한 프로퍼티를 정의할 수 있다
  
- 함수 기능을 하는 메서드를 정의할 수 있다
  
- 내부 값을 .으로 접근하여 사용할 수 있다
  
- 초기값을 설정하기 위해 생성자를 설정할 수 있다
  
- extension을 사용하여 기능을 확장할 수 있다(+열거형)
  
- protocol을 채택하여 기능을 설정할 수 있다
  
  <br /><br />
 

### 💡구조체와 클래스, 열거형의 차이점



### 클래스


- 참조 타입이다 <br />

     `참조 타입` 변수나 상수에 값을 할당을 하거나 함수에 인자로 전달할 때 그 값이 복사되지 않고 참조된다. <br />

```Swift

let tenEighty = VideoMode()

tenEighty.frameRate = 25.0

let alsoTenEighty = tenEighty

alsoTenEighty.frameRate = 30.0

```


- ARC로 메모리를 관리한다

   `ARC: Auto Reference Counting`

   자동으로 메모리 관리, 객체에 대한 참조 카운트를 관리하고 0이 되면 자동으로 메모리 해제된다

   run time에 계속 실행되는게 아니라 컴파일(빌드)할 때 실행된다

   Objective-C에서는 수동으로 메모리를 관리했다


- 같은 클래스 인스턴스를 여러 개의 변수에 할당한 뒤 값을 변경시키면 할당한 모든 변수에 영향을 준다(메모리만 복사)
  
- 상속이 가능하다
  
- 타입 캐스팅을 통해 런타임에서 클래스 인스턴스의 타입을 확인할 수 있다
  
- deinit을 사용하여 클래스 인스턴스의 메모리 할당을 해제할 수 있다
  
  <br />
  
  <br />
 

### 구조체


- 값 타입이다 <br />
  


  `값 타입` 함수에서 상수나 변수에 전달될 때 그 값이 복사되서 전달된다는 의미이다. Swift에서 모든 구조체와 열거형 타입은 값 타입이다


```Swift

let hd = Resolution(width: 1920, height: 1080)

var cinema = hd

cinema.width = 2048

```



- 구조체 변수를 새로운 변수에 할당할 때마다 새로운 구조체가 할당된다<br />
  
  (같은 구조체를 여러 개의 변수에 할당한 뒤 값을 변경시키더라도 다른 변수에 영향을 주지 않는다(값 자체를 복사)<br />
  
- 상속이 불가능하다<br />
  
  <br />
  
  <br />


### 열거형


- 값 타입이다 <br />
  
- 열거형은 관련된 값으로 이루어진 그룹을 공통의 형으로(type) 선언해 형 안전성(type-safety)을 보장하는 방법이다 <br />
  
- 열거형은 1급 클래스 형(first-class types)이어서 계산된 프로퍼티(computed properties)를 제공하거나 초기화를 지정하거나,
  
  <br />초기 선언을 확장해 사용할 수 있다<br />
  
- 상속이 불가능하다<br />


```Swift

enum CompassPoint {

   case north

   case south

   case east

   case west

}

var directionToHead = CompassPoint.west

directionToHead = .east

```


- 각 열거형 정의는 완전 새로운 형(type)을 정의한다(형의 이름은 대문자로 시작하며, 열거형 자체가 하나의 데이터 타입이다)<br />
  
  <br /><br /><br />


####   🧐 상속, 값을 참조할 필요가 있다면 클래스, 아니라면 구조체나 열거형을 써야겠다!
