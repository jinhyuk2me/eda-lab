![banner](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/banner.jpg?raw=true)

# 웹 크롤링을 통한 로봇 SW 개발 기업 분석

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

| 분류 | 사용 기술 | 배지 |
|------|-----------|------|
| **크롤링** | Selenium<br>BeautifulSoup | ![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)<br>![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-4B8BBE?style=for-the-badge&logo=python&logoColor=white) |
| **데이터 처리** | pandas<br>numpy | ![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)<br>![NumPy](https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white) |
| **시각화** | matplotlib | ![Matplotlib](https://img.shields.io/badge/matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white) |
| **환경** | Python<br>Jupyter Notebook | ![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white)<br>![Jupyter](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white) |


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
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/1.png?raw=true)  

#### ▷ Swarmplot  
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/2.png?raw=true)  

#### ▷ Barplot  
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/3.png?raw=true)  

---

### 2. 연봉 수준이 가장 높은 기업들

#### ▷ 평균 연봉 기준  
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/4.png?raw=true)  
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/5.png?raw=true)

#### ▷ 최소 연봉 기준  
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/6.png?raw=true)

#### ▷ 최대 연봉 기준  
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/7.png?raw=true)

※ 일부 기업은 소규모지만 고연봉 정책을 운영

---

### 3. 매출액과 연봉 수준의 관계

#### ▷ 매출 vs 평균 연봉 (log scale)  
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/9.png?raw=true)


※ 매출과 연봉 사이에 뚜렷한 상관관계는 보이지 않음

---

### 4. 시도별 총 매출액과 평균 연봉 비교

#### ▷ 시도별 매출 총합 및 평균 연봉
![](https://github.com/jinhyuk2me/eda-lab/blob/main/eda-project-saramin/img/10.png?raw=true)

---

## 🙋‍♂️ 기여자

<table>
  <thead>
    <tr>
      <th>이름</th>
      <th>GitHub</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td><strong>장진혁</strong></td>
      <td>
        <a href="https://github.com/jinhyuk2me">
          <img src="https://img.shields.io/badge/github-jinhyuk2me-181717?style=flat-square&logo=github&logoColor=white">
        </a>
      </td>
    </tr>
  </tbody>
</table>
