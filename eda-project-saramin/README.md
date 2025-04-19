# 사람인 크롤링을 통한 로봇 SW 개발 기업 분석

> 사람인 검색 결과에 노출된 **로봇 SW 개발 관련 기업 정보**를 자동 수집하여  
> **기업 규모, 연봉 수준, 매출액, 지역 분포**를 분석한 프로젝트입니다.

---

## 📌 프로젝트 개요

사람인(saramin) 채용 플랫폼에서 **"로봇 SW 개발" 키워드로 검색 결과에 노출된 기업들을 자동으로 크롤링**하고,  
각 기업의 연봉·매출·규모·위치 등의 데이터를 수집하여 시각적으로 분석했습니다.

- Selenium 기반 검색 페이지 순회 및 상세 정보 수집 자동화
- BeautifulSoup을 활용한 HTML 파싱 및 데이터 정제
- pandas와 matplotlib을 통한 시각화 중심 EDA 수행

---

## ⚙️ 기술 스택

| 분류 | 사용 기술 |
|------|-----------|
| 크롤링 | Selenium, BeautifulSoup |
| 데이터 처리 | pandas, numpy |
| 시각화 | matplotlib |
| 환경 | Python, Jupyter Notebook |

---

## 📂 데이터 수집 방식

- **키워드**: `"로봇 SW 개발"`
- **수집 대상**: 검색 결과에 노출된 모든 기업의 상세 페이지
- **수집 항목**:
  - 기업명, 업력, 업종, 기업형태, 사원수, 매출액, 주소
  - 연봉 정보: 평균 연봉, 최소 연봉, 최대 연봉

---

## 📊 분석 항목 및 주요 결과

### 1. 기업 규모별 연봉 분포

#### ▷ Boxplot  
![](img/기업규모_box.png)  
※ 기업 규모별 연봉 편차가 뚜렷함

#### ▷ Swarmplot  
![](img/기업규모_swarm.png)  
※ 소수 고연봉 기업이 눈에 띔

#### ▷ Barplot  
![](img/기업규모_bar.png)  
※ 대기업 > 중견 > 중소 순으로 평균 연봉 차이 존재

---

### 2. 연봉 수준이 가장 높은 기업들

#### ▷ 평균 연봉 기준  
![](img/top_avg_salary_bar.png)  
![](img/top_avg_salary_table.png)

#### ▷ 최소 연봉 기준  
![](img/top_min_salary_bar.png)

#### ▷ 최대 연봉 기준  
![](img/top_max_salary_bar.png)

※ 일부 기업은 소규모지만 고연봉 정책을 운영

---

### 3. 매출액과 연봉 수준의 관계

#### ▷ 매출 vs 평균 연봉 (log scale)  
![](img/revenue_vs_salary_logscatter.png)

#### ▷ 상관계수 히트맵  
![](img/salary_corr_heatmap.png)

#### ▷ 분포 히스토그램  
![](img/salary_revenue_dist.png)

※ 매출과 연봉 사이에 뚜렷한 상관관계는 보이지 않음

---

### 4. 시도별 총 매출액과 평균 연봉 비교

#### ▷ 시도별 매출 총합  
![](img/province_total_revenue.png)

#### ▷ 시도별 평균 연봉  
![](img/province_avg_salary.png)

※ 수도권과 일부 지역에 고매출/고연봉 기업이 집중됨

---

## 🧑‍💻 기여자

- 장진혁 ([@jinhyuk2me](https://github.com/jinhyuk2me))
