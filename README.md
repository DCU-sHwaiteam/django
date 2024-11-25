백엔드 역할: 프론트엔드와 데이터베이스 사이에서 요청을 처리하고 비즈니스 로직을 실행에 중점을 둔 역할을 수행합니다. 

!(https://github.com/DCU-sHwaiteam/django/blob/main/django%20%EA%B5%AC%EC%A1%B0.png)  → 이 사진 넣지 마세요. 발표자료준비하시는분 이해를 돕기 위해 넣은 사진입니다. 아래 계층 구조로 표현 부탁드립니다~!!
    위 django 구조를 아래와 같이 계층적으로 표현했습니다. (#: 각 파일의 역할을 간략히 설명한 것)

dcuclubs_backend/
    ├── clubs/
    │   ├── models.py        # 데이터베이스 모델
    │   ├── views.py         # 로직 처리
    │   ├── serializers.py   # JSON 직렬화
    │   ├── urls.py          # 앱 URL 라우팅
    │   └── admin.py         # 관리자 페이지
    ├── settings.py          # 프로젝트 설정
    ├── urls.py              # 메인 URL 라우팅
    └── wsgi.py              # WSGI 설정

django 프로젝트 흐름(이건 api 통신 흐름으로 바꿔서 프론트엔드에서 어떻게 요청하는지 추가해주면 좋을 것 같습니다, 다이어그램 형식으로) 
   [프론트엔드 요청 → Django URL 라우팅 → 뷰(Views) 처리 → 데이터베이스 → JSON 응답]

!(https://github.com/DCU-sHwaiteam/django/blob/main/%EB%AA%A8%EB%8D%B8%20%EA%B5%AC%EC%A1%B0%20.png)
    위 사진은 django 모델의 ERD 입니다.

Club: 동아리 정보를 저장.

Member: 회원 정보를 저장.

AttendanceRecord:출석 기록을 저장.

Activity: 동아리 활동 정보를 저장.

Participation: 회원과 활동 간의 참여 관계를 저장.

 테이블 간 관계
Member ↔ AttendanceRecord:
1:N 관계: 한 명의 회원(Member)은 여러 출석 기록(AttendanceRecord)을 가질 수 있음.

Member ↔ Participation:
1:N 관계: 한 명의 회원(Member)은 여러 활동 참여 기록(Participation)을 가질 수 있음.

Activity ↔ Participation:
1:N 관계: 하나의 활동(Activity)에 여러 회원(Participation)이 참여할 수 있음.

!(https://github.com/DCU-sHwaiteam/django/blob/main/swagger%20%ED%98%B8%EC%B6%9C.png)
      위는 Swagger UI를 통해 GET /api/attendance/1/ 요청하는 사진입니다. 

https://github.com/DCU-sHwaiteam/django/blob/main/swagger%20%ED%98%B8%EC%B6%9C%20%EA%B2%B0%EA%B3%BC.png
       위는 호출한 결과입니다.
