# CombineWithSwiftUI
Udemy The Complete Guide to Combine Framework in iOS Using Swift 강좌를 듣고 <br/>
SwfitUI에서 Combine을 사용해 MVVM 구현을 연습할 레포



## Chapter1
- 함수형 프로그래밍이란?
>  함수형 프로그래밍 내에서 생성하는 변수는 일정해야하며 변경할 수 없다. 따라서 함수형 프로그래밍에서는 변수의 상태를 변경할 수 없다.
>  객체지향 프로그래밍과는 상대되는 개념. 
>  변경할 수 있는 상태란 누구나 값을 변경할 수 있음을 의미함. -> 동시성이슈, Race Conditions, Deadlock 등이 발생할 수 있다.
>  함수형 프로그램에는 Deadlock도 발생하지 않고 동시성 의존성이 없다.
>  <br/>
>  함수형 프로그래밍은 **first class와 highter order Function** 의 개념도 갖고 있다.  다른 함수를 취하고 반환할 수 있다는 뜻인데 
>  필터와 맵을 사용하는 다양한 예들이 있다.<br/>
>  함수 프로그래밍은 pure functions이라는 것을 뜻하기도 한다. 이는 동일 입력 동일 출력을 의미한다. 이는 외부에 부작용을 전혀 만들지 않는 것을 의미한다.
### MVVM 과 Combine (언제 Combine을 사용해야하는가)

>  Combine 을 채택하면 이벤트 처리 코드를 중앙 집중화하고 중첩 클로저 및 규칙 기반 콜백과 같은 번거로운 기술을 제거하여 코드를 더 쉽게 읽고 유지 관리할 수 있다. 


## Chpater2
- Publisher, Subsciber, Operator
> Publisher 와 Subscriber 가 구독 관계로 이어지면 데이터를 보낼 수 있게 된다.(stream of data)
> 예시(Netflix) 사용자가 Netfilx를 구독하면 Netfilx에서 새로운 영화를 추가할 때 구독에 따라 다양한 영화를 볼 수 있게 됨.

// 까지 편집 완료 23.1.17.2시 
https://www.udemy.com/course/the-complete-guide-to-combine-framework-in-ios-using-swift/learn/lecture/15710566#overview

- Combine 프레임워크란?
   
- Combine VS RxSwift
