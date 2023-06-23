## ARC

ARC(Automatic Reference Coding)은 메모리 관리를 자동으로 처리하기 위한 기술이다.

Swift는 객체 지향 프로그래밍 언어로서 클래스 인스턴스를 사용하여 작업을 수행하는데, 이 때 메모리는 필요한 시점에 할당되고 해제되어야 한다. ARC는 객체가 더 이상 사용되지 않을 때 자동으로 메모리를 해제하여 프로그램의 메모리 사용량을 최적화한다.

ARC는 레퍼런스 카운팅을 기반으로 동작한다. 

즉, 객체가 생성될 때마다 해당 객체의 레퍼런스 카운트가 1 증가하고, 레퍼런스가 삭제될 때마다 해당 객체의 레퍼런스 카운트가 1 감소합니다. 레퍼런스 카운트가 0이 되면 객체는 더 이상 참조되지 않으므로 메모리에서 해제된다.

ARC는 strong reference, weak reference, unowned reference 세 가지 타입의 레퍼런스를 사용한다.

1. Strong Reference
기본적으로 모든 레퍼런스는 strong reference이다. strong reference는 참조된 객체의 레퍼런스 카운트를 증가시키므로, 객체는 참조되는 동안 메모리에서 해제되지 않는다.

2. Weak Reference
참조된 객체의 레퍼런스 카운트를 증가시키지 않는다. weak reference를 사용하면 순환 참조(circular reference)를 방지할 수 있다. 순환 참조는 객체들이 서로를 강한 참조하고 있어 해제되지 않는 상황을 말한다. weak reference는 객체가 해제되면 자동으로 nil로 설정된다.

3. Unowned Reference
unowned reference는 참조된 객체의 레퍼런스 카운트를 증가시키지 않으며, 참조된 객체가 해제되어도 자동으로 nil로 설정되지 않는다. unowned reference는 참조되는 객체가 항상 유효한 경우에만 사용해야 한다. 그렇지 않을 경우, 참조된 객체가 해제된 상태에서 접근하게 되어 런타임 오류가 발생한다.
