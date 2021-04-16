## 추상클래스 vs. 인터페이스

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

int, long, float, double, boolean, char ...  

new로 객체생성 불가



## String vs. StringBuffer

StringBuffer

- 객체 단 한번 생성
- 값변경가능
- 메모리 사용량 많고 속도 느림.

String 

- +연산시, 새로운 객체 생성

- 생성 후 값변경 불가능 == immutable

- 문자열 변경 메서드 : 새로운 객체를 생성하여 리턴

  

## 배열 vs. Vector vs. ArrayList

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

## HashMap

map interface의 한종류, key 중복불가, value는 가능(null key1, value 여러개)

정렬 X

멀티쓰래드는 hashmap X →hashTable

동작원리?

hashcode메서드로 key, value모두 버킷에 저장

동일한 hashcode가질 경우?

Object class : equals(), hascode() 메서드 가짐

equals, hashcode contract

- 두객체 같으면, 반드시 동일한 hashcode
- hashcode같다고해서, 동일한 객체 X
- equals재정의시, hashcode도 재정의
- equals 비교시 사용되지않는 필드 - hashcode메서드에서 사용하면 안됨.

서로다른 객체의 hashcode가 동일할 경우?

버킷위치 찾고, 버킷내 연결리스트에서 keys.equals()로 맞는값 찾기.

hashmap 크기가 적재인수 보다 더 많은 객체를 담을 경우?

임계점 도달시, hashmap크기 재조정. → 2배 새 버킷생성 & 넣기 : rehashing



## TreeMap

key 기준 정렬(binary search tree)



## HashTable

null값 안됨

동기화 지원 but ConcurrentHashMap 사용권장

반환값 (https://odol87.tistory.com/3)

검색 : HashTable < TreeMap < HashMap

정렬 : HashMap < TreeMap