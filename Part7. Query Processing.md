![Query Processing](https://github.com/HongYooCho/DataBase/blob/master/image/Part1.%20Intro/queryprocessing.png)  
1. Parsing and translation  
  - Parsing: 구문 분석  
  - Translation: sql문장을 db 시스템의 내부표현으로 바꿔주기 (execution plan = evaluation plan)  
2. Optimization  
  - translation 결과를 최소의 시간이 걸리는 것으로 찾아내기  
3. Evaluation  
  - sql문 실제로 실행하기  


### Query Optimization  
결과는 같을지라도 속도나 메모리 차지하는 정도(cost)는 다르다.  
통계정보(ex. table row 개수, 특정 attribute 가진 row 개수, attribute 분포 등)을이용해서 query optimization을 진행한다.  


### Sorting  
DB에서는 데이터가 많아(메모리에 맞지 않아) 일반적으로 external sorting(disk를 이용한 sorting)을 말한다.  
* external sort-merge  

### Join Operation  
* nested-loop join  
* block nested-loop join  
* indexed nested-loop join  
* merge-join  
* hash-join  


~~~~~~~~~ 수정 및 추가 환영 ~~~~~~~~~  
