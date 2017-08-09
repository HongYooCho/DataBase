### DataBase 특징
* 데이터 중복&불일치 문제가 없다. (no redundancy & inconsistency and no isolation)  
  - 정보 수정시 한 번만 수정하면 되며 여러 곳에 정보가 있을 때 똑같이 수정된다.  
* 데이터 접근이 쉽다. (easy to access)  
* 새로운 제약이 생기거나 이미 있는 제약을 바꿀 때 추가하기 쉽다. (integrity)  
* atomicity (원자성)  
  - 송금/입금이 쪼개져서 실행되면 안 된다. 둘 다 되거나 둘 다 안되거나 해야 한다.  
* 여러 명이 동시에 접근할 수 있다. (concurrent access)  

### Schema and Instance
* __Logical Schema__: high level schema로 디비의 전반적인 로지컬 구조  
* __Physical Schema__: low level schema. 파일, 하드디스크에 어떻게 저장할 건지?  
* __Instance__: 실제로 데이터가 들어가있는 특정 상태.  
* __Physical data independence__: 로지컬 스키마가 바뀌든 피지컬 스키마가 바뀌든 데이터 저장되는 방식이 바뀌어도 __데이터는 그대로 "유지"되어야 한다.__  

__데이터 모델__ 에서는 데이터, 데이터 relationships, 데이터 semantic, 데이터 제약조건들을 어떻게 표현할지 정의하는 도구이다.  
전세계적으로 relational model(70%)를 사용한다. - 예전부터 웬만하면 바뀌지 않음.  


### Data Definition Language (DDL)  
table 형식을 정한다. 실제 데이터는 들어가지 않지만 틀이 생긴다.  
__data dictionary__: 테이블의 구성, 구조 정보(metadate: data의 data)를 저장한다.  
* 데이터베이스 스키마(table schemas)  
* integrity constraints: primary key - 특정 object를 유일하게 가리킬 수 있는 정보    
* authorization: 데이터에 접근할 수 있는 사람  

<pre><code>
CREATE TABLE DEPARTMENT
    DEPT_NAME     CHAR(20),
    BUILDING      CHAR(15),
    BUDGET        NUMERIC(12, 2);
</code></pre>  

### Data Manipulation Language (DML)  _(= query language)_  
data 저장/검색에 사용된다.  
declarative (non-procedural) 언어이다.  
<pre><code>
SELECT  INSTRUCTOR.ID, DEPARTMENT.DEPT_NAME
FROM    INSTRUCTOR, DEPARTMENT
WHERE   INSTRUCTOR.DEPT_NAME = DEPARTMENT.DEPT_NAME AND
            DEPARTMENT.BUDGET > 95000;
</code></pre>  

### Structured Query Language (SQL)  
DDL과 DML을 아우르는 스테이트먼트. 데이터베이스에 어떤 작업을 할 때 사용하는 언어이다.  

### Query Processing  
Query Processor  
: query 가 들어오면 어떻게 찾으면 좋을지 판단하여 결과를 주는 것. 질의 처리기  
- Parsing and translation: compile  
- Optimization: 쿼리 프로세싱 최적화(제일 빠르게)하기  
- Evaluation: 데이터 실제로 읽어와 전달    
![Query Processing](https://github.com/HongYooCho/DataBase/blob/master/image/Part1.%20Intro/queryprocessing.png)

### Transaction  
한 트랜잭션은 여러 sql로 이루어져 있는데 all done 이거나 never done이어야 한다. partially done은 안됨!!!!!!  
