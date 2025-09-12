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

- _Describe your EDA process and step-by-step conclusion_

### Data Processing

- _Describe data processing process (e.g. Data Labeling, Data Cleaning..)_

## 4. Modeling

### Model descrition

- _Write model information and why your select this model_

### Modeling Process

- _Write model train and test process with capture_

## 5. Result

### Leader Board
<img width="836" height="657" alt="image" src="https://github.com/user-attachments/assets/e3c317b3-3f73-4ab5-8357-58573f62823b" />

rank: 1
RMSE: 11861.9779
submission count: 54

### Presentation

- _Insert your presentaion file(pdf) link_

### Reference

- _Insert related reference_ 현태님
