# Kotlin
## 변수와 상수
* var:읽기와 쓰기가 둘다되는 변수
* val:읽기만 되는 변수
* 변수선언 방식:   
var 변수이름(:변수의타입)=변수에 넣을 값   
-변수에 넣을 값의 타입에 따라서 자동으로 타입 지정 가능
## 조건문
* 변수에 조건문의 결과를 저장할수 있다   
(예: var result= 1>2)
* 문자열의 길이로도 조건문을 만들수 있다   
(예:var result="홍길">"홍길동")
* 자바처럼 if,if else문을 사용할수 있다
* __when:__ switch case문 대신 사용함   
```kotlin
when(result){   
    1->{
        실행코드
    }(1일때 실행)   
    2,3->{
        실행코드 1
    }(2혹은3일때 실행)   
    in 5..9{
        실행코드3
    }(5부터 9사이일때 실행)
```
## 배열&컬렉션
* 배열:미리 정해둔 개수 만큼 자료들을 넣을수있음  
```kotlin 
var intArray:IntArray=IntArray(40)
```
* 다른 언어의 배열처럼 0번방부터 시작
* 리스트: 배열과 같이 미리 공간을 정해두고 사용
* var intArray=intArrayOf(1,2,3...)으로 미리 값을 넣어둘수있음
* 리스트 사용법: 
```kotlin
var list=Listof<Int>(10)
```
### 컬렉션
* __뮤터블리스트__ :동적으로 공간을 지정해서 사용자가 넣는만큼 사용

* 뮤터블 리스트 사용법:   
var mutableList=MutavleListof<Int>()   
<>안에 넣을값의 자료형을 적음 __(Generic)__
* 리스트 값 관리
1. 값 추가방법:mutableList.add(값)
2. 값 접근방법:mutableList.get(방번호)
3. 값 삭제방법:mutableList.removeAt(방번호)

* __맵__ : 인덱스가 아니라 __키(key)__ 로 접근하는 컬렉션
1. 선언: var mutableMap=mutableMapOf<String,String>()
2. 추가:mutableMap.put("키값",값)
3. 접근:mutableMap.get("키값")
4. 수정:mutableMap.put("수정할 키값",값) 
5. 삭제:mutableMap.remove("키값")

* __Set__ : __반복되는 값 없이__ 저장해두는것 
1. 선언방법:var set=mutableSetOf<String>()
2. 사용방법:set.add("JAN")...(동일한값은 입력되지 않음)
3. set은 인덱스를 사용할수 없다(값으로 조회가능)
## 반복문
* __for__:for()에서 괄호안에 조건문을 넣음   
(예: for(변수 in 1..100){
실행코드
})-변수는 자동으로 1씩 올라간다
* __until__:for(변수 in 1 until 100)에서 100은 포함하지않음
* __step__:for(변수 in 1 until 100 step 2)에서 2씩 건너뛰면서 실행
* __downto__:for(변수 in 100 downTo 1)에서 100부터 줄어들면서 실행
* for(value in intArray)는 intArray의 요소개수만큼 반복함, value에는 intArray의 요소값이 들어감
* while문도 사용가능(예:while(조건문){실행코드})
* __do While__:(예: do{
    실행코드
}while)- do를 한번 하고나서 while로 반복할지 확인
* continue,break 사용가능(continue:반복문 처음으로 돌아감)
## 합수
* 함수: fun 함수이름() (:리턴값의 자료형){}
* 매게변수넣기:fun 함수이름(이름:자료형):리턴값의 자료형{}
## 클래스
* 프로퍼티와 메서드의 모음
* __프로퍼티__:클래스 상위에있는 변수
* __메서드__: 클래스에 있는 함수
### 클래스 사용
* __클래스 사용__: var 변수=클래스()
* __init{}__: 클래스를 초기화(메모리에 로드)하는 함수(클래스를 호출하면 초기화)
* __constructor__:생성자처럼 사용이 가능하지만 java처럼 초기화 되지는 않음
* 프로퍼티,메서드 사용법: var 변수=클래스()   
변수.메서드, 변수.프로퍼티
* companion object: 이걸로 감싸면 초기화 하지 않고도 사용가능
### 상속
* 상속의 이유1:기존의 크드를 재활용하기위함
* 이유2:코드를 체계적으로 계층구조화해서 사용하기위함
* 하는법: 1.부모클래스 앞에 __open__을 붙여줌   
2.상속할 자식클래스: class child:Parent(){

}
* __override__: 상속받은 프로퍼티나 메서드를 덮어쓰기   
부모클래스의 메서드,프로퍼티에 open붙여줌   
자식 클래서에서 override를 앞에 붙여서 사용
* __overload__: 같은 이름의 메서드를 매게변수의 형태를 다르게해서 접근할수 있는것