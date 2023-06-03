# class의 성능을 향상시킬 수 있는 방법들을 나열해보시오.

<br />

### 1. heap보다는 stack메모리를 할당하려고 노력한다.

class는 heap 참조 타입 <br />
struct / enum은 stack 값 타입 <br />

<br /><br />

### 2. reference counting을 적게 만든다.

클래스에서 스트링 타입의 변수 사용을 줄인다. <br />
string은 struct타입이지만 문자열의 콘텐츠를 heap에 저장하기 때문이다. <br />

<br /><br />

### 3. dynamic dispatch보다 static dispatch를 지향한다. <br />

dynamic dispatch - 런타임 <br />
static dispatch - 컴파일 <br />

<br />

class는 상속이 가능하기 때문에 하위클래스에서 메서드가 오버라이드 될 가능성이 존재한다. <br />
그렇기 때문에 Dynamic Dispatch 방식으로 메서드를 호출하며, 런타임 시점에 호출되기 때문에 성능상 손해를 본다. <br />

<br /><br />

### 4. 클래스를 선언할 때 상속되지 않는 클래스에 final 키워드를 붙이면 성능이 향상된다. <br />

final은 상속 또는 상속에 따른 재정의를 방지하는 키워드이다. <br />
Static Dispatch로 함수를 호출해서 결과적으로 컴파일 타임에 함수를 호출하게 되고, 성능을 향상시킬 수 있다. <br />
