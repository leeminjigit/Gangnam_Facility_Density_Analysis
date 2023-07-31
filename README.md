# Gangnam_Facility_Density_Analysis
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/448c1cd7-2f85-40ac-919f-76cc3933cf45)
## 비지도 학습을 통한 강남구 내 특정 위치의 시설 밀도 분석
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/637b844f-61e3-4966-9c55-87c5d71ce9ff)

📖 introduce
-----
* 서울시 내에서 시설 밀집도가 높은 곳을 찾는다면 많은 사람들은 **강남구**를 말할 것입니다.
* 강남구 내의 모든 곳이 시설 밀집도가 높을까요?
* 강남구의 밀집도 분석 모델은 강남구 내 지역들의 시설 밀집 정도를 제시해줍니다.
  
 ![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/7aec968e-2f7d-48bc-a2e4-248de3642a30)

🎯 result
-----
지역별 밀도 레벨을 구분하여 시설 밀집도가 높은 곳과 낮은 곳을 다섯 단계로 구분하여 지역 특성을 보여줍니다. 

![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/a5bd02cc-252f-4483-89d1-2522dde6665f)

💻 modeling
-------
### 1. Dataset
* 공공데이터 포탈
  * 행정동별 생활인구 데이터
  * 서울시 공중화장실 데이터
  * 강남구 지하철 역 데이터
* 편의점 홈페이지 크롤링
  * 빅5 편의점 브랜드 매장정보
* 로컬 데이터 포탈
  * 인허가 시설 데이터
  
### 2. preprocesing
* 전체 인허가 시설 데이터 중 5개의 카테고리로 정리
  ```
  음식점, 의료시설, 체육시설, 숙박시설, 문화시설
  ```
* 행정동 통일 
  ```
  -1동, -2동, 본동 등 -동으로 통일
  세곡동 산하 율현동, 자곡동 > 세곡동으로 통일 
  ```
