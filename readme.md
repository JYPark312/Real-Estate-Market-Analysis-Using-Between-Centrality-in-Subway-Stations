# 지하철 역의 between centrality를 이용한 부동산 시세 분석

## 연구 배경
- 사람들은 대부분 교통이 편한 곳에 거주하려 함
- 지하철 노선도를 중심으로 교통이 편한 곳은 환승역 
- 환승역 부근의 원룸 가격은 많은 수요로 인해 가격이 높음
- 환승역외에 교통이 편리한 역을 선정
- 지하철 노선도를 네트워크로 변환해 between centrality가 높은 역을 기준으로 부동산 가격 분석

## Between centrality
- 네트워크 내에서 한 노드가 다른 노드들 사이에 위치하는 정도를 나타내는 지표
- 내트워크 내에서 어디에 위치하는지를 파악함으로써 해당  노드의 영향력을 파악할 수 있음 
- between centrality가 높은 노드는 중재자 역할을 수행하게 되며 핵심노드로 기능할 가능성이 높음

## 데이터 수집 
### 지하철 노선도를 엑셀 파일로 직접 변환 (경기도권 제외)

![image](https://user-images.githubusercontent.com/70933580/166194251-5b255235-ba27-4aaf-837a-7ea035878499.png)
![image](https://user-images.githubusercontent.com/70933580/166194264-8dd44366-9b82-4128-b29e-af1e31272573.png)

## 데이터 분석
### 지하철 노선도 network matrix로 변환 

![image](https://user-images.githubusercontent.com/70933580/166195831-585df105-d606-43cf-a6f2-ba223b3f7cfa.png)

### network 분석
- 483개의 노드
- 평균 degree 2.27
- centralization 0.0098
- density 0.00471
- avg distance 19

![image](https://user-images.githubusercontent.com/70933580/166194777-c9ecc788-29c1-4fc1-b74c-7c03226a9071.png)

### visualization(netdraw)
![image](https://user-images.githubusercontent.com/70933580/166198667-e520d4a5-af7c-4855-8692-22380bb9e59a.png)

### Degree & centrality
- Degree가 높고 centrality가 높은 역은 분석 대상에서 제외
- Degree는 높지 않지만 between centrality가 높은 역 선정(degree: 2, 3/ between centrality top 30)
- 구로, 대방, 광운대
- 원룸: 전용 면적 17~33 m^2(약 5~9평), 월세, 보증금 1천만원 이하, 반지하 제외, 선정 역 외에 다른 역과 가깝지 않은 곳

![image](https://user-images.githubusercontent.com/70933580/166194847-cab57912-5a09-4fdc-a1f8-ca6e709ead23.png)
![image](https://user-images.githubusercontent.com/70933580/166195345-f4e3979b-7026-4519-92c3-a732111a580c.png)

### 시세 비교
- 왕십리역(degree top 1, between centrality top 1)

![image](https://user-images.githubusercontent.com/70933580/166195759-ab678ab3-cfb9-4bef-bb6a-18b2c91803af.png)
  - 지하철 역과 가까울 수록 가격이 비싸짐
  - 18m^2 기준 1000/50, 관리비 5만원 이상의 가격대

- 구로역 

![image](https://user-images.githubusercontent.com/70933580/166196249-d580dd7e-45bf-4f0a-bbb0-ddb417ba767c.png)
  - 31m^2 기준 500/50, 관리비 5만원 이상
  - 신도림역(1호선)과 가까움
  - 과거 치안에 대한 부정적인 인식이 있었음
  - 영등포, 디지털 단지 직장인이 고려하면 좋을 위치

- 대방역

![image](https://user-images.githubusercontent.com/70933580/166196768-2e7df854-0f72-4a06-b73e-209fb09a1bc5.png)
  - 19m^2 기준 500/50, 관리비 5만원 이상
  - 신길역, 노량진역과 가까움
  - 1,5,9호선을 쉽게 이용할 수 있음
  - 여의도, 강남 30분 안으로 접근 가능

- 광운대역

![image](https://user-images.githubusercontent.com/70933580/166196896-042dc399-059e-43e3-ae8a-0f5b07aa6236.png)
  - 30m^2 기준 500/45, 관리비 5만원 이상
  - 석계역, 상봉과 가까움
  - 학교 앞에 비해 비교적 값싼 원룸
  - 신축 건불 보다는 오래된 건물이 많음

- 서빙고역

![image](https://user-images.githubusercontent.com/70933580/166197214-cb2b197b-4c00-4df4-9eb5-1992551ad76c.png)
  - 19m^2 기준 500/50 관리비 1만원 이상
  - 이촌과 옥수역이 가까움
  - 한강이 가까움
  - 직장이나 학교 위치에 따라 고려해볼만 함

## 결과
### 결론 
- degree가 높은 역들이 대체적으로 between centrality가 높음
- degree가 낮은 역 중 between centrality가 높은 역들이 존재
- 환승역들은 대부분 부동산 시세가 높음
- degree가 낮고 between centrality가 높은 역 중 선호 지역을 기준으로 비교적 부동산 시세가 저렴한 지역을 찾을 수 있음

### 한계
- 경기도권까지 고려한다면 결과가 바뀔 수 있음
- 부동산 시에의 다른 요소들을 고려하지 못함

