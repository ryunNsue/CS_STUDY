## 추상클래스 vs. 인터페이스

---

### 추상클래스(Abstract Class)

- 하나 이상의 구현 안된 메서드 존재 -> 인스턴스화 할수 없는 클래스
- extends, 다중상속 불가
- final외의 변수도 가능
- 일반 클래스와 동일한 멤버유형 가능

### 인터페이스(Interface)

- 구현안된 메서드만 존재하는 클래스

- Implements, 다중가능

- 변수: 기본 final

- public 멤버

  

## Primitive 자료형

---

int, long, float, double, boolean, char ...  

new로 객체생성 불가



## String vs. StringBuffer

---

StringBuffer

- 객체 단 한번 생성
- 값변경가능
- 메모리 사용량 많고 속도 느림.

String 

- +연산시, 새로운 객체 생성

- 생성 후 값변경 불가능 == immutable

- 문자열 변경 메서드 : 새로운 객체를 생성하여 리턴

  

## 배열 vs. Vector vs. ArrayList

---

### 배열 

- 크기 고정, 크기 변경불가
- 연속된 메모리공간
- 빈공간 생길 수 있음
- Index로 원소접근 가능 (O(1))

### List

- 크기 유연, 동적 크기

- 불연속 메모리공간, 포인터를 통한 접근

- 빈공간 없음

- 삽입,삭제에 용이

  #### ArrayList

  인덱스로 객체 관리, 동적크키 (1.5배). 

  데이터 추가 삭제시, 모두 이동

  #### LinkedList

  노드간 연결, 인덱스 없음(순차접근)

  #### Vector

  ArrayList와 동일 내부구조 (2배 증가)

  차이점 : 동기화, Thread Safe -> 느림

어떤 경우에 무엇이 유리?

[참고](https://velog.io/@adam2/Array와-List그리고-Java-List)