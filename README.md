# 🏠 Real Estate Data Lab  
**한국 부동산 시장을 데이터로 해석하는 분석 연구소**

Real Estate Data Lab은 한국 아파트 시장의 실거래가·전세·가격지수·거래량 데이터를  
Python 기반으로 분석하고 시각화하는 프로젝트입니다.  
데이터와 뉴스 흐름을 결합해 부동산 시장을 보다 정확하고 객관적으로 이해하는 것을 목표로 합니다.

---

## 📊 주요 분석 주제

### 1) **실거래가 데이터 분석**
- 지역별 아파트 매매가 추세
- 전용면적·층수·입주연도별 가격 패턴
- 단지별 가격 변동성 분석

### 2) **전세 및 전세가율 분석**
- 전세가율(매매/전세) 변화 추적  
- 지역별 갭투자 리스크 분석  
- 전세 시장 수급(매물·가격) 변화

### 3) **지역별 시장 비교**
- 노도강 vs 강남 3구 비교  
- 과천·세종·수도권 주요 신도시 분석  
- 지방 주요 도시 가격 흐름

### 4) **부동산원·국토부·서울시 공개데이터 활용**
- 부동산 가격지수  
- 매매심리지수  
- 전세가격 흐름  
- 거래량 변화

---

## 🛠 사용 기술(Tech Stack)

- **Python**
- **Pandas / NumPy**
- **Matplotlib / Seaborn / Plotly**
- **Jupyter Notebook**
- **공공데이터포털 API**
- **CSV 기반 오프라인 데이터 처리**

---

## 🚀 시작하기

### 1) 패키지 설치
```bash
pip install -r requirements.txt
```

### 2) Jupyter Notebook 실행
```bash
jupyter notebook
```

### 3) 실거래가 CSV 불러오기 예시
```python
import pandas as pd

df = pd.read_csv("data/apt.csv")
df['거래금액'] = df['거래금액'].str.replace(",", "").astype(int)

df.head()
```

## 📈 예시: 월별 평균 매매가 시각화
```python
import matplotlib.pyplot as plt

df['월'] = df['계약년월'].astype(str).str.slice(0,6)
monthly = df.groupby('월')['거래금액'].mean()

monthly.plot(figsize=(10,4))
plt.title("월별 아파트 평균 매매가")
plt.xlabel("월")
plt.ylabel("거래금액(만원)")
plt.show()
```

## 🏗 향후 계획 (To-Do)

- [ ] 지역별 매매/전세 가격 대시보드 만들기 (Streamlit)
- [ ] 전세가율 기반 갭투자 위험도 지도화
- [ ] 과천·세종 등 특정 지역 심층 레포트 자동화
- [ ] 뉴스 + 데이터 자동 스크립트 생성 기능
- [ ] Notion/블로그 연동 자동화

---

## 📢 만든 사람

**부동산쟁이 견문록 | Real Estate Insight Creator**  
한국 부동산 콘텐츠를 만들고 있습니다.  
