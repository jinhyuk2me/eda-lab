<p align="center">
  <img src="https://raw.githubusercontent.com/jinhyuk2me/eda-project-gasstation/main/img/banner.png" width="100%">
</p>
 

---

# 서울시 주유소 데이터 분석   
> **Exploratory Data Analysis on Gas Stations in Seoul**

---

## 🗂️ 프로젝트 개요

서울시 주유소의 **가격, 브랜드, 운영 형태, 위치 정보**를 수집·정리하여 **지역별 가격 분포와 시설 특성**을 분석한 프로젝트입니다.  
**Selenium** 기반 크롤링과 **Google Maps API**를 활용해 지도 시각화를 포함한 EDA를 수행했습니다.

---

## ⚙️ 기술 스택

| 분류 | 기술 | 배지 |
|------|------|------|
| **개발환경** | Linux (Ubuntu)<br>VS Code<br>Jupyter Notebook | ![Linux](https://img.shields.io/badge/linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)<br>![VS Code](https://img.shields.io/badge/VSCode-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)<br>![Jupyter](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white) |
| **언어** | Python 3 | ![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white) |
| **데이터 처리** | pandas<br>numpy | ![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)<br>![NumPy](https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white) |
| **시각화** | matplotlib<br>folium | ![Matplotlib](https://img.shields.io/badge/matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)<br>![Folium](https://img.shields.io/badge/folium-77B829?style=for-the-badge&logo=leaflet&logoColor=white) |
| **크롤링** | Selenium | ![Selenium](https://img.shields.io/badge/Selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white) |
| **지도 API** | Google Maps Geocoding API | ![Google Maps](https://img.shields.io/badge/Google%20Maps%20API-4285F4?style=for-the-badge&logo=googlemaps&logoColor=white) |
| **형상 관리** | Git / GitHub | ![Git](https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white) |

---

## 📥 데이터 수집 및 전처리

| 항목 | 설명 |
|------|------|
| **출처** | [Opinet](https://www.opinet.co.kr/) |
| **수집 방식** | `Selenium` 기반 웹 자동화 크롤링 |
| **수집 항목** | 주유소명, 주소, 브랜드, 유종별 가격(보통/고급/경유/등유), 24시간 운영 여부, 편의점, 세차장, 충전소, 경정비 가능 여부 |
| **좌표 변환** | Google Maps API (`googlemaps`)를 사용한 주소 → 위경도 변환 |
| **전처리** | 결측값 제거, 이상치 필터링, DataFrame 통합 등 |

---

## 🧭 분석 항목

### 📉 가격 분석
- 자치구별 **유종별 평균 가격 분석**  
- **보통휘발유 가격 기준 상/하위 20개 주유소** 비교  

### 🕘 운영 특성
- 자치구별 **24시간 운영 주유소 수**  
- 자치구별 **편의점 유무 주유소 수**  

### 🗺️ 위치 시각화
- **편의점이 있는 주유소만 필터링하여 지도 시각화**  
- **유종별 가격 분포 지도 시각화 (보통/고급/경유/등유)**

### 📈 상관관계 분석
- 유종 간 가격 상관관계 분석 (Corr Matrix & Scatter)

---

## 📑 주요 결과 요약

| 항목 | 인사이트 |
|------|----------|
| **자치구별 가격 차이** | 휘발유 가격은 자치구 간 최대 **400원 차이** 발생 |
| **브랜드 경향** | **SK에너지 / GS칼텍스**는 고가, **S-OIL / 알뜰주유소**는 저가 경향 |
| **공간 분포** | 고가 주유소는 도심 밀집, 저가 주유소는 외곽에 분포 |
| **운영 특성** | 24시간 운영 비율은 **중구/동작구/송파구**에서 높음 |
| **유종 상관성** | 가격 간 상관관계 매우 높음 (휘발유↔경유: 0.988 등) |

---

## 📊 분석 결과 시각화 (Figures A–F)

### 📊 Figure A. 주유소 유형별(셀프/일반) 보통휘발유 가격 분포
![Figure A](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/self%20vs%20general.png?raw=true)

---

### 📊 Figure B. 브랜드 및 주유 형태별 가격 차이
![Figure B](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/brand%20self%20price.png?raw=true)

---

### 📊 Figure C. 자치구별 유종별 가격 분석

#### Figure C-1. 보통휘발유 (Regular)
- 지도  
  ![Regular Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/regular%20price%20by%20gu.png?raw=true)
- 막대그래프  
  ![Regular Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/regular%20price%20by%20gu%20bar.png?raw=true)

#### Figure C-2. 고급휘발유 (Premium)
- 지도  
  ![Premium Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/premium%20price%20by%20gu.png?raw=true)
- 막대그래프  
  ![Premium Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/premium%20price%20by%20gu%20bar.png?raw=true)

#### Figure C-3. 경유 (Diesel)
- 지도  
  ![Diesel Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/diesel%20price%20by%20gu.png?raw=true)
- 막대그래프  
  ![Diesel Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/diesel%20price%20by%20gu%20bar.png?raw=true)

#### Figure C-4. 실내등유 (Kerosene)
- 지도  
  ![Kerosene Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/kerosene%20price%20by%20gu.png?raw=true)
- 막대그래프  
  ![Kerosene Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/kerosene%20price%20by%20gu%20bar.png?raw=true)

---

### 📊 Figure D. 자치구별 주유소 운영 특성

#### Figure D-1. 24시간 운영 주유소 비율
![24hr Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/24hour%20ratio%20by%20gu.png?raw=true)  
![24hr Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/24hour%20ratio%20by%20gu%20bar.png?raw=true)

#### Figure D-2. 편의점 운영 주유소 비율
![CVS Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/cvs%20ratio%20by%20gu.png?raw=true)  
![CVS Bar](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/cvs%20ratio%20by%20gu%20bar.png?raw=true)

---

### 📊 Figure E. 보통휘발유 기준 가격 상/하위 주유소

#### Figure E-1. Top 20 비싼 주유소
- 테이블  
  ![Expensive Table](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20expensive%20table.png?raw=true)
- 지도  
  ![Expensive Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20expensive%20map.png?raw=true)

#### Figure E-2. Top 20 저렴한 주유소
- 테이블  
  ![Cheap Table](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20cheap%20table.png?raw=true)
- 지도  
  ![Cheap Map](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/most%20cheap%20map.png?raw=true)

---

### 📊 Figure F. 유종 간 가격 상관관계 분석
- 상관계수 테이블  
  ![Correlation Table](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/fuel%20corr%20table.png?raw=true)
- 산점도 매트릭스  
  ![Correlation Scatter](https://github.com/jinhyuk2me/eda-project-gasstation/blob/main/img/fuel%20corr%20scatter.png?raw=true)


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

