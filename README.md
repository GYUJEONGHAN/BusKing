# BusKing

### 개요
 - 실시간 버스 위치 정보를 이용한 버스 알람 앱
### 구성원
 - 프론트: 한규정, 홍성산
### 상세 내용
 - 기능: 공공데이터포털 API 활용한 실시간 버스 위치정보 호출 및 디바이스 로컬 알림 기능
 - 개발 플랫폼: Flutter(Android, IOS)

### API 사용 및 관련 기능 정리
1. 드롭박스 혹은 사용자 텍스트 입력으로 탑승하고자 하는 버스 번호 획득
2. 버스 번호로 경기도 버스 노선 조회 API 로부터 해당 버스의 노선 ID 획득
3. 노선 ID 로 경기도 버스 노선 조회 API 로부터 해당 버스 노선 전체 목록 획득 (정류소 선택 UI 구성 시 사용)
4. 정류소 선택 UI 에서 사용자 선택으로 출발, 도착 정류소 획득
5. 정류소 이름으로 버스정류소 현황 API 로부터 정류소 ID 획득
6. 정류소 ID 로 경기도 버스도착정보 API 로부터 실시간 버스도착정보 획득
    - 도착예정 버스는 버스 번호별로 2대씩 확인 가능
7. 1.에서 입력받은 버스 번호로 사용자가 탑승할 버스 특정
8. '탑승' 기능을 이용해, 사용자가 탑승하는 버스의 차량 번호를 획득
9. 5.에서 획득한 도착 버스 정류소 ID 로 경기도 버스도착정보 API 로부터 8.에서 특정한 차량 번호 등장에 대한 리스너 구현