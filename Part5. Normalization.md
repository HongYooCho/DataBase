## Normarlization (정규화)
: 관계형 DB에서 중복을 최소화하기 위해 데이터를 구조화하는 작업  
하지만 실무에서는 대규모 데이터 처리시 성능(Performance)향상을 위해 정규화를 안쓰거나 낮은 수준의 정규화를 만족하는 경우가 많다.  

### 함수 종속 (FD: Functional Dependency)  
`R: relation` `X, Y: R의 attribute 집합의 부분집합`  
X의 값 각각에 대해 Y의 값이 항상 오직 하나만 연관되어 있을 때 __Y는 X의 함수 종속(FD)__ 라고 하며 __X→Y__ 로 표기한다.  
--> X: 결정자(determinant), Y: 종속자(dependent)  
_그렇다고 X가 반드시 R의 candidate key가 되어야 하는 것은 아니다._

### Closure (F+)
FD 집합 F가 주어졌을 때, F를 통해 __논리적으로 암시 가능한 다른 FD__ 를 F의 closure라고 한다. F+라고 쓴다.  
ex) A→B와 B→C를 통해 A→C 유추가 가능하다. -> __F+ (A→B, B→C, A→C)__  

### 1NF (First Normal Form)
: 행과 열의 순서에 영향을 받지 않으며(scalar) 모든 항목에 값이 있어야 한다.(null 허용 안됨). 중복되는 열이 없어야 한다.(__atomic -> composite, derived attribute 안됨!!!!!__)  
#### --> 중복되는 데이터를 분리한다.
<p>

### 2NF (Second Normal Form)  
: relation R이 1NF이고 primary key에 속하지 않는 모든 attribute가 primary key에 __완전 함수 종속(FD)일 때__.    
#### --> 부분 종속일 경우 분리한다.
<p><p>

### 3NF (Third Normal Form)  
: 이행적 함수 종속(transitive FD)이 있을 경우 테이블을 쪼갠다. 다른 열의 값을 계산해서 얻을 수 있는 열은 제거한다.  
__모든 결정자(determinant)가 candidate key__ 이면 R은 3NF이다.  
relation R이 2NF이고 primary key에 속하지 않는 모든 attribute가 primary key에 __이행적 함수 종속(transitive FD)이 아닐 때__.  
#### --> 이행적 종속 관계 분리한다.  
_transitive FD란? A→B와 B→C가 성립되면 A→C도 성립한다. 이 때 C는 A에 transitive FD이라고 한다._  
_transitive FD 제거하기: A→B AND B→C, THEN A→C_  
_{A, B, C} --> {A, B}, {B, C}_   
<p><p>

### BCNF (Boyce-Codd Normal Form)
: __모든 결정자(determinant)가 superkey__ 이면 R은 BCNF이다.  
BCNF에 속하는 relation은 모두 3NF이다. -> BCNF는 강한 3NF이다.    
하지만 1NF, 2NF, primary key, transitive FD 등 개념을 이용하지 않고 정의되기 때문에 3NF보다 간단하다. 복합속성 허용한다.  
<p><p>


```
아무나......내용 추가해주세요....... 틀린 부분/애매한 부분도 수정 부탁..........
어려운 정규화ㅠㅠ
```

__References__  
[DB 정규화](http://blog.naver.com/PostView.nhn?blogId=force44&logNo=130100972038)  
[데이터 종속성과 정규화 ](http://beansberries.tistory.com/entry/%EB%8D%B0%EC%9D%B4%ED%84%B0-%EC%A2%85%EC%86%8D%EC%84%B1%EA%B3%BC-%EC%A0%95%EA%B7%9C%ED%99%94)
