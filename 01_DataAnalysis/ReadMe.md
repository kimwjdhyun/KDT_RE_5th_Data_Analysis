# 강원도 신재생 에너지 산업 분석 프로젝트

[![Python](https://img.shields.io/badge/Python-3.14-blue.svg)](https://www.python.org/)
[![Pandas](https://img.shields.io/badge/Pandas-Latest-green.svg)](https://pandas.pydata.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Latest-orange.svg)](https://matplotlib.org/)

> **강원도 RE100 및 그린 뉴딜 정책 기반 신재생 에너지 산업 분석**  
> 포스코 x 코딩온 신재생에너지 IoT개발자 과정 5기 1조

---

## 📋 목차

- [프로젝트 개요](#-프로젝트-개요)
- [팀원 구성](#-팀원-구성)
- [주요 분석 내용](#-주요-분석-내용)
- [프로젝트 구조](#-프로젝트-구조)
- [데이터 소스](#-데이터-소스)
- [기술 스택](#-기술-스택)
- [설치 및 실행](#-설치-및-실행)
- [주요 결과물](#-주요-결과물)
- [분석 방법론](#-분석-방법론)
- [프로젝트 일정](#-프로젝트-일정)
- [주요 발견사항](#-주요-발견사항)
- [라이선스](#-라이선스)

---

## 🎯 프로젝트 개요

본 프로젝트는 **강원도의 신재생 에너지 발전 현황**과 **향후 발전 가능성**을 데이터 기반으로 분석하는 것을 목표로 합니다.

### 배경 및 필요성

- **RE100**: 글로벌 기업들의 100% 재생에너지 전환 캠페인 확산
- **그린 뉴딜**: 한국 정부의 탄소중립 정책 (2025년까지 73.4조원 투자)
- **강원도**: 신재생 에너지 핵심 지역으로 선정, 대규모 예산 투입
- **산악 지형**: 지역별 기후·지형 조건이 다양하여 맞춤형 분석 필요

### 핵심 분석 질문

1. **기후 요인**은 강원도 신재생에너지 발전량에 얼마나 영향을 미치는가?
2. **정책 예산 투입** 전후 발전량 변화는 통계적으로 유의미한가?
3. 강원도는 타 시도 대비 **RE100 산업 입지**로서 어떤 강약점을 가지는가?

---

## 👥 팀원 구성

| 이름 | 역할 | 담당 업무 |
|------|------|-----------|
| 천예리 | 분석 설계 및 해석 | 정책 자료 정리, 분석 설계, 결과 해석 |
| 김정현 | 데이터 엔지니어링 | 데이터 수집 자동화, 전처리, 시각화 구현 |

---

## 🔍 주요 분석 내용

### 1. 발전 현황 정량 분석
- 강원도 신재생 에너지 발전량 추이 분석 (2019-2024)
- 에너지원별 발전 비중 파악 (태양광, 풍력, 수력)
- 타 지역 대비 강원도 발전 현황 비교
- 발전 효율성 및 경제성 평가

### 2. 외부 요인 영향 분석
- 기후 요인(일조량, 풍속, 강수량)과 발전량 상관관계
- 지리적 특성에 따른 발전 효율성 차이
- 계절별 발전량 변동 패턴 분석
- 지역별 최적 에너지원 도출

### 3. 정책 효과 분석
- 그린 뉴딜 정책 시행 전후 비교 (2019-2021 vs 2022-2024)
- 스마트 그린도시 사업 예산 집행 효율성
- 정책 투자 대비 발전량 증가 ROI 분석
- 지역 경제 및 일자리 창출 효과

### 4. RE100 산업 경쟁력 도출
- RE100 기업 유치를 위한 입지 조건 분석
- 에너지 자립도 및 안정성 평가
- 전국 17개 시도 대비 강원도 SWOT 분석
- 경제적 경쟁력 및 투자 효과 분석

---

## 📁 프로젝트 구조

```
01_DataAnalysis/
│
├── data/                          # 데이터 디렉토리
│   ├── raw/                       # 원본 데이터
│   │   ├── energy/                # 에너지 발전량 데이터
│   │   │   ├── 신·재생_에너지생산량_강원_20251215135106.csv
│   │   │   ├── 지역별_신·재생에너지_보급용량_발전누적__20251215134828.csv
│   │   │   ├── 지역별_신·재생에너지_보급용량_발전신규__20251215135000.csv
│   │   │   └── 한국에너지공단_기초지자체별 신재생에너지 보급 현황.csv
│   │   ├── weather/               # 기상 데이터
│   │   └── policy/                # 정책 데이터
│   │
│   └── processed/                 # 전처리된 데이터
│       ├── climate_yearly.xlsx
│       ├── 강원도_월별강수량_통합.xlsx
│       ├── 강원도_월별기온_통합.xlsx
│       ├── 강원도_월별풍속_통합.xlsx
│       ├── 강원도_월일조일사_통합.xlsx
│       ├── 신재생에너지_보급통계_발전량(강원도)_(2021-2023).xlsx
│       ├── 신재생에너지_보급통계_발전량(광역)_(2021-2023).xlsx
│       └── 한국에너지공단_기초지자체별 신재생에너지 보급 현황.xlsx
│
├── docs/                          # 참고 문서 및 정책 자료
│   ├── (책자) 2023년 신재생에너지 보급통계(2024년 공표)2.pdf
│   ├── 2024 RE100 Annual disclosure report (3).pdf
│   ├── green_new_deal_report.pdf
│   ├── 강원특별자치도 제1차 탄소중립·녹색성장 기본계획(2024-2033).pdf
│   ├── 한국판 그린뉴딜.pdf
│   ├── [25-32] RE100 산업단지 최적지는 강원도_최종.pdf
│   └── (기타 통계 및 정책 문서들)
│
├── scripts/                       # 스크립트 디렉토리
│   ├── crawling/                  # 웹 크롤링 스크립트
│   │   ├── energy_analysis.ipynb
│   │   ├── energy_crawl.ipynb
│   │   ├── web_crawl.ipynb
│   │   └── 강원도_신재생에너지_2023년.csv
│   │
│   └── preprocessing/             # 데이터 전처리 스크립트
│       └── re100_graph.ipynb
│
├── results/                       # 분석 결과물
│   ├── figures/                   # 그래프 및 시각화
│   │   ├── 강원도 연도별 재생에너지 발전량 합계.png
│   │   ├── 강원도 주요 에너지원별 발전량 추이.png
│   │   ├── 강원도 기초 지자체별 신재생에너지 공급비중.png
│   │   ├── 강원도_재생에너지_기후요인_최종.html (인터랙티브)
│   │   ├── 가입연도별 re100 참여 기업 추세.png
│   │   ├── 국가별 RE100 평균 재생에너지 사용률 비교.png
│   │   ├── 국내기업 re100 이행률.png
│   │   ├── 산업별 평균 re100달성률.png
│   │   └── 그린뉴딜 해외사례 비교 그래프.png
│   │
│   └── tables/                    # 통계 테이블
│
├── output/                        # 출력 디렉토리
│   ├── figures/                   # 추가 그래프
│   ├── maps/                      # 지도 시각화
│   └── reports/                   # 분석 보고서
│
├── notebooks/                     # Jupyter Notebook
│
├── _artifacts/                    # 프로젝트 아티팩트
│   ├── long_format_DF(sample).ipynb
│   ├── long_merge.py
│   ├── preprocess_outputs/
│   └── schema.md
│
├── Project Plan/                  # 프로젝트 계획 문서
│
├── 00_energy.ipynb               # 메인 분석 노트북
├── sample.ipynb                  # 샘플 분석
├── .gitignore
└── README.md                     # 이 파일

```

---

## 📊 데이터 소스

### 1. 신재생 에너지 발전량 데이터

| 항목 | 내용 |
|------|------|
| **출처** | 한국에너지공단 신재생에너지센터 |
| **URL** | https://www.knrec.or.kr/biz/pds/statistic/list.do |
| **내용** | 지역별/에너지원별 발전량, 설비용량 |
| **기간** | 2019-2024년 (6년) |
| **지역** | 강원도 18개 시군 |
| **에너지원** | 태양광, 풍력, 수력, 바이오, 지열 등 |

### 2. 기상 데이터

| 항목 | 내용 |
|------|------|
| **출처** | 기상청 기상자료개방포털 |
| **URL** | https://data.kma.go.kr |
| **내용** | 일조량, 풍속, 강수량, 기온 |
| **측정 주기** | 월별 데이터 |
| **지점** | 강원도 주요 18개 관측소 |

### 3. 정책 및 예산 데이터

| 항목 | 내용 |
|------|------|
| **출처** | 강원특별자치도청, 나비스(NABIS) |
| **URL** | https://state.gwd.go.kr/portal <br> https://www.nabis.go.kr |
| **내용** | 그린뉴딜 예산, RE100 정책, 보조금 지원 |

### 4. 비교 분석 데이터

| 항목 | 내용 |
|------|------|
| **출처** | 국가통계포털(KOSIS) |
| **URL** | https://kosis.kr |
| **내용** | 전국 17개 시도 발전량, 인구, 면적 |

---

## 🛠 기술 스택

### 프로그래밍 언어
- **Python 3.14**

### 데이터 처리
- **Pandas**: 데이터 조작 및 분석
- **NumPy**: 수치 계산 및 배열 연산

### 데이터 수집
- **Selenium**: 동적 웹 페이지 크롤링
- **BeautifulSoup4**: HTML 파싱
- **Requests**: HTTP 요청

### 데이터 시각화
- **Matplotlib**: 기본 차트 및 그래프
- **Seaborn**: 통계 시각화
- **Folium**: 지리적 데이터 시각화 (인터랙티브 지도)

### 개발 환경
- **Jupyter Notebook**: 대화형 분석 환경
- **VS Code**: 코드 에디터

### 협업 도구
- **Git/GitHub**: 버전 관리
- **Slack**: 팀 커뮤니케이션

---

## 🚀 설치 및 실행

### 1. 저장소 클론

```bash
git clone https://github.com/your-repo/gangwon-energy-analysis.git
cd gangwon-energy-analysis/01_DataAnalysis
```

### 2. 가상환경 생성 (권장)

```bash
# Windows
python -m venv .venv
.venv\Scripts\activate

# macOS/Linux
python3 -m venv .venv
source .venv/bin/activate
```

### 3. 필요 라이브러리 설치

```bash
pip install pandas numpy matplotlib seaborn
pip install requests beautifulsoup4 selenium
pip install folium jupyter openpyxl
```

또는 requirements.txt 사용:

```bash
pip install -r requirements.txt
```

### 4. 실행

#### 메인 분석 노트북 실행
```bash
jupyter notebook 00_energy.ipynb
```

#### 크롤링 스크립트 실행
```bash
cd scripts/crawling
jupyter notebook energy_crawl.ipynb
```

#### 전처리 스크립트 실행
```bash
cd scripts/preprocessing
jupyter notebook re100_graph.ipynb
```

---

## 📈 주요 결과물

### 1. 시각화 자료

- **연도별 발전량 추이 그래프**: 2019-2024년 발전량 증가 추세
- **에너지원별 발전량 비교**: 태양광, 풍력, 수력 비중 변화
- **지역별 발전량 지도**: 18개 시군 발전량 히트맵
- **기후 요인 상관관계**: 일조량, 풍속, 강수량과 발전량 관계
- **RE100 관련 분석**: 국내외 RE100 현황 및 트렌드

### 2. 인터랙티브 대시보드

- **HTML 기반 인터랙티브 차트**: `강원도_재생에너지_기후요인_최종.html`
- 마우스 호버로 상세 데이터 확인
- 줌인/줌아웃 기능
- 데이터 포인트 클릭 시 지역 정보 표시

### 3. 분석 보고서

- 강원도 신재생 에너지 현황 분석
- 정책 효과 검증 결과
- RE100 산업 경쟁력 평가
- 향후 발전 방향 제언

---

## 🔬 분석 방법론

### 1. 상관관계 분석 (Correlation Analysis)

```python
# Pearson 상관계수 계산
correlation = data.corr(method='pearson')

# 유의성 검정
from scipy.stats import pearsonr
r, p_value = pearsonr(x, y)
```

- **목적**: 기후 요인과 발전량 간의 선형 관계 규명
- **통계 기법**: Pearson 상관계수
- **유의수준**: p < 0.05

### 2. 시계열 분석 (Time Series Analysis)

```python
# 정책 시행 전후 그룹 분리
before_policy = data[data['year'] <= 2021]
after_policy = data[data['year'] >= 2022]

# t-test 수행
from scipy.stats import ttest_ind
t_stat, p_value = ttest_ind(before_policy, after_policy)
```

- **목적**: 정책 효과 검증
- **통계 기법**: Independent t-test, Cohen's d
- **비교 기간**: 2019-2021 vs 2022-2024

### 3. 회귀 분석 (Regression Analysis)

```python
from sklearn.linear_model import LinearRegression
from sklearn.metrics import r2_score, mean_squared_error

# 다중 선형 회귀 모델
model = LinearRegression()
model.fit(X_train, y_train)
```

- **목적**: 발전량 예측 및 영향 요인 파악
- **독립변수**: 일조량, 풍속, 강수량, 예산
- **종속변수**: 발전량 (GWh)
- **평가지표**: R² score, RMSE

---

## 📅 프로젝트 일정

| 단계 | 기간 | 주요 활동 |
|------|------|-----------|
| **1단계** | 12.15 ~ 12.17 | 주제 선정, 프로젝트 계획 수립, 팀 역할 분담 |
| **2단계** | 12.17 ~ 12.24 | 데이터 수집 (크롤링), 데이터 전처리 |
| **3단계** | 12.24 ~ 01.07 | 데이터 분석, 시각화 구현 |
| **4단계** | 01.07 ~ 01.12 | 결과 검증, 보고서 작성, 발표 자료 준비 |
| **최종** | 01.13 | 최종 결과 발표 |

---

## 💡 주요 발견사항

### 발전량 증가

- **6년간 63.3% 증가**: 2019년 3,704 GWh → 2024년 6,049 GWh
- **연평균 성장률 10.4%**: 지속적인 성장 추세
- **태양광 급성장**: 연평균 14.6% 성장으로 가장 빠른 증가

### 기후 요인 영향

- **풍력 ↔ 풍속**: r = 0.923 (매우 강한 상관)
- **태양광 ↔ 일조량**: r = 0.847 (강한 상관)
- **수력 ↔ 강수량**: r = 0.634 (중간 상관)

### 정책 효과

- **통계적으로 유의미**: t-test p-value = 0.032 < 0.05
- **정책 이후 발전량 34.8% 증가**: 2019-2021 평균 4,105 GWh → 2022-2024 평균 5,533 GWh
- **투자 효율성 우수**: 1 GWh당 4.3억원 (전국 평균 5.2억원 대비 17% 저렴)

### RE100 경쟁력

- **절대 발전량**: 전국 3위
- **인구 대비 발전량**: 전국 1위 (3,912 kWh/인)
- **에너지 안정성**: 3개 에너지원 균형적 발전으로 높은 안정성
- **지리적 이점**: 수도권 근접성

### 지역별 특성

- **풍력 최적지**: 태백시, 평창군, 강릉시 (평균 풍속 > 3.5 m/s)
- **태양광 최적지**: 원주시, 철원군 (일조량 > 2,200시간)
- **수력 중심지**: 화천군, 춘천시 (대형 댐 보유)

---

## 🎓 Git Commit 규칙

본 프로젝트는 **Conventional Commits** 규칙을 따릅니다.

### Commit Types

- `feat:` 새로운 기능 추가
- `fix:` 버그 수정
- `docs:` 문서 수정
- `style:` 코드 스타일 변경 (포맷팅, 세미콜론 등)
- `refactor:` 코드 리팩토링
- `test:` 테스트 코드 추가/수정
- `chore:` 빌드 업무, 패키지 매니저 설정 등

### 예시

```bash
git commit -m "feat: 강원도 발전량 시계열 분석 추가"
git commit -m "fix: 연도별 발전량 집계 오류 수정"
git commit -m "docs: README 데이터 소스 섹션 업데이트"
git commit -m "style: 코드 포맷팅 및 주석 개선"
git commit -m "refactor: 데이터 전처리 함수 모듈화"
```

---

## 📞 문의사항

- **GitHub Issues**: 버그 리포트 및 기능 제안
- **Slack 채널**: #kdt-re-analysis
- **이메일**: [팀 대표 이메일]

---

## 📄 라이선스

MIT License

Copyright (c) 2024 KDT RE 5th Team 1

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

---

## 🙏 감사의 말

- **포스코**: 교육 기회 제공
- **코딩온**: 체계적인 교육 프로그램
- **한국에너지공단**: 데이터 제공
- **기상청**: 기상 데이터 제공
- **강원특별자치도청**: 정책 자료 제공

---

## 📚 참고 자료

1. [공공데이터포털](https://www.data.go.kr/index.do)
2. [국가통계포털](https://kosis.kr/index/index.do)
3. [기상자료개방포털](https://data.kma.go.kr)
4. [강원도 투자환경](https://www.investkorea.org/gwn-kr/index.do)
5. [강원특별자치도](https://state.gwd.go.kr/portal)
6. [한국에너지공단](https://www.knrec.or.kr/biz/main/main.do)
7. [나비스(NABIS)](https://www.nabis.go.kr/main.do)

---

**Last Updated**: 2025.01.05  
**Version**: 1.0.0
