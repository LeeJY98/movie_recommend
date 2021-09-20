# movie_recommend
#### 영화 추천 시스템 만들기 _ 동국대 하얀집 팀(강협, 이지영, 윤영채, 이시은) 
-------------------------------------
### 주제 선정의 이유
> IMDB 데이터를 활용하여 영화를 보고 남긴 평점, 리뷰 등을 토대로한 영화 추천 시스템을 만들어보자는 취지였다. 넷플릭스와 유튜브와 같은 추천시스템에 영감을 받아 우선 IMDB 데이터로 간단한 추천 시스템을 만들고자 하였다. 
### 시스템을 구축하기 위한 단계
---------------------------------------------
#### 1. 추천 시스템 선정
+ Contents Based Filtering(CBF) 와 Collaborative Filtering(CF) 중 CF 선택
> 콘텐츠간의 유사도를 기반으로하여 추천을 결정하는 알고리즘인 Contents Based 
Filtering 을 사용할 것을 고려하였으나 사용자 데이터를 반영하지 않고 콘텐츠 내부에서만 결정하는 한계가 존재함. 따라서 사용자 데이터를 반영하는 CF 방식을 사용
#### 2. CF 적용 프로세스
+ 사용한 데이터 (movie.csv / ratings.csv)
![image](https://user-images.githubusercontent.com/79441145/134026892-0d65f046-4384-494d-9348-ed6b7793257f.png)
![image](https://user-images.githubusercontent.com/79441145/134026990-df53b10c-9da2-4f3f-bd6a-bd2d71a65749.png)
+ 데이터 전처리 (불필요한 데이터의 삭제 및 데이터 합병)
  + ratings.csv의 colums 중 timestamp가 추천 시스템에 부적합한 데이터이므로 삭제
  + ratings.csv와 movies.csv 의 합병
  + pivot table 생성 후 NaN의 값을 가진 데이터는 null값으로 채우기
+ 추천 지수 출력
  + 코사인 유사도 분석을 통해 1 에 가까운 값을 가진 영화 순으로 추천
#### 3. 결론
+ 1번 영화(id)를 좋아한 사람은 1번 영화와 유사도가 높은 3114, 260, 356등의 영화를 좋아한다는 결론이 내려짐.
![image](https://user-images.githubusercontent.com/79441145/134028880-d8c08c31-1db6-4162-a2e0-de2f335ca47d.png)

### 추가보완 
--------------------------------------
+ 새로운 user를 input으로 넣어서 이 user에게 해당하는 추천 영화 리스트를 반환하는 코드를 추가함.
 
