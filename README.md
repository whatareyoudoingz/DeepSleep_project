# 라이프로그와 슬립테크기기 기반 수면 질 지표의 머신러닝 연구

*!본 프로젝트는 [라이프로그 데이터를 활용한 수면의 질 추정에서의 주요 요인에 대한 연구](https://github.com/amthreeh/ETRI-lifelog-data-project)의 후속연구입니다.!*

----

<br/>

### **1. 연구 요약 및 결과**
- 연구 목적
  
  ```
  수면은 건강한 삶을 유지하는 데 필수적인 요소로서, 수면 문제는 조기 사망의 예측 요인으로 알려져 있다.
  수면에 관한 연구에 따르면,수면시간을 10시간 이상 가진 사람이 7-8시간 가진 사람보다 사망률이 약 1.8배 높아 무조건적인 수면시간의 증가가 삶의 질 향상으로 이어지지 않는다고 볼 수 있다.
  또한 수면의 질은 수면의 양보다 삶의 질 향상과 건강 개선에 더 유의미한 관계를 가지므로 수면의 질을 중점적으로 연구할 필요가 있다.
  
  수면의 질은 통계적 분석에 의해 수면 외 다양한 요인들과 유의한 관계를 가진다고 알려져 있다.
  심리적 요인으로는 우울, 주관적 건강, 스트레스 정도가 있고, 생활 요인은 흡연, 전자기기 사용, 식사 거름이 있으며, 환경 요인은 소음, 불편하거나 불규칙한 잠자리, 조명이 있다.
  본 논문에서는 사용한 한국전자통신연구원(ETRI)의 2020년도 라이프로그 데이터에서는 수면 테크기기로 수면의 질을 측정하는데, 수면 데이터를 측정하고, 이를 기반으로 산출된 수면 점수를 수면의 질 지표로 제공한다.
  수면 테크기기 수면 점수는 Withing Sleep Tracking Mat에서 측정한 총 수면시간, 회복 단계와 수면에 소요되는 밤의 일부, 취침 시간과 일어나는 시간 사이의 일관성, 깨어 있는 시간을 기반으로 측정된다.
  그러나 이 지표는 수면의 양을 나타내는 총 수면시간에 과하게 의존하므로 수면의 질 지표로 사용하기에 무리가 있다.
  
  이에 따라 본 논문에서는 깊은 수면시간을 수면의 질 추정 지표로 삼아 이진분류를 진행하여 정확도를 높이고자 한다.
  또한, 수면의 양적 영향을 줄이고 심리 · 생활 · 환경 요인을 추가하여 수면의 양적 요인 외의 다양한 요인 중에서 수면의 질에 영향을 주는 요인을 탐색하고자 한다.
  ```

<br/>

- 깊은 수면비율을 수면의 질 지표로 선정한 이유
  
  ```
  수면 점수를 기준으로 분류했을 때 중요 변수는 총 수면시간, 램 수면시간, 호흡 방해 강도, 얕은 수면시간, 깊은 수면시간 순이었다.
  또한, 깊은 수면시간은 부족할 시 면역 기능이 저하되고, 신경학적 질환이 악화할 수 있으며, 제2형 당뇨병 및 심장병 발병에 기여하는 등 삶의 질과 건강 악화로 이어진다고 알려져 있다.
  이러한 이유들로 인해 깊은 수면시간은 수면의 질을 좌우한다고 볼 수 있으므로 총 수면시간의 영향을 줄이고자 깊은 수면시간을 총 수면시간으로 나눈 값인 “깊은 수면 비율”을 수면 점수를 대체할 수 면의 질 지표로 설정하였다.
  ```
  
<br/>

- 연구 결과
  
  - 교차검증 정확도
    
    <img width="306" alt="스크린샷 2023-12-10 오후 9 02 03" src="https://github.com/whatareyoudoingz/DeepSleep_project/assets/108795647/b8f5d433-dafe-4274-8932-9c70d41e866d">
    <img width="284" alt="스크린샷 2023-12-10 오후 9 02 23" src="https://github.com/whatareyoudoingz/DeepSleep_project/assets/108795647/ce8cd23b-9b62-4b03-9cd4-063be9f87064">
    
  - 특성중요도
    
    <img width="302" alt="스크린샷 2023-12-10 오후 9 02 45" src="https://github.com/whatareyoudoingz/DeepSleep_project/assets/108795647/b3bc20d6-aca2-40f4-b38c-097a5e2a10a9">
    <img width="302" alt="스크린샷 2023-12-10 오후 9 02 58" src="https://github.com/whatareyoudoingz/DeepSleep_project/assets/108795647/cbeb63dd-774f-46e6-b4c9-a630d9a8d3e8">

<br/>

- 연구 요약
  
  ```
  본 논문에서 2020년도 ETRI 라이프로그 데이터셋을 사용하여 앙상블 머신러닝 모델로 수면 지표를 이진 분류하였고, 특성 중요도를 통해 기존 수면 지표를 대신할 지표를 탐색하였다.
  라이프로그 데이터로부터 총 수면시간의 영향을 제외하고 기존 수면 테크기기의 ‘수면점수’를 기준으로 숙면과 비 숙면 그룹을 나눈 결과의 정확도는 82.7%였다.
  의공학 해석과 중요도를 고려하여 깊은 수면 비율을 수면의 질 구분 지표로 선택하였고, 총 수면 시간을 제거한 데이터로 분류한 새로운 지표 그룹의 머신러닝 정확도는 83.5%였다.
  새로운 특성 중요도의 순위를 확인했을 때, 심리 · 생활 · 환경 요인 중 ‘대면 소통’, ‘사교활동(Socialising)’, ‘야외 활동(Outdoor Act)’등의 요인이 수면에 영향을 미친다는 것을 알 수 있었다.
  특정 지표에 의존하지 않도록 개선함으로써 새롭게 중요도가 부각된 특성들을 고려하여 심박수, 호흡, 수면 방해 요소를 개선하는 것에 더해 타인과의 소통 및 야외 활동의 빈도를 조절하면 수면의 질 개선에 도움이 될 수 있음을 발견하였다.
  ```
  
----

<br/>


### **2. 데이터** : [ETRI 라이프로그 데이터셋 (2020)](https://nanum.etri.re.kr/share/schung1/ETRILifelogDataset2020?lang=ko_KR)
  
- 스케일링해줘야 될 연속형 변수
    - cAmount(ml) : 카페인 섭취량
    - aAmount(ml) : 알코올 섭취량
    - wakeupduration : 일어난 시간
    - lightsleepduration : 얕은 수면시간
    - deepsleepduration : 깊은 수면시간
    - wakeupcount : 일어난 횟수
    - durationtosleep : 잠자는 데 든 시간
    - remsleepduration : 램 수면시간
    - durationtowakeup : 일어나는 데 든 시간
    - hr_average : 평균 심박수
    - hr_min : 최소 심박수
    - hr_max : 최대 심박수
    - rr_average : 평균 호흡량
    - rr_min : 최소 호흡량
    - rr_max : 최대 호흡량
    - breathing_disturbances_intensity : 호흡 방해 강도
    - snoring : 코골이 시간
    - snoringepisodecount : 코골이 횟수
    - sleep_score : 주관적 수면 점수
    - total_sleep_time : 총 수면시간

- 이진분류 기준 수치
  <img width="1040" alt="image" src="https://github.com/whatareyoudoingz/DeepSleep_project/assets/108795647/3301d76e-548d-49a1-8708-fe7144ec74ce">

----

<br/>


### **3. 폴더 구성**
- `2020_2th_paper_data_plus_activity_v2.csv` : 최종 활용 데이터 파일
- `data_2th.iypnb` : 데이터 구축 파일
- `result_2th.iypnb` : 이진분류 결과 파일
  
  ```
  - 주관적 수면 점수 이진분류
    - origin
    - origin/총 수면시간

  - 깊은 수면시간 이진분류
    - origin
    - origin/총 수면시간
    - 주요 변수 기반
    ```
  
----

<br/>
