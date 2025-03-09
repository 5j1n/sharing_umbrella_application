## ✅ mobile programming - 열섬현상 커뮤니티 어플 제작
도시열섬지도, 공유우산지도, 무더위쉼터지도, 사용자 커뮤니티 및 투표서비스가 제공되는 도시열섬 어플리케이션입니다.
<br><br>

<div align="center">
  <img src="./image/IMG_1985-_online-video-cutter.com_.gif" alt="쓰랑께 소개 영상" width = "300"/>
  <img src="./image/쓰랑께소개화면.png" alt="쓰랑께 소개 화면" width = "500" />
</div>

---

### 😀 팀원 소개
| 이름   | 역할   | 프로젝트 내용                       |
|--------|--------|------------------------------------|
| 유주경 | 팀장   | 도시 열섬 현상을 지도로 표현       |
| 조성진 | 팀원   | 공유 우산 지도 프로그램 구현       |
| 김솔아 | 팀원   | 무더위 쉼터 지도 프로그램 구현     |
| 김지애 | 팀원   | 커뮤니티 프로그램 구현             |
| 김영아 | 팀원   | 살수차 투표 프로그램 구현           |

### ⏰ Develop Period
---
- Octover 2023 ~ December 2023
<br>

### 🛠️ Development Environment
---
- lang: Java 17
- IDE: Android Studio
- Android compileSdk 34
- Android tartgetSdk 34
- emulator: Pixel 7 Pro API 34
- external library : VectorChildFinder
- database: MySQL, SQLlite
<br>

### 🌳 Structure Tree
---

```
├── README.md
├── __MACOSX
│   └── final
├── app
│   ├── build
│   ├── build.gradle
│   ├── proguard-rules.pro
│   └── src
├── build.gradle
├── gradle
│   └── wrapper
├── gradle.properties
├── gradlew
├── gradlew.bat
├── local.properties
├── settings.gradle
└── vectorchildfinder
    ├── build
    ├── build.gradle
    ├── proguard-rules.pro
    └── src
```


### 🧭 Setting
---
- 해당 프로젝트 파일을 다운로드하고 API 키를 설정하는 단계를 거쳐야 실행 가능합니다.
- 맵(지도)를 어플리케이션에 띄우기 위해 **google cloud console** 에서 프로젝트 및 API 키를 발급 받습니다.
- **서울시 열린 데이터 광장**에서 openAPI를 사용하여 필요한 데이터를 받아오기 위해 API 키를 발급 받습니다. 
- AndroidManifest.xml 파일에 다음과 같은 코드를 작성합니다.
```java
    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <application>
        <!-- ... -->
        <meta-data
            android:name="com.google.android.geo.API_KEY"
            android:value="MY_API_KEY_HERE" />
    </application> 
```
- HeatShelterAPI.java 클래스에 key 변수로 서울시 api키를 적어 넣습니다.
<br>

### 📌 Main Function
---
#### **도시열섬지도**
<div align="center">
  <img src="./image/도시열섬지도.png" alt="도시 열섬 지도" />
</div>
<br>

- SVG(Scalable Vector Graphics): 각 서울시 행정구 path 지정
- Spinner 를 사용하여 “온도", “습도", “열섬" 지도 표현
- 08.14 ~ 08.20 일 데이터 CSV  데이터 사용!
- 열섬 정의 기준은 평균 온도/습도 + 각 자치구 유동인구 고려
- S-Dot  유동인구 & 도시데이터 CSV 사용 
<br>

#### **무더위쉼터지도**
<div align="center">
  <img src="./image/무더위쉼터지도.png" alt="무더위 쉼터 지도" width = "200" />
  <img src="./image/성동구.png" alt="성동구 검색 화면" width="200" />
</div>
<br>

- 열섬피해를 막기 위해 무더위 쉼터를 사용자에게 정보 제공
- 현재 사용자 위치 기준 무더위 쉼터를 Google Maps 에 표시(가장 가까운 쉼터 5곳을 초록색으로 표시)
- 쉼터 아이콘 터치시 상세 주소 및 상황 제공
- 구 별 무더위쉼터 **검색** 기능 제공
- 서울시 무더위 쉼터 open API 사용 및 데이터 parse 함수를 이용하여 전처리
<br>

#### **📌✨ 공유우산지도 (본인 업무 담당) ☂️**  
<div align="left">
  <img src="./image/공유우산지도.png" alt="공유 우산 지도" width="200" />
  <img src="./image/우산삭제.png" alt="우산 삭제 예시 화면" width="700" />
</div>

🚀 **본인이 직접 담당한 기능으로, 공유 우산 관리 시스템을 구현하였습니다.**  

✅ **주요 기능:**  
- **🌦️ 변덕스러운 날씨와 뜨거운 햇빛으로부터 시민 보호**  
- **📍 사용자 위치 기반 공유 우산 시스템 구축** (서울 시를 가정하여 임의 설정)  
- **🛠️ 우산 개수 관리 기능 추가** (최대 2개까지 대여 가능)  
- **🔄 실시간 상태 업데이트 및 사용자 편의성 개선**  
  - **우산통이 이미 존재하는 위치에서는 새 우산통 배치 불가**  
  - **우산 아이콘 클릭 시** → 우산 추가/제거 버튼 활성화  
  - **중앙 + 버튼 클릭 시** → 사용자가 직접 이름을 설정하여 우산통 배치 가능  
- **📌 직관적인 지도 기반 UI 제공**  
  - **Google Maps API 활용**하여 우산 위치를 지도에서 쉽게 조회하고 관리 가능  

💡 **공유 우산 시스템을 통해, 더욱 편리한 도시 생활을 지원합니다!** 😊

#### **커뮤니티**
<div align="center">
  <img src="./image/커뮤니티1.png" alt="커뮤니티" width="200" />
  <img src="./image/커뮤니티2.png" alt="커뮤니티" width="200" />
</div>
<br>

- 해당 지역구의 카테고리별로 게시물 **작성** 가능, 게시물 **삭제** 가능
- 카테고리 및 지역구별 **검색** 가능
- 댓글 기능 구현
- DB연동, SQL 사용
<br>

#### **살수차투표**
<div align="center">
  <img src="./image/살수차투표.png" alt="살수차 투표표" width="200" />
</div>
<br>

- 해당 지역구 사람들의 투표로 살수차 배치 고려
- 메인 화면을 통하여 투표된 지역구 조회 가능
- DB 연동, SQL 사용





