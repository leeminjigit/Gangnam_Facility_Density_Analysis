# 비지도 학습을 통한 강남구 내 특정 위치의 시설 밀도 분석
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/448c1cd7-2f85-40ac-919f-76cc3933cf45)

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
### 3. EDA
part 1. 행정동 별 생활인구 & 시설 현황

part 2. 강남구 시설별 분포 지도
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/6d7f4b63-156b-4320-babf-72b459096def)
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/09dc0eb0-6a05-4cf7-a735-1ec4654c8820)

### 4. model seting
**(1) 폴리곤 바운더리 활용하여 강남구 내 랜덤 좌표 추출**

폴리곤 바운더리로 랜덤 좌표 중 강, 산 부분을 제외
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/90376473-139d-4b1f-9924-8faf1deb9084)

**(2) 랜덤 좌표 기준 반경 500m 내 시설별 개수 추출, 전처리**

랜덤 좌표를 기준으로 반경 500m 내 편의시설별 개수를 추출
위경도를 제외한 좌표별 시설 개수를 피처로 사용
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/ad9546c8-fab1-4051-b359-fafd725f434d)

**(3) 군집화(KMeans)**

클러스터 5개로 나누었을 때가 가장 적절하다 판단.

**(4) 클러스터별 밀도 레벨 구분 – 평균값, 중위값 활용**

평균값과 중위값을 기준으로 밀도가 높은 클러스터를 선별
![image](https://github.com/leeminjigit/Gangnam_Facility_Density_Analysis/assets/135116165/df7a49dd-e86b-481b-88fb-339ffae05db0)























