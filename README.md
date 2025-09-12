# 아파트 실거래가 가격 예측 경진 대회
## Team

| ![박패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![이패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![최패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![김패캠](https://avatars.githubusercontent.com/u/156163982?v=4) | ![오패캠](https://avatars.githubusercontent.com/u/156163982?v=4) |
| :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: | :--------------------------------------------------------------: |
|            [안현태](https://github.com/UpstageAILab)             |            [문서연](https://github.com/UpstageAILab)             |            [손은혜](https://github.com/UpstageAILab)             |            [정용재](https://github.com/UpstageAILab)             |            [주예령](https://github.com/UpstageAILab)             |
|                            팀장, 팀 활동 주도/ 데이터 EDA 담당                             |                            도전 독려/리더보드 순위권 유지                             |                            외부데이터 가공 및 테스트, 다양한 모델로 테스트                             |                            데이터 전처리 및 외부데이터 테스트                             |                            모델 테스트                             |

## 0. Overview
Upstage AI Stages에서 진행하는
**House Price Prediction | 아파트 실거래가 예측 대회**에 참여하기 위한 팀 리포

목표: 주어진 아파트 관련 데이터(위치, 면적, 건축년도 등)를 활용하여
**거래금액(target)**을 예측하는 머신러닝 회귀 모델을 개발

### Environment
-   파이썬 10 또는 11
-   가상환경(콘다 등)

### Requirements
-   matplotlib==3.7.1
-   numpy==1.23.5
-   pandas==1.5.3
-   scipy==1.11.3
-   seaborn==0.12.2
-   scikit-learn==1.2.2
-   statsmodels==0.14.0
-   tqdm==4.66.1

## 1. Competiton Info

### Overview

- 대회명: house Price Prediction | 아파트 실거래가 예측
- 주최: Upstage AI Stages
- 목표: 서울시 아파트 실거래 데이터를 활용해 매매 가격 예측
### Timeline

- September 1, 2025 - Start Date
- September 12, 2025 - Final submission deadline

## 2. Components

### Directory

```
project-repo/
│
├── data/       
    ├── baseline/        # baseline code (공통 데이터)
│   ├── raw/             # 원본 데이터
│   └── processed/       # 전처리 데이터
│
├── notebooks/           # 개인별 Jupyter Notebook 작업 공간
│   ├── eunhye/          # 손은혜 개인 폴더
│   ├── hyoentae/        # 안현태 개인 폴더
│   ├── seoyeon/         # 문서연 개인 폴더
│   └── yeryeong/        # 정용재 개인 폴더  
│   └── yongjae/ 
├── src/                 # 프로젝트 코드 (Python 스크립트, 모듈화된 코드)
│
├── reports/             # 보고서, 회의 정리, 결과물
│   ├── figures/         # 시각화 이미지, 그래프
│
├── README.md            # 프로젝트 설명 문서
└── requirements.txt     # 패키지/환경 정보

```
## 3. Data descrption

### Dataset overview

.csv 형태로 제공 

학습 데이터는 1,118,822개 
학습 데이터의 기간: 2007년 1월 1일부터 2023년 6월 30일까지

### EDA

**과정**

- 계약년(계약년) 기준으로 연도별 데이터 분포 확인

- 결측치 비율 확인 (예: 면적 정보, 위치 좌표, 도로명 등)

- 주요 피처(전용면적, 층, 위치, 금리 등)와 타깃(target) 간 상관관계 시각화

- 타깃값의 분포 확인 (왜도, 이상치 존재 여부 확인 → 로그 변환 고려)

**결론**

- 데이터가 특정 연도(2014~2020)에 집중되어 있어 불균형 존재

- 일부 피처에서 결측치와 이상치 발견 → 전처리 필요

- 집값 분포가 한쪽으로 치우쳐 있음 → 정규화/변환 필요

### Data Processing

**과정**

- **데이터 라벨링**: 타깃 변수(거래금액) 정의

- **데이터 클리닝**: 결측치 처리, 불필요한 피처 제거

**Feature Engineering**:

- 연도(계약년) 기반 샘플 수 가중치 부여 (중앙값 / 해당연도 샘플 수)

- 금리, 거래량, 전세-매매 갭, 공급량 등 파생변수 추가

- 카테고리형 피처(아파트명, 동) → 타깃 인코딩

- *스케일링/정규화*: 로그 변환(log1p) 적용해 타깃 분포 안정화

## 4. Modeling

### Model descrition

**LightGBM** 선택

- 범주형/수치형 혼합 데이터에 강함

- 학습 속도 빠르고 성능 우수

- 불균형 데이터에 가중치 적용 가능

### Modeling Process

**Train / Validation Split: 시간 기반 분할(TimeSeriesSplit) 적용**

- 가중치 적용 학습: 연도별 샘플 수 불균형 완화

- 하이퍼파라미터 튜닝: Optuna 활용 (learning_rate, num_leaves, max_depth 등)

- 평가 지표: **RMSE** (Root Mean Squared Error)

## 5. Result
- Baseline Model: RMSE ≈ 17,300

- 가중치 적용 후: RMSE ≈ 14051.0850

- 최종 보드 결과: RMSE ≈ 11861.9779 (성능 크게 향상)

- 결론: 연도별 불균형 해소를 위한 가중치 적용이 성능 개선에 크게 기여
### Leader Board
<img width="836" height="657" alt="image" src="https://github.com/user-attachments/assets/e3c317b3-3f73-4ab5-8357-58573f62823b" />

rank: 1
RMSE: 11861.9779
submission count: 54

### Presentation

- _Insert your presentaion file(pdf) link_

### Reference

- LightGBM 공식 문서 (https://lightgbm.readthedocs.io)

- Optuna 하이퍼파라미터 튜닝 가이드 (https://optuna.org)
