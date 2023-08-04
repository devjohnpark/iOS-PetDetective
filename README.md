# 📌 Capston Design
## 📱 유실·유기견을 빠른 실내에 찾게 도와주는 iOS앱

#### 유실 유기견의 문재
강아지의 활동반경이 넓음 
-> 시간이 지날수록 찾아야하는 반경이 커지고 생존 확률도 떨어짐 
-> 골든 타임이 매우 중요 (3시간)

<br/>

### 기존 유실 유기견 찾아주는 서비스: 
보호자가 글을 쓰면 다른 사용자가 해당 글을 들어가서 
직접 확인하고 연락을 취하는 방식
-> 지역도 시 단위로 넓은 범위 
-> 찾는 보호자 입장에 찾아야 할 범위, 들이는 시간, 비용 증가

<br/>

### 해당 펫 탐정소 앱 차별성:
머신 러닝 활용
Teachalbe machine(machine learning)을 학습시칸 모델로  강아지의 품종, 털색을 검출
사용자가 신고한 유실견과 실종견 매치하여 유사도 검증 및 노출

보호자가 글을 쓴 시각과 위치를 기반 
-> 일정거리 안의 앱 사용자에게 실시간 알림 
-> 정보를 받은 앱 사용자가 반려동물의 정보, 잃어버린 위치 등을 활용하여 골든 타임 내에 빠른 대처가 가능

<br/>

### 핵심 기능(담당 작업)
1. 유실·유기견 탐색 위치 설정 및 수정 기능
2. 애완동물 실종/발견 위치 설정
3. 긴급 구조 맵 뷰 (골든 타임 이내에 구조 도움) 구현 및 실시간 알림 연동

<br/>

### 기능의 상세 설명(담당 작업)
1. 긴급구조 맵뷰(의뢰 신고) | 앱의 핵심 기능

        * 사용자 근처의 의뢰/목격 신고된 유실·유기견들 맵뷰 위에 개의 사진 Annotaion 표시
        * 의뢰/목격 신고된 유실·유기견 정보(실종/목격 좌표, 시간, 사례금) 조회
        * 의뢰/목격 신고된 유실·유기견 신고글 조회
        * 실종 신고에는 골든타임 (3시간)이 가장 중요함으로 타이머로 남은 골든타임 표시
    
2. 맵, 위치 기능 (UIKIt, CoreLocation, Naver Map Api)
        
        * 모둘화: Map과 Location 관련 코드 같은 경우 긴급 구조 맵뷰, 탐색 위치 설정, 실종 / 발견 위치 설정 여러 곳에 쓰이기 때문에 맵, 위치 관련 기능 모듈화 시킴 
        * 객체 지향 프로그래밍: Map, Location Controller에 해당하는 클래스 캡슐화, 상속
        * Get 요청 후 객체를 마커에 저장후  Naver Map View에 마커로 정보 표시
        
3. 타이머 기능 (골든 타임 관련)
        
        * 각 마커 객체에 해당하는 타이머 기능 (골든타임의 남은 시간)
        
4. Restful API 연동

        * GET: URLSession (실종/목격된 견의 해당 좌표 및 주소, 실종/목견된 견의 해당 게시글)
        * PUT: Alamofire library (유실·유실견 탐색 좌표 및 주소 수정)

<br/>

### 디자인 패턴(담당 작업)
#### MVC 
1. Delegate Parttern: Geocoding한 주소와 위도, 경도 데이터 전달
2. Observer Pattern: Notification Center로 Push Notification 알람 객체 전달

<br/>

### 앱 소개 영상
[![Alt text](https://img.youtube.com/vi/2iOcF1O8Ah0/0.jpg)](https://www.youtube.com/watch?v=2iOcF1O8Ah0)

### 앱 주요 기능 GIF

인공지능(자동 견의 종, 털색 분류) 체크 및 목격 신고글 생성

![인공지능_체크_및_글_생성_MP4_AdobeExpress](https://user-images.githubusercontent.com/109328441/183868749-92646438-6914-4386-afd7-d63b85670184.gif)

<br/>

긴급구조 맵뷰(의뢰 신고)

![긴급구조_의뢰_AdobeExpress](https://user-images.githubusercontent.com/109328441/183868752-3eda1d27-90ae-40bd-89b2-9fceec5d5775.gif)

<br/>

푸쉬알림 읽기 및 동작

![푸쉬알림_읽음_동작_MP4_AdobeExpress](https://user-images.githubusercontent.com/109328441/183868730-8ab1fccc-6fa9-4389-9c29-a5ecc22ed64b.gif)
