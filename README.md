# NBA 챔피언십 예측 분석

이 프로젝트는 4개의 머신러닝 모델을 사용하여 NBA 팀의 성과를 예측하고 챔피언십 우승 확률을 분석합니다.

## 📊 프로젝트 개요

- **목표**: NBA 플레이오프 시뮬레이션을 통한 챔피언십 예측
- **방법론**: 다중 머신러닝 모델 앙상블 및 시뮬레이션 기반 예측
- **데이터**: 2017-2023년 정규시즌 및 플레이오프 데이터 활용

## 🚀 주요 특징

### 다중 모델 앙상블
- **XGBoost**: 그래디언트 부스팅 기반 회귀 모델
- **LightGBM**: 효율적인 그래디언트 부스팅 프레임워크
- **Random Forest**: 앙상블 학습 기반 회귀 모델
- **CatBoost**: 범주형 데이터 처리에 특화된 그래디언트 부스팅

### 고급 피처 엔지니어링
- 팀 성과 지표 (득점, 어시스트, 리바운드 등)
- 시즌 진행률 및 최근 폼 분석
- 홈/어웨이 효과 반영
- 팀 간 상호작용 특성

### 현실적인 시뮬레이션
- 1000회 시뮬레이션을 통한 확률적 분석
- NBA의 높은 변동성을 반영한 노이즈 추가
- 플레이오프 특성을 고려한 홈 어드밴티지 적용

## 📁 파일 구조

### 필수 파일 (깃허브 업로드 권장)
```
├── NBA_Championship_Prediction_Clean.ipynb  # 메인 분석 노트북
├── README.md                                # 프로젝트 설명서
├── requirements.txt                         # 필요한 라이브러리 목록
├── 2017_2023_정규_플옵_재구성완료.csv        # 훈련 데이터 (필수)
├── 2024_25_파생변수_포함_WIN_PROB_최종.csv    # 검증 데이터 (필수)
└── data/                                    # 데이터 파일들
    ├── nba_team_stats_2020_25.csv          # 팀 통계 데이터
    └── NBA_Team_Stats_Regular_Playoffs_2014_2024.csv  # 플레이오프 데이터
```

### 결과 파일 (선택적 업로드)
```
├── model_performance_comparison.csv         # 모델 성능 비교 결과
├── nba_playoffs_simulation_results.csv     # 시뮬레이션 결과
└── feature_importance_analysis.csv         # 피처 중요도 분석
```

## 🛠️ 설치 및 실행

### 1. 필요 라이브러리 설치
```bash
pip install -r requirements.txt
```

### 2. 노트북 실행
```bash
jupyter notebook NBA_Championship_Prediction_Clean.ipynb
```

## 📈 분석 결과

### 모델 성능 비교
- 교차 검증을 통한 객관적 성능 평가
- RMSE, MAE, R² Score 지표 활용
- 최고 성능 모델 자동 선택

### 시뮬레이션 결과
- 4강 진출팀: Minnesota Timberwolves, Oklahoma City Thunder, Indiana Pacers, New York Knicks
- 컨퍼런스별 승률 및 시리즈 스코어 분포 분석
- 결승 진출팀 예측

## 🔧 기술적 특징

### 데이터 전처리
- 팀명 정규화 및 결측치 처리
- 이상치 제거 및 데이터 밸런싱
- RobustScaler를 통한 특성 스케일링

### 모델 최적화
- Early stopping을 통한 과적합 방지
- 하이퍼파라미터 튜닝
- 교차 검증을 통한 일반화 성능 평가

### 시뮬레이션 설계
- 시드 제어를 통한 재현 가능한 결과
- 가중치 기반 최근 경기 데이터 샘플링
- 현실적인 득점 범위 제한

## 📊 주요 지표

- **정확도**: R² Score > 0.85
- **안정성**: 낮은 표준편차의 교차 검증 결과
- **현실성**: NBA 경기의 실제 득점 분포 반영

## 🎯 활용 방안

1. **스포츠 분석**: NBA 팀의 성과 예측 및 분석
2. **머신러닝 교육**: 다중 모델 비교 및 앙상블 기법 학습
3. **데이터 사이언스**: 시뮬레이션 기반 확률적 분석 방법론

## ⚠️ 주의사항

- 이 분석은 과거 데이터를 기반으로 한 예측으로, 실제 경기 결과와는 차이가 있을 수 있습니다.
- 모델의 성능은 사용된 데이터의 품질과 양에 크게 의존합니다.
- 시뮬레이션 결과는 확률적 예측이며, 절대적인 결과를 보장하지 않습니다.

## 📤 깃허브 업로드 가이드

### 1. 필수 파일 업로드
```bash
# 메인 파일들
git add NBA_Championship_Prediction_Clean.ipynb
git add README.md
git add requirements.txt

# 핵심 데이터 파일들
git add 2017_2023_정규_플옵_재구성완료.csv
git add 2024_25_파생변수_포함_WIN_PROB_최종.csv
git add nba_team_stats_2020_25.csv
git add NBA_Team_Stats_Regular_Playoffs_2014_2024.csv

git commit -m "Initial commit: NBA Championship Prediction Analysis"
git push origin main
```

### 2. 선택적 파일 업로드
```bash
# 결과 파일들 (선택사항)
git add model_performance_comparison.csv
git add nba_playoffs_simulation_results.csv
git add feature_importance_analysis.csv

git commit -m "Add analysis results"
git push origin main
```

### 3. .gitignore 권장사항
```
# 대용량 파일 제외
*.csv
!2017_2023_정규_플옵_재구성완료.csv
!2024_25_파생변수_포함_WIN_PROB_최종.csv
!nba_team_stats_2020_25.csv
!NBA_Team_Stats_Regular_Playoffs_2014_2024.csv

# 기타 제외 파일
__pycache__/
*.pyc
.ipynb_checkpoints/
```

## 🤝 기여하기

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

## 📞 연락처

프로젝트 관련 문의사항이 있으시면 이슈를 생성해 주세요.

---

**Made with ❤️ for NBA Analytics**
