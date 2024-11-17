# lecture-1083-project  
  
README.md  
  
# 타이타닉 데이터셋 분석  
  
## 프로젝트 개요  
  
타이타닉 데이터셋을 활용하여 생존 여부를 예측하기 위한 머신러닝 모델을 개발하기보다는 데이터 자체의 특성을 분석하고 잠재적인 의미를 탐구합니다.  
이를 통해 탑승객들의 생존과 관련된 다양한 변수 간의 관계 및 주요 인사이트를 발견하고 해석합니다.  
    
## 주요 목적  
  
- 데이터 탐색: 데이터 구조를 이해하고, 누락된 값을 식별하며, 주요 특징의 분포를 탐색합니다.  
- 특징 분석: 다양한 특징(예: 좌석 등급, 성별, 나이, 고객 요금)에 대한 심층 분석을 수행하여 생존율에 미치는 영향을 발견합니다.  
- 모델 개발: 승객 생존율을 예측하기 위해 `RandomForestClassifier`를 사용하여 분류 모델을 구축하고 세분화합니다.  
- 인사이트 추출: 데이터 시각화 및 해석을 통해 유의미한 결과를 도출합니다.  
  
## 데이터셋 정보  
  
타이타닉 데이터셋에는 다음과 같은 열이 포함되어 있습니다:  
Survived: 0=사망, 1=생존  
Pclass: 1=1등석, 2=2등석, 3=3등  
Sex: male=남성, female=여성  
Age: 나이  
SipSp: 타이타닉 호에 동승한 자매 / 배우자의 수  
Parch: 타이타닉 호에 동승한 부모 / 자식의 수  
Ticket: 티켓 번호  
Fare: 승객요금  
Cabin: 방 호수  
Embarked: 탑승지, S=사우샘프턴, C=셰르부르, Q=퀸즈타운  
  
## 구체적인 구현 내용  
- 데이터 탐색 및 전처리  
	결측값 확인 및 처리:  
    Age와 Fare의 결측치는 중앙값과 0으로 대체.  
    Cabin은 결측치 비율이 매우 높아 분석에서 제외.  
	범주형 변수 변환: 성별(Sex)과 탑승 항구(Embarked)를 숫자형으로 매핑.  
- 데이터 분석  
	단일 변수 분석: 승객의 좌석 등급(Pclass), 성별(Sex), 연령대(AgeGroup), 승객 요금(Fare)의 분포 분석.  
	다중 변수 분석: 변수 간의 관계와 생존율 분석. 예) 성별 및 좌석 등급에 따른 생존율 시각화.  
	통계적 검증 및 시각화를 통한 인사이트 도출.  
- 모델 개발 및 최적화  
	랜덤 포레스트(Random Forest) 기반의 분류 모델 개발.  
	GridSearchCV를 사용하여 최적의 하이퍼파라미터 탐색.  
	모델 성능 평가: Accuracy, Precision, Recall, F1 Score 확인.  
	사망자를 잘 예측하는 데 초점  
- 결과 분석  
	좌석 등급과 요금은 생존율에 중요한 영향을 미침.  
	여성 및 어린아이 그룹의 생존율이 높았음.  
	저렴한 요금을 낸 승객의 생존율은 상대적으로 낮음.  
  
## 개발환경  
Python 3.9 이상  
주요 라이브러리:  
Pandas, Numpy: 데이터 처리 및 조작  
Matplotlib, Seaborn: 시각화   
Scikit-learn: 모델 개발 및 평가  
데이터: 타이타닉 데이터셋  
Jupyter Notebook  
  
  
## 프로젝트 구조  
  
titanic-analysis/ ├── data/ │ ├── train.csv │ └── test.csv ├── notebooks/ │  
└── titanic_analysis.ipynb ├── README.md ├── pyproject.toml └── requirements.txt  
  
## 실행 방법  
  
   1. 의존성 도구 설치  
프로젝트 폴더로 이동 후, 아래 명령어를 실행하여 필요한 Python 패키지를 설치  
pip install -r requirements.txt  
  
   2. 데이터셋 준비  
데이터 파일 위치:  
./data/train.csv  
./data/test.csv  
위 경로에 타이타닉 데이터셋 파일을 배치합니다.  
train.csv와 test.csv 파일은 Kaggle에서 다운로드할 수 있습니다 (Kaggle Titanic Dataset).  
   3. 분석 노트북 실행  
Jupyter Notebook을 사용하여 분석을 수행:  
jupyter notebook assignment.ipynb  
   4. 분석 결과 확인  
분석 결과는 nbviewer를 통해 쉽게 확인할 수 있습니다:  
https://nbviewer.org/github/suoooo-01/lecture-1083-project/blob/main/assignment.ipynb  
터미널 명령어 예시  
의존성 설치:  
pip install -r requirements.txt  
Jupyter Notebook 실행: jupyter notebook assignment.ipynb  