# CombineWithSwiftUI
Udemy The Complete Guide to Combine Framework in iOS Using Swift 강좌를 듣고 <br/>
SwfitUI에서 Combine을 사용해 MVVM 구현을 연습할 레포

참고 블로그: https://inuplace.tistory.com/


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
- Publisher와 Subscriber의 flow(이하 S와 P)
> 1. S가 P를 구독
> 2. P가 구독을 허락함
> 3. S가 값을 요청
> 4. P가 값을 보내줌
> 5. P가 completion을 보냄
- Subscriber의 구현
> Subscription 이라는 구독을 대변하는 객체가 있다. Subscribe 받음을 처리하는 recieve 함수를 만듦. 이때 backPressure(얼마만큼의 item을 전달받고 싶을지)를 설정할 수 있음.
> 실제로 값을 받을 recieve 함수도 만듦. 리턴값으로 backPressure를 변경할지 반환해야함
> Publisher가 일을 끝내면 Subscriber가 completion을 받음. 이때 쓸 receive 함수도 구현
- Subjects
> Subjects는 Subscriber일 수도 있고 Publisher가 될 수 있다

- Type Eraser
> combine 프레임워크와는 관련이 없고 swift 언어와 상관이 있음.
> TE는 실제로 타입을 지우는 것이 아닌 다른 타입 뒤에 숨기는 것을 말함.
> 아직 자세한 내용은 이해 못하게씀 ..


## Chpater2
- Transformation Operators
> 예를들어 [1,2,3] 같은 시퀀스가 있다고 하면 Transformation Operator를 거치면 ["one", "two", "three"] 같이 완전히 다른 시퀀스로 바꿀 수 있음
### collect()
> finish 될 때 까지 모든 이벤트를 모아줌. 
> 갯수에 한계치가 없으므로 메모리 관리에 주의할 것.
> 인자값에 숫자가 들어가면 그 갯수만큼 이벤트를 전달한다. ex) [a,b,c,d,e].publisher.collect(2).sink  --> [a,b], [c,d], [e]

### map()
> 일반적인 swift의 map과 같다. 모든 이벤트에 같은 변화를 주는 기능을 함.
> map(keyPath) 는 특정 키에만 maping 한다고 생각하면 됨.
// 까지 편집 완료 23.1.25.2시 
https://www.udemy.com/course/the-complete-guide-to-combine-framework-in-ios-using-swift/learn/lecture/15970500#overview

## Chapter 12
- MVC 디자인 패턴이란?
> Model Veiw Controller로 이루어진 패턴
> Model 은 Data 다. 
> View는 인터페이스다.
> Controller는 모델과 뷰 사이. 모델과 뷰는 직접적으로 연결되면 안됨.  
- MVC의 문제
> MVC를 하면 컨트롤러에 너무 많은 코드가 들어간다는 단점이 있다.
> 거대해진 컨트롤러는 테스트 하기 힘들다.
- MVVM 디자인 패턴이란?
> 뷰와 모델을 분리해줄 수 있는 패턴
> View -> 인터페이스
> ViewModel -> 뷰가 뷰 모델에 연결은 되지만 모델에는 연결되면 안됨. 뷰 모델만 모델과 연결 가능.
> Model
// 까지 편집 완료 23.1.26 2시 
https://www.udemy.com/course/the-complete-guide-to-combine-framework-in-ios-using-swift/learn/lecture/15970500#overview
