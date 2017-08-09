## SQL(Structured Query Language) - DDL & DML
### * DDL(Data Definition Language): 데이터 정의  
  - relation *schema* 를 정의한다. (create table ~)  
  - 각 attribute가 무슨 type인지 *domain* 정의 (char, varchar, int, numeric, ..)
  - *integrity constraints* (결점없기 위한 만족 조건 정보)  
    * not null
    * primary key (A)
    * foreign key (A) references (r)
### * DML(Data Manipulation Language): 데이터 처리, 검색, 접근 작업 _(= Query)_    
* SELECT, WHERE, FROM clause  
: __select__ * __from__ instructor __where__ department="Computer Science";  
_참고로 WHERE절 없이 FROM까지만 쓰면 Cartesian product이다.__
* JOIN, NATURAL JOIN  

### Views
: 어떤 유저에게서 특정 데이터를 감추기위한 메커니즘이다.  
* view는 select문을 string으로 저장한다. -> 보안문제 해결가능!  
ex. 교수의 id, 이름, 부서에 접근할 수는 있지만 salary에 대한 정보는 접근할 수 없다.  

__[Definition]__ `CREATE VIEW v AS <query expression>`  
v: view 이름 <query expression>: SQL문  


* view update (insert, delete, update)는 안 되는 경우가 있다.  
-> integrity constraints 때문에 발생한다.  

ex)
<pre><code>
CREATE VIEW instructor_info AS
SELECT ID, name, building
FROM instructor, department
WHERE instructor.dept_name = department.dept_name;
</code></pre>
-> 여기서 INSERT INTO instructor_info values('69987, 'White', 'Taylor');를 할 경우  
1. instructor에 insert할지 department에 insert할지 모른다.  
2. dept_name에 대해 join을 했는데 insert 에는 dept_name 정보가 없다.  

#### view update 잘 되는 경우
1. view 정의시 from절에 table이 하나일 경우
2. select절에 attribute 이름만 있을 때(연산(SUM, MAX, ..)이나 DISTINCT 없는 경우)
3. attribute 값에 NULL, DEFAULT 값이 들어갈 수 있는 경우  
4. group by 하지 않은 경우 (group by하면 SUM, MAX, DISTINCT 처럼 대표값이 설정되어 유니크하게 매칭되지 않는다.)

### Transaction
반드시 atomic 해야 한다.  
