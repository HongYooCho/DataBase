관계형 모델. 관계형 데이터베이스.  
### Relational DB 구조
* __tuples__ (=rows, records)  
* __attributes__ (=columns, fields): 한 가지 타입의 값을 갖는다. 이 값은 *atomic* 해야 한다.    
* 특정 column에 모든 가능한 집합을 __domain__ 이라고 한다.  

### Keys  
* superkey: relation에서 tuple을 구별할 수 있는 값들.  
* candidate key: superkey가 최소한의 key로 이루어진 경우. candidate key에서 하나의 key라도 없을 경우 key역할을 못한다.  
* __primary key__: candidate key 중 하나.
* __foreign key__: 현재 테이블(relation)의 키가 아닌 다른 테이블의 키  

#### Relational Query Languages  
SQL, Relational algebra, Tuple relational calculus, Domain relational calculus는 __non-procedural (declarative) 언어__ 이다.  

### Relational Operations  
* select: selection of rows(tuples)  
* project: selection of columns(attributes)  
* union: 합집합  
* difference: 차집합  
* intersection: 교집합  
* join  
  - __cartesian product__ (rxs)  
  - __natural join__ (r⋈s)  
