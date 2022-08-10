# 📌 Capston Design
## 유실·유기견을 빠른 실내에 찾게 도와주는 iOS앱

### 핵심 기능(담당 작업)
1. 유실·유기견 탐색 위치 설정 및 수정 기능
2. 애완동물 실종/발견 위치 설정
3. 긴급 구조 맵 뷰 (골든 타임 이내에 구조 도움) 구현 및 알림 연동

<br/>

### 기능의 상세 설명(담당 작업)
1. 유저 디폴트
2. 맵, 위치 기능 (UIKIt, CoreLocation, Naver Map Api)
        
        * 모둘화: Map과 Location 관련 코드 같은 경우 긴급 구조 맵뷰, 탐색 위치 설정, 실종 / 발견 위치 설정 여러 곳에 쓰이기 때문에 맵, 위치 관련 기능 모듈화 시킴 
        * 객체 지향 프로그래밍: Map, Location Controller에 해당하는 클래스 캡슐화, 상속
        * Get 요청 후 객체를 마커에 저장후  Naver Map View에 마커로 정보 표시
        
3. 타이머 기능 (골든 타임 관련)
        
        * 각 마커 객체에 해당하는 타이머 기능 (골든타임의 남은 시간)
        
4. Restful Api 연동

        * GET: URLSession (실종/목격된 견의 해당 좌표 및 주소, 실종/목견된 견의 해당 게시글)
        * PUT: Alamofire library (유실·유실견 탐색 좌표 및 주소 수정)

<br/>

### 디자인 패턴(담당 작업)
#### MVC 
1. Delegate Parttern: Geocoding한 주소와 위도, 경도 데이터 전달
2. Observer Pattern: Notification Center로 Push Notification 알람 객체 전달

<br/>

### 앱 주요 기능 영상

인공지능(자동 견의 종, 털색 분류) 체크 및 목격 신고글 생성

![인공지능_체크_및_글_생성_MP4_AdobeExpress](https://user-images.githubusercontent.com/109328441/183868749-92646438-6914-4386-afd7-d63b85670184.gif)

<br/>

긴급구조 맵뷰(의뢰 신고)

![긴급구조_의뢰_AdobeExpress](https://user-images.githubusercontent.com/109328441/183868752-3eda1d27-90ae-40bd-89b2-9fceec5d5775.gif)

<br/>

푸쉬알림 읽기 및 동작

![푸쉬알림_읽음_동작_MP4_AdobeExpress](https://user-images.githubusercontent.com/109328441/183868730-8ab1fccc-6fa9-4389-9c29-a5ecc22ed64b.gif)
