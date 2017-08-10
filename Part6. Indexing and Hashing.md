indexing을 통해 원하는 데이터를 빠르게 접근할 수 있다.  
index 파일은 __search-key + pointer__ 의 형태인 record(index entry)로 이루어져 있다.  
index의 두 종류에는 _1. ordered indices_ 와 _2. hash indices_ 가 있다.  
1. ordered indices: search key들이 sort된 순서로 저장되어 있다.  
2. hash indices: hash function을 이용하여 buckets에 균등하게 분배되어 있다.  

_search key는 file에서 레코드를 찾는데 사용되는 attribute(s)이다._  


### ordered indices  
: index entries가 search-key value 순으로 저장되어 있다.  
ex) B+ Tree, B Tree  

* primary index(= clustering index): search-key의 index 순서대로 저장되어 있다.  
primary index의 search key는 보통 primary key이다.  
  - index-sequential file: record(tuple)저장 순서가 primary index 순서  
  - dense index file: index entry가 모든 tuple에 대해 하나씩 다 존재한다.    
  - sparse index file: 모든 tuple에 대해 index entry가 존재하지 않는다. - search-key에 대해 순차적으로 record가 있어야 한다.(_sort가 되어있어야 함!_)    
* multilevel index: primary index가 메모리에 안 맞을 때  
* secondary index(= non-clustering index): 순차적으로 저장되어 있지 않다.  
  - 무조건 dense index이다.  

### hashing indices  
hash index는 record pointer와 같이 search key로 구성된다.  
hash indices는 항상 secondary indices이다.  
### static hashing
* bucket: 1개 이상의 record가 있는 저장 단위로 대게 disk block이다.  
hash function을 이용하여 bucket을 나눌 수 있다.  
- Worst case: 모든 search-key 값이 같은 bucket으로 들어갈 때 -> _bucket overflow가 발생할 수 있다._    
- Ideal case: uniform하고 random하게 나뉘어질 때  


* bucket overflow를 줄이기 위해 __overflow bucket__ 을 쓴다. -> overflow chaining (linked list를 이용하여 연결된다.)  

### Dynamic hashing
Extensible hashing - 다이나믹 해싱의 한 형태로 bucket 수가 다이나믹하게 바뀐다.  

~~~~~~~~~ 수정 및 추가 환영 ~~~~~~~~~  
