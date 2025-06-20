# 직원 이탈 예측 프로젝트 (Employee Attrition Prediction)

본 프로젝트는 기업 인사 데이터 기반으로 **직원 이탈 여부(Attrition)**를 예측하는 머신러닝 모델을 구축하고,  
퇴사에 영향을 미치는 주요 요인을 파악하는 데에 목적을 둡니다.  
SVM과 의사결정나무 모델을 활용하여 예측력과 해석 가능성을 동시에 고려한 HR 분석을 수행했습니다.

<br/>

## 프로젝트 개요

- **목표**: 직원의 이탈 가능성을 사전에 예측하고, 이를 통해 조직의 핵심 인재 유지를 위한 전략 수립에 기여
- **데이터 출처**: [Employee Attrition Dataset (Kaggle)](https://www.kaggle.com/datasets/stealthtechnologies/employee-attrition-dataset)
- **사용 모델**:
  - Support Vector Machine (SVM)
  - Decision Tree 

<br/>

## 파일 구성

| 파일명 | 설명 |
|--------|------|
| `attrition_prediction.ipynb` | 전체 분석이 포함된 Jupyter Notebook |
| `train.csv` / `test.csv` | 전처리된 학습/테스트 데이터셋 |
| `직원 이탈 여부 예측 보고서.pdf` | 분석 과정과 결과를 정리한 팀 보고서 |
| `README.md` | 리포지토리 설명 문서 |

<br/>

## 주요 변수 요약

- **예측 대상 변수**: `Attrition` (Stayed / Left)
- **대표 변수**:
  - 수치형: `Age`, `Years at Company`, `Monthly Income`, `Distance from Home`, `Company Tenure`
  - 범주형: `Job Role`, `Overtime`, `Marital Status`, `Job Satisfaction`, `Work-Life Balance`, `Remote Work` 등 18개

<br/>

## 모델링 및 성능 요약

### Support Vector Machine (SVM)
- **전처리**: 범주형 변수 → 원-핫 인코딩, 수치형 변수 → 표준화
- **하이퍼파라미터 튜닝**: `C = 0.1`에서 F1-score 최대
- **정확도**: 75.0%
- **F1-score (퇴사자)**: 0.74
- **주요 영향 변수**: `Distance from Home`, `Promotions`, `Dependents`

### Decision Tree
- **전처리**: 범주형 변수 → 라벨 인코딩
- **가지치기(alpha)**: `0.005` 선택 (test acc: 70.1%)
- **정확도**: 71.7%
- **해석 가능성**: 퇴사 예측 규칙 도출 가능
- **주요 영향 변수**: `Marital Status`, `Job Level`, `Remote Work`

<br/>

## 주요 인사이트

- **미혼자**, **초과근무자**, **낮은 워라밸(Poor)**을 가진 직원의 퇴사 확률이 높음
- **리더십 기회**, **원격근무 가능 여부**, **직무 수준(Job Level)**은 퇴사 확률을 낮춤
- **선형 모델(SVM)**은 변수 해석이 가능하지만, **비선형 모델(Decision Tree)**는 더 직관적인 해석 제공

<br/>

> 사용 도구: Python (pandas, scikit-learn, matplotlib, seaborn)

<br/>

## 참고 자료

- [Kaggle Dataset](https://www.kaggle.com/datasets/stealthtechnologies/employee-attrition-dataset)
- 분석 보고서: `직원 이탈 여부 예측 보고서.pdf`

---
