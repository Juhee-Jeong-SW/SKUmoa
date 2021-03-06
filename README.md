# 매쉬업 서비스 + 원페이지 웹 어플리케이션 SKU MOA

## 기획의도

- 해당 대학교에 관심이 있는 일반인(학부모,예비서경인), 또는 재학생들에게 필요한 정보들을 담는 원페이지 사이트 개발
- 기존에 나와있는 API를 활용하여 다양한 정보를 원페이지에 담아 한번에 제공하여 원하는 정보를 쉽고 편하게 접근하도록 함

## 웹페이지 구성

- D-DAY
- 공지사항 및 퀵링크
- 날씨 API
- 밥대생 API
- 버스 API
- 다음지도 API
- 도서관 좌석정보
- 인스타그램 피드

## 각 기능 설명

### 날씨

- 목적
  * 날씨를 예측하고 이에 맞춰 준비할 수 있도록 일기 예보를 제공한다.
- 내용
  * Openweathermap API 연동
  * 상단에는 현재의 날짜와 지역을 기준으로 날씨 상태 및 온도의 정보를 나타내어 준다. 
  * 하단에는 일기 예보 형식으로 하여 당일을 기준으로 일주일치 날씨 상태 및 온도 정보를 제공한다.
  * 오늘의 날씨 정보에서 온도와 날씨 상태는 실시간으로 반영되어 사용자가 매시간마다 날씨 변화를 파악할 수 있다.
  
### 오늘 뭐 먹지?

- 목적
  * 학식정보를 제공함으로써 학생들이 식당을 선택할 때 도움을 준다.
- 내용
  * 밥대생 API연동을 통해 식단정보 출력
  * 학교 각 식당의 식단정보를 슬라이드 형식으로 정보제공
  * 버튼클릭을 통해 2일치 식단정보 추가제공
  
### 실시가 버스 도착 알리미

- 목적
  * 학교를 순환하는 버스들(1164, 2115, 셔틀버스)의 도착 예정 시간을 제공한다.
- 내용
  * 다른 경로를 배제하고 오직 학교를 기준으로 한 주된 정류소에서의 버스 도착 예정 시간을 나타내어 이를 사용자들이 쉽게 비교하며 이용할 수 있도록 한다.
  * 등교 시 버스 운행 복잡도를 고려하여 13시 이전에는 등교 시 버스 예정 시간 즉, 길음역부터 서경대까지의, 성신여대입구역부터 서경대까지의 1164, 2115 도착 정보 시간 및 길음역에서의 셔틀버스 출발 시간을 제공한다.
  * 13시 이후에는 서경대를 중점으로 1164와 2115 도착예정 시간을 제공한다. 이 때 학교에서 출발하는 셔틀버스의 시간은  따로 정해져있지 않으므로 제공하지 않는다.
  * 페이스북 혹은 대자보에만 게시되어 있던 셔틀버스 운행 시간표를 단순 이미지가 아닌 웹 페이지의 한 요소로 등록하여 사용자들이 이용할 수 있도록 한다.
  * 기존에 고정된 셔틀버스 시간표를 이용하여 각 시간대별로 이용 가능한 셔틀버스와 그 셔틀버스의 출발 예정 잔여 시간을 제공한다.

### 지도

- 목적
  * 학교 주변 편의시설 등의 정보와 위치를 제공한다.
- 내용
  * 학교를 중심으로한 지도를 띄워 사용자들이 학교근처의 정보들을 우선적으로 볼 수 있게 한다.
  * 학교 마커인 skon을 클릭하면 인포윈도우가 생성되고 그 안에 ‘서경대 길찾기’링크가 있는데,  해당 위치를 목적지로 지정한 상태의 길찾기 URL이 들어있다.
  * 지도 안에 카테고리를 선택할 수 있는 버튼을 넣어 사용자들이 원하는 카테고리의 정보만 제공해준다.
  * 컨트롤버튼으로 지도의 확대/축소를 쉽게 하도록 도와준다.
  * drag on/off버튼을 추가하여 사용자가 모바일에서 사용할 때, 스크롤에 방해 되지 않게 한다. 

### 학사일정을 이용한 D-day

- 목적
  * 중요하다고 생각되는 내용에 대해 남은 날짜를 표시해주기 위함
- 내용
  * 본교 홈페이지의 학사일정 내용을 가져와 원하는 정보를 추출 현재의 날짜와 비교해 가장 가까운 날짜에 대해 남은 일자를 보여준다.
  * 연도가 바뀌어 학사일정이 변경되었을 경우 새로 정보를 가져와야 하기때문에 파일 이름을 연도로 했으며 파일이 없을경우 php에서 python을 실행시켜 파일을 만든뒤 파일의 내용을 불러온다.

### 도서관 좌석 정보 현황

- 목적
  * 도서관 좌석정보가 학술정보관 사이트에 있는데 학생들이 잘 모르기 때문에 보여주기 위함
- 내용
  * 학술정보관 페이지에 있는 도서관 좌석정보(열람실 상태,전체좌석,사용좌석,잔여좌석,날짜)를 가져와 보여줌
  

## 구현 결과
<img width="200" alt="그림1" src="https://user-images.githubusercontent.com/70262329/91384801-70828200-e86a-11ea-9249-734bb65bfffc.png"> <img width="200" alt="그림2" src="https://user-images.githubusercontent.com/70262329/91384803-71b3af00-e86a-11ea-9345-08d7b64bf3ef.png"> <img width="200" alt="그림3" src="https://user-images.githubusercontent.com/70262329/91384805-72e4dc00-e86a-11ea-8d44-9ebc46265a3b.png"> <img width="200" alt="그림4" src="https://user-images.githubusercontent.com/70262329/91384808-737d7280-e86a-11ea-888d-f0c2a0308b4c.png"> <img width="200" alt="그림5" src="https://user-images.githubusercontent.com/70262329/91384810-74ae9f80-e86a-11ea-90e5-524ce8df0cd1.png"> <img width="200" alt="그림6" src="https://user-images.githubusercontent.com/70262329/91384814-75dfcc80-e86a-11ea-9671-309777384782.png"> <img width="200" alt="그림7" src="https://user-images.githubusercontent.com/70262329/91384816-75dfcc80-e86a-11ea-8aaf-19295f363e9f.png"> <img width="200" alt="그림8" src="https://user-images.githubusercontent.com/70262329/91384818-76786300-e86a-11ea-95e7-79a2d84b5432.png"> <img width="200" alt="그림9" src="https://user-images.githubusercontent.com/70262329/91384819-7710f980-e86a-11ea-87cd-ae101699e026.png"> <img width="200" alt="그림10" src="https://user-images.githubusercontent.com/70262329/91384822-77a99000-e86a-11ea-8560-22aeeb02c2d1.png">

2018-sku i&amp;c summer internship
