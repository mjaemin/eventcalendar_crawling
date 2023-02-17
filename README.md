# eventcalendar_crawling

## 사용법
### 1. 공공데이터 xml 크롤링
- 공공데이터API (http://apis.data.go.kr)에서 해당 API 접근한다.
- 카테고리별로(국경일, 기념일 등) xml import를 한다.
- ".//item"위치에 있는 모든 데이터를 변환한다.
    - 도큐먼트 설명
        - ..dateKind : {1:국경일, 2:공휴일, 3:기념일, 4:24절기, 5:잡절}
            - 단, 중복되는 항목이 존재함
        - ..dateName : 특일 이름
        - ..isHoliday : 공휴일 유무
        - ..locdate : 날짜
        - ..seq : 순번
        - ..remarks : 비고

### 2. 1번의 방법 * 국경일, 공휴일, 기념일, 24절기, 잡절
1. 국경일: http://apis.data.go.kr/B090041/openapi/service/SpcdeInfoService/getHoliDeInfo
2. 공휴일: http://apis.data.go.kr/B090041/openapi/service/SpcdeInfoService/getRestDeInfo
3. 기념일: http://apis.data.go.kr/B090041/openapi/service/SpcdeInfoService/getAnniversaryInfo
4. 24절기: http://apis.data.go.kr/B090041/openapi/service/SpcdeInfoService/get24DivisionsInfo
5. 잡절: http://apis.data.go.kr/B090041/openapi/service/SpcdeInfoService/getSundryDayInfo

### 3. csv export
- 한 테이블로 통합하여 csv export