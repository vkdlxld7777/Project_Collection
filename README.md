# AI_12_이대웅_Section1,2 프로젝트

### 프로젝트 개요
+ 개인방송의 게임 광고효과에 대해 집계를 하고자 게임 이용율과 해당 게임 방송시간의 연관관계를 찾고자함

+ 가설
  + 전체방송의 시간과 해당게임의 인기가 

### 데이터셋
##### Twitch_Hours_watched : 시청시간
##### Twitch_Hours_Streamed : 스트리밍 시간
##### Twich_Peak_viewers : 제일 많이 본 시청자 수
##### Twitch_Peak_channels : 제일 많이 한 방송 수
##### Twitch_Streamers : 전체 방송 수
##### Twitch_Avg_viewers : 전체 시청자 수 평균
##### Twitch_Avg_Channels : 전체 방송 수 평균


### 결과정리
+ heatmap을 통한 연관관계
![image](https://user-images.githubusercontent.com/74826174/189703392-f8fa8d2a-dd80-4e09-b407-5212dc5b3f66.png)
+ basemodel : XGBRegressor -> 정확성 : 0.5976943850788301
+ RandomForestRegressor -> 정확성 : 0.8905392340377372
+ 특성 중요도
![image](https://user-images.githubusercontent.com/74826174/189703528-f96e7345-aa6c-4a7d-b5ea-845346893f1d.png)

+ 테스트 데이터(리그오브레전드)
![image](https://user-images.githubusercontent.com/74826174/189703724-f8bc9e4d-d328-4d11-b639-fd281f8f9ac2.png)

Positive 영향을 가장 많이 주는 3가지 요인 입니다:
1. Twitch_Avg_viewers : 127021
2. Twitch_Hours_watched : 94377226
3. Twitch_Hours_Streamed : 1362044


Negative 영향을 가장 많이 주는 3가지 요인 입니다:
1. Twitch_Peak_channels : 2903
2. Twitch_Streamers : 129172
3. Twitch_Avg_channels : 1833

###문제점 및 개선방안
+ 최신데이터가 없기에 정확한 측정이 불가능하였고 특히 가장중요한 신규게임의 광고에 대한 방송 데이터가 없어 평가 데이터의 신뢰성이 떨어짐.
+ 트위치에서의 각 방송의 시청시간 및 시청인원의 데이터를 더이상 지원하지 않아 직접적인 데이터 수급을 하지 못하였음.
+ 트위치 방송에서는 신규게임이 나오면 광고로 다양한 스트리머에게 의뢰를 맡기는데 1주에서 2주가량의 광고가 달린 게임 데이터와 해당게임의 구입 데이터가 있다면 정확한 데이터 집계가 가능할 것으로 보임
