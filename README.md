# PortMatch

취업준비생 맞춤 포트폴리오 분석 및 채용 공고 매칭 서비스

지원자의 포트폴리오와 기업 데이터를 AI로 분석해 도메인을 추출하고, 같은 도메인의 기업과 지원자를 자동으로 매칭합니다.

- 기간: 2026.01.06 ~ 02.13 (6주)
- 인원: 6명 (Backend 3, Frontend 3)
- 역할: Backend, 채용 데이터 크롤러

<table> <tr> <td align="center" width="50%"> <img src="https://github.com/user-attachments/assets/6d1c4fe2-1090-40fa-b7bb-50151d59585f" alt="메인 화면" /><br /> <sub>메인 화면</sub> </td> <td align="center" width="50%"> <img src="https://github.com/user-attachments/assets/903b5396-084e-4680-b7f2-e5077bcb7b9e" alt="전체 공고 조회" /><br /> <sub>전체 공고 조회</sub> </td> </tr> <tr> <td align="center" width="50%"> <img src="https://github.com/user-attachments/assets/b31003e3-c3fc-4ef8-a82b-0131059a091e" alt="공고 상세 확인" /><br /> <sub>공고 상세 확인</sub> </td> <td align="center" width="50%"> <img src="https://github.com/user-attachments/assets/9243c22f-2148-4d70-a2d1-a5015ef89f40" alt="분석 결과" /><br /> <sub>분석 결과</sub> </td> </tr> <tr> <td align="center" width="50%"> <img src="https://github.com/user-attachments/assets/39ff7b70-eb9f-40b2-bd33-e8cc3e428430" alt="공고 확인(기업)" /><br /> <sub>공고 확인(기업)</sub> </td> <td align="center" width="50%"> <img src="https://github.com/user-attachments/assets/ccc8826d-981c-472d-a74b-47a8424497cb" alt="공고 지원자 확인(기업)" /><br /> <sub>공고 지원자 확인(기업)</sub> </td> </tr> </table>


## 주요 기능


- 포트폴리오 AI 분석, 도메인 추출
- 기업-지원자 자동 매칭
- 채용공고 검색, 기술스택 필터, 최신순 조회
- 공고 스크랩, 인기 공고 조회
- 면접 일정 관리

## 기술 스택

| 구분 | 기술 |
|---|---|
| Frontend | React |
| Backend | Spring Boot, JPA, PostgreSQL |
| AI 분석 | FastAPI (LangChain) |
| 크롤러 | Python (requests) |
| Infra | Docker, GitLab CI/CD, EC2 |

## 담당 범위

**REST API (Spring Boot / JPA)**
- 채용공고 CRUD: 검색, 기술스택 필터, 최신순 페이지네이션, 조회수
- 만료 공고 자동 비활성화 (`@Scheduled`, 매일 자정)
- 인기 공고 조회 (스크랩 수 집계), 스크랩 토글
- 기업 CRUD, 면접 일정 CRUD (중복 등록 방지), 기술스택 CRUD

**채용 데이터 크롤러 (Python)**
- 수집 → 전처리 → 기술스택·회사·공고 DB 적재 → 분석 API 호출 순서의 파이프라인
- 적재 시 중복 체크(갱신 / 스킵 / INSERT)
- Docker로 묶어 EC2에서 crontab으로 매일 새벽 4시에 자동 실행

> 원 프로젝트에서 커밋 히스토리 없이 옮겨 온 레포입니다.
