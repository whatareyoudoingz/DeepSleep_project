<img width="1040" alt="image" src="https://github.com/whatareyoudoingz/DeepSleep_project/assets/108795647/3301d76e-548d-49a1-8708-fe7144ec74ce"># ETRI-lifelog-data-project

**라이프로그와 슬립테크기기 기반 수면 질 지표의 머신러닝 연구**

****본 프로젝트는 [라이프로그 데이터를 활용한 수면의 질 추정에서의 주요 요인에 대한 연구](https://github.com/amthreeh/ETRI-lifelog-data-project)의 후속연구입니다.****

----

**1. 데이터**
- 원시 데이터 : [ETRI 라이프로그 데이터셋 (2020)](https://nanum.etri.re.kr/share/schung1/ETRILifelogDataset2020?lang=ko_KR)
- 최종 사용한 가공 데이터 : 2020_2th_paper_data_plus_activity_v2.csv
----

<br/>

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
----

<br/>

**2. 폴더 구성**
- 2020_2th_paper_data_plus_activity_v2.csv : 최종 활용 데이터 파일
- data_2th.iypnb : 데이터 구축 파일
- result_2th.iypnb : 이진분류 결과 파일
  ```
  - 주관적 수면 점수 이진분류
    - origin
    - origin/총 수면시간
    - 
  - 깊은 수면시간 이진분류
    - origin
    - origin/총 수면시간
    - 주요 변수 기반
    ```
----

<br/>
