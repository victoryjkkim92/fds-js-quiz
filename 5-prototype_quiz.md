## [금요일아침 퀴즈 _ prototype](https://repl.it/@victoryjkkim92/prototype-quiz)





#TIL

1번 문제 접근 방법

* 공통으로 사용할 속성이 들어있는(메소드 등) prototype이라는 객체를 생성함

* 그것을 사용할 배열을 선언! object.create(만들어놓은 prototype)를 해서 그 안에 있는 속성들을 사용할 수 있게 해줌

* 그리고 `.` 을 이용해서 속성에 접근

2번 문제 접근 방법

* 생성자 함수를 만듬

* 생성자 함수에 메소드를 프로토타입으로 지정

* 인스턴스를 만들어 원하는 값 얻어냄!
