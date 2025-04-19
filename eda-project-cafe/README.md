<p align="center">
  <img src="https://github.com/jinhyuk2me/eda-project-cafe/blob/main/img/banner.png?raw=true" width="100%">
</p>

---

# 스타벅스 vs 이디야: 입지 전략 비교 분석  
> **Store Location Analysis Project: Starbucks vs Ediya in Seoul**

---

## 🗂️ 프로젝트 개요

서울시 내 대표 프랜차이즈 카페인 **스타벅스**와 **이디야**의 매장 위치 데이터를 수집하여, **공간적 근접성**, **상권 중복도**, **입점 전략의 차이**를 정량적으로 비교 분석한 프로젝트입니다.  
주소 기반 웹 크롤링부터 좌표 변환, DB 저장, 거리 계산, 통계적 상관관계 분석, 지도 시각화까지 전 과정을 구현하였습니다.

---

## ⚙️ 기술 스택

| 분류 | 기술 | 배지 |
|------|------|------|
| **개발환경** | Ubuntu (Linux)<br>VS Code<br>Jupyter Notebook | ![Linux](https://img.shields.io/badge/linux-FCC624?style=for-the-badge&logo=linux&logoColor=black)<br>![VS Code](https://img.shields.io/badge/VSCode-007ACC?style=for-the-badge&logo=visual-studio-code&logoColor=white)<br>![Jupyter](https://img.shields.io/badge/jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white) |
| **언어** | Python 3 | ![Python](https://img.shields.io/badge/python-3776AB?style=for-the-badge&logo=python&logoColor=white) |
| **데이터 수집** | BeautifulSoup<br>Selenium<br>Naver API<br>Google Maps API | ![BeautifulSoup](https://img.shields.io/badge/BeautifulSoup-FFDB4D?style=for-the-badge&logo=python&logoColor=black)<br>![Selenium](https://img.shields.io/badge/selenium-43B02A?style=for-the-badge&logo=selenium&logoColor=white)<br>![Google Maps](https://img.shields.io/badge/Google_Maps_API-4285F4?style=for-the-badge&logo=googlemaps&logoColor=white)<br>![Naver API](https://img.shields.io/badge/Naver_API-03C75A?style=for-the-badge&logo=naver&logoColor=white) |
| **데이터 분석** | Pandas<br>Numpy | ![Pandas](https://img.shields.io/badge/pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)<br>![Numpy](https://img.shields.io/badge/numpy-013243?style=for-the-badge&logo=numpy&logoColor=white) |
| **시각화** | Matplotlib<br>Folium | ![Matplotlib](https://img.shields.io/badge/matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white)<br>![Folium](https://img.shields.io/badge/folium-77B829?style=for-the-badge&logo=leaflet&logoColor=white) |
| **DB** | MySQL | ![MySQL](https://img.shields.io/badge/mysql-4479A1?style=for-the-badge&logo=mysql&logoColor=white) |
| **형상 관리** | Git / GitHub | ![Git](https://img.shields.io/badge/git-F05032?style=for-the-badge&logo=git&logoColor=white) ![GitHub](https://img.shields.io/badge/github-181717?style=for-the-badge&logo=github&logoColor=white) |

---

## 🧩 전체 분석 흐름

본 프로젝트는 매장 간 입지 관계를 파악하기 위해 **두 가지 분석 방식**을 병행하였습니다.  
각 방식은 서로 다른 관점에서 브랜드 간 전략적 분포 특성을 파악합니다.

---

### 🛣️ [1] 거리 기반 근접성 분석

> 위경도 좌표를 기준으로 이디야 매장이 스타벅스 반경 내에 얼마나 분포하는지를 정량적으로 분석합니다.

1. **매장 주소 크롤링**  
   - 스타벅스: 도로명 주소 직접 수집  
   - 이디야: 지번 주소 → 도로명 주소로 정제 필요  

2. **좌표 변환**  
   - Google Maps API 사용, 보완적으로 Naver API 및 Selenium 적용  

3. **거리 계산**  
   - Haversine 공식으로 두 좌표 간 물리적 거리 측정  
   - KDTree 기반 최근접 매장 거리 탐색  

4. **시각화 및 해석**  
   - folium 지도 시각화  
   - 거리 분포 히스토그램 (matplotlib 사용)  
   - 거리 구간별 비율 계량화  

---

### 🏙️ [2] 도로명 주소 기반 상권 중복 분석

> 동일 도로명 기준으로 두 브랜드의 매장 수를 비교하여 상권 중첩도를 파악합니다.

1. **주소 정제 및 전처리**  
   - AddressManager를 통한 지번 → 도로명 변환  
   - 서울시 도로명 필터링  

2. **도로 단위 매장 수 집계**  
   - 각 도로에 존재하는 브랜드별 매장 수 집계  

3. **상관관계 분석**  
   - Pandas 기반 매장 수 테이블 생성  
   - Pearson 상관계수 계산 → ρ ≈ 0.6937  

4. **시각화 및 해석**  
   - scatter plot 및 도로 단위 비교 시각화  
   - 동일 상권에서의 공동 진출 경향 해석  

---

## 📑 주요 분석 결과 요약

| 항목 | 결과 |
|------|------|
| **100m 이내 근접 비율** | 약 12~15% |
| **300m 이내** | 약 42~47% |
| **500m 이내** | 약 63~68% |
| **도로명 기반 매장 수 상관계수 (ρ)** | **0.6937** |
| **전략 해석** | 동일 생활권 내에서 일정 거리 유지하며 공존하는 경향 |

> 위 결과를 종합하면, 이디야는 스타벅스와 **유사한 상권을 공유하면서도 물리적 거리에는 일정 수준의 간격을 유지**하는 입점 전략을 활용하고 있는 것으로 해석됩니다.

---

## 📊 분석 및 시각화

### 📍 Figure A. 스타벅스 & 이디야 매장 위치 (folium 시각화)
![Figure A](https://github.com/jinhyuk2me/eda-project-cafe/blob/main/img/store%20map%20folium.png?raw=true)
> 지도 기반의 단순 시각화만으로는 두 브랜드의 입지 전략을 명확히 파악하기 어려우며, 서울 전역에 균일하게 분포된 것처럼 보이는 현상이 나타납니다.  
> 이에 따라 **물리적 거리 기반 분석(Haversine/KDTree)** 과 **도로명 주소 기반 상권 중복 분석**을 추가로 수행하여 두 브랜드의 실제 입지 전략을 **정량적으로 비교**하고자 하였습니다.

---

### 📊 Figure B. 최근접 스타벅스까지의 거리 분포 (이디야 기준)

| 구간 | Haversine 기반 | KDTree 기반 |
|------|----------------|-------------|
| 100m 이내 | 15.32% | 12.77% (65 / 509) |
| 300m 이내 | 47.94% | 42.83% (218 / 509) |
| 500m 이내 | 68.37% | 63.46% (323 / 509) |

> Haversine 및 KDTree 결과는 전체적으로 유사한 분포를 보이며,  
> 이디야 매장의 약 65% 이상이 스타벅스 반경 500m 이내에 위치하고 있음이 확인되었습니다.

---

### 📈 Figure C. 도로명 기준 매장 수 상관관계 분석
![Figure C](https://github.com/jinhyuk2me/eda-project-cafe/blob/main/img/correlation%20by%20region.png?raw=true)

> 도로 단위 Pearson 상관계수 **ρ ≈ 0.6937**은 통계적으로 **중강 이상의 양의 상관관계**를 의미하며,  
> 두 브랜드가 동일 도로 기반 상권을 강하게 공유하고 있음을 시사합니다.

---

## 📌 종합 정리

- 거리 기반 분석을 통해 **이디야는 스타벅스 반경 내에 높은 비율로 위치**함이 확인되었고,  
- 도로명 기반 상권 분석에서는 **같은 도로상에 매장이 함께 존재할 가능성**이 높음이 드러났습니다.  
- 이는 두 브랜드가 **생활권 및 유동 인구가 높은 동일 상권을 공략**하되, **직접적인 경쟁을 피하고자 일정 거리를 유지**하는 전략을 택했을 가능성을 보여줍니다.

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


---

## 📎 참고 및 출처

- [스타벅스 매장 찾기](https://www.starbucks.co.kr/store/store_map.do)
- [이디야 매장 찾기](https://members.ediya.com/store)
- Google Maps Geocoding API
- Naver Local Search API

