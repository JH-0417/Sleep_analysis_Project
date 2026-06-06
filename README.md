# 😴 Sleep Pattern Analysis

> 갤럭시 워치 수면 데이터로 나만의 최적 수면 패턴 찾기







***

## 📌 프로젝트 개요

갤럭시 워치로 측정한 **개인 수면 데이터**를 분석하여, 수면 점수에 영향을 주는 요소를 파악하고 나에게 최적화된 수면 패턴을 도출하는 데이터 분석 프로젝트입니다.

> **"나는 몇 시에 자서 몇 시간 자야 가장 컨디션이 좋은가?"**

***

## 📁 프로젝트 구조

```
sleep-analysis/
├── data/
│   ├── raw/                       # 원본 데이터 (Samsung Health 내보내기) - gitignore 처리
│   │   ├── Sleep.csv              # 일별 수면 요약 데이터
│   │   ├── Sleep-Stage.csv        # 분 단위 수면 단계 데이터
│   │   └── Sleep-Goal.csv         # 목표 취침·기상 시간 설정값
│   └── processed/                 # 전처리된 데이터
│       └── sleep_cleaned.csv
├── notebooks/
│   ├── 01_load_and_explore.ipynb  # 데이터 로드 및 탐색
│   ├── 02_preprocessing.ipynb     # 전처리
│   ├── 03_eda.ipynb               # 탐색적 분석 (EDA)
│   ├── 04_visualization.ipynb     # 시각화
│   └── 05_modeling.ipynb          # 머신러닝 모델
├── outputs/
│   └── figures/                   # 저장된 그래프 이미지
├── .gitignore
├── requirements.txt
└── README.md
```

***

## 📊 데이터 출처

**Samsung Health** — Galaxy Watch 개인 수면 데이터 내보내기 (privacy.samsung.com)

| 파일 | 설명 | 크기 |
|------|------|------|
| `Sleep.csv` | 일별 수면 요약 (점수, 시간, 회복도, 효율 등) | ~130 KB |
| `Sleep-Stage.csv` | 분 단위 수면 단계 (얕은 수면 / 깊은 수면 / REM / 각성) | ~4.7 MB |

### 주요 컬럼 (Sleep.csv)

| 컬럼명 | 설명 |
|--------|------|
| `sleep_score` | 종합 수면 점수 (0~100) |
| `sleep_duration` | 총 수면 시간 (밀리초) |
| `start_time` | 취침 시작 시간 |
| `end_time` | 기상 시간 |
| `deep_score` | 깊은 수면 점수 |
| `rem_score` | REM 수면 점수 |
| `wake_score` | 각성 점수 |
| `physical_recovery` | 신체 회복도 |
| `mental_recovery` | 정신 회복도 |
| `efficiency` | 수면 효율 (%) |

***

## 🔍 분석 단계

| 단계 | 파일 | 내용 | 상태 |
|------|------|------|------|
| 1단계 | `01_load_and_explore.ipynb` | 데이터 로드 및 구조 파악 | 🔄 진행 중 |
| 2단계 | `02_preprocessing.ipynb` | 날짜 변환, 결측치 처리, 파생 변수 생성 | ⬜ 예정 |
| 3단계 | `03_eda.ipynb` | 수면 시간·점수 분포, 요일별 패턴 분석 | ⬜ 예정 |
| 4단계 | `04_visualization.ipynb` | 수면 패턴 시각화 그래프 | ⬜ 예정 |
| 5단계 | `05_modeling.ipynb` | XGBoost로 수면 점수 예측 모델 | ⬜ 예정 |

***

## 🛠 사용 기술

```
Python 3.10+
├── 데이터 처리   : pandas, numpy
├── 시각화        : matplotlib, seaborn
└── 머신러닝      : scikit-learn, XGBoost
```

***

## ⚙️ 설치 및 실행

### 1. 저장소 클론

```bash
git clone https://github.com/{your-username}/sleep-analysis.git
cd sleep-analysis
```

### 2. 라이브러리 설치

```bash
pip install -r requirements.txt
```

### 3. 데이터 준비

`data/raw/` 폴더에 Samsung Health에서 내보낸 CSV 파일을 직접 넣어주세요.
(개인정보 보호를 위해 원본 데이터는 저장소에 포함되어 있지 않습니다.)

### 4. 노트북 실행

VS Code에서 `notebooks/` 폴더의 파일을 **01번부터 순서대로** 실행하세요.

***

## ⚠️ 데이터 비공개 안내

`data/raw/` 및 `data/processed/` 폴더의 수면 데이터는 **개인정보 보호**를 위해 GitHub에 업로드하지 않습니다. `.gitignore`에 의해 자동으로 제외됩니다.

***

## 📝 License

This project is for personal use and learning purposes.
