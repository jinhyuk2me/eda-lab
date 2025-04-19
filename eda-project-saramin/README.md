# 👩‍💻 로봇 SW 개발 기업 분석 (사람인 기반)

> 사람인 검색 결과에 노출된 **로봇 SW 개발 관련 기업 정보**를 자동 수집하여  
> **기업 규모, 연봉 수준, 매출액, 지역 분포**를 분석한 프로젝트입니다.

---

## 📌 프로젝트 개요

본 프로젝트는 사람인(saramin) 채용 플랫폼에서 **"로봇 SW 개발" 키워드로 검색 결과에 노출된 기업들을 자동 크롤링**하여, 해당 기업들의 주요 지표를 분석한 것입니다.

- Selenium을 활용한 검색 페이지 순회 및 기업 상세 정보 수집
- BeautifulSoup 기반 HTML 파싱 및 데이터 전처리
- pandas 및 matplotlib을 활용한 시각화 기반 EDA 수행

---

## ⚙️ 기술 스택

| 분류 | 사용 기술 |
|------|-----------|
| 크롤링 | Selenium, BeautifulSoup |
| 데이터 처리 | pandas, numpy, re |
| 시각화 | matplotlib |
| 환경 | Python, Jupyter Notebook (Linux 기반) |

---

## 📂 데이터 수집 방식

- 키워드: **"로봇 SW 개발"**
- 수집 방식: **검색 결과 페이지의 기업 목록을 Selenium으로 자동 수집**
- 수집 항목:
  - 기업명, 업력, 업종, 기업형태, 사원수, 매출액, 주소
  - 연봉 정보: **평균 연봉, 최소 연봉, 최대 연봉**

---

## 📊 분석 항목 및 주요 결과

### 1. 기업 규모별 연봉 분포

| 유형 | 시각화 |
|------|--------|
| Boxplot | ![](img/기업규모_box.png) |
| Swarmplot | ![](img/기업규모_swarm.png) |
| Barplot | ![](img/기업규모_bar.png) |

---

### 2. 연봉 수준이 가장 높은 기업들

| 기준 | 시각화 |
|------|--------|
| 평균 연봉 | ![](img/top_avg_salary_bar.png) ![](img/top_avg_salary_table.png) |
| 최소 연봉 | ![](img/top_min_salary_bar.png) |
| 최대 연봉 | ![](img/top_max_salary_bar.png) |

※ 일부 기업은 업력이나 사원 수가 작지만 고연봉을 제공함

---

### 3. 매출액과 연봉 수준의 관계

- 매출이 높다고 해서 연봉이 높지는 않음

| 설명 | 시각화 |
|------|--------|
| 매출 vs 평균연봉 (log scale) | ![](img/revenue_vs_salary_logscatter.png) |
| 상관계수 히트맵 | ![](img/salary_corr_heatmap.png) |
| 분포 히스토그램 | ![](img/salary_revenue_dist.png) |

※ 매출과 평균 연봉 간의 상관계수는 낮은 편

---

### 4. 시도별 총 매출액과 평균 연봉 비교

- 지역별 산업 집중도, 기업 규모 차이 등이 연봉에 영향을 미침

| 항목 | 시각화 |
|------|--------|
| 시도별 매출 총합 | ![](img/province_total_revenue.png) |
| 시도별 평균 연봉 | ![](img/province_avg_salary.png) |

---

## 🧑‍💻 기여자

- 장진혁 ([@jinhyuk2me](https://github.com/jinhyuk2me))
