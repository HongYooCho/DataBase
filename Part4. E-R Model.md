
### Entity-Relationship Model (E-R Model)  
: entity(attribute 집합, object)와 relationship(entity들 사이 association)으로 이루어져 있다.  

### Mapping cardinality constraints
binary relationship set에서 mapping cardinality가 있다.  

`화살표 선 directed line(→): one`  
`직선 undirected line(—): many`

* one-to-one  
![one-to-one relationship](https://github.com/HongYooCho/DataBase/blob/master/image/Part4.%20E-R%20Model/one-to-one.png)
* one-to-many, many-to-one  
![one-to-many relationship](https://github.com/HongYooCho/DataBase/blob/master/image/Part4.%20E-R%20Model/one-to-many.PNG)
* many-to-many  
![many-to-many relationship](https://github.com/HongYooCho/DataBase/blob/master/image/Part4.%20E-R%20Model/many-to-many.png)

#### Total and partial participation
* total participation (두 줄로 표시)  
entity set내의 모든 entity가 relationship에 참여해야 한다.  
* Partial participation (한 줄로 표시. default)  

ex) 지도학생(total)이 없는 교수(partial)도 있다.  
![total-and-partial](https://github.com/HongYooCho/DataBase/blob/master/image/Part4.%20E-R%20Model/total-partial.PNG)  

### Weak entity set
![weak-entity-set](https://github.com/HongYooCho/DataBase/blob/master/image/Part4.%20E-R%20Model/weak-entity.png)  
중복된 attribute가 제거된 entity set을 weak entity set이라고 한다.  
weak entity set은 혼자서는 불충분하기 때문에 무조건 total participation이 되어야 한다.  
-> 자기가 dependent한 __strong entity set__ 의 primary key와 자기가 갖고 있는 partial key (__discriminator__)가 합쳐져야 한다!  
--> 따라서 weak entity set는 dependent한 strong entity set(=indentifying entity set)이 반드시 하나는 존재한다.   
_Weak entity set는 Existence dependent하다. weak와 strong 사이의 Relationship을 identifying relationship이라고 한다. _  
