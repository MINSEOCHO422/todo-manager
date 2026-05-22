# 📝 할 일 관리 웹앱 (Todo Manager)

> 소프트웨어 공학 프로세스를 적용한 바이브코딩 실습 프로젝트

## 프로젝트 개요

소프트웨어 공학의 개발 프로세스(요구분석 → 설계 → 구현 → UI설계 → 품질관리)를
Claude AI를 활용한 바이브코딩 방식으로 적용하여 제작한 할 일 관리 웹 애플리케이션입니다.

## 🌐 배포 주소

https://MINSEOCHO422.github.io/todo-manager/

## 사용 기술

- Frontend: HTML, CSS, JavaScript
- 아키텍처: MVC 패턴
- 데이터 저장: localStorage
- AI 도구: Claude (Anthropic)
- 형상관리: GitHub

## 적용 프로세스

| 단계 | 내용 | 적용 교재 챕터 |
|------|------|--------------|
| 요구분석 | 유스케이스 다이어그램, 요구 명세 | Chap 04, 05 |
| 설계 | MVC 패턴, 클래스 다이어그램 | Chap 06, 07 |
| 구현 | 코딩 표준, SOLID 원칙 적용 | Chap 09 |
| UI 설계 | 사용성 원칙, UI 요소 설계 | Chap 08 |
| 품질 관리 | 코드 인스펙션, 리팩토링 | Chap 12 |

## 주요 기능

- 할 일 추가 / 수정 / 삭제
- 완료 여부 체크
- 우선순위 설정 (높음 / 중간 / 낮음)
- 마감일 설정 (오늘 이후만 선택 가능)
- 상태별 필터링 (전체 / 진행중 / 완료 / 오늘)
- 우선순위순 / 마감일순 정렬
- 전체 완료 처리 / 완료 항목 일괄 삭제
- 통계 표시 (전체 / 진행중 / 완료 카운트)
- 다크모드 (설정 유지)
- 모바일 반응형

## 프로젝트 구조

\`\`\`
📁 todo-manager
├── 📁 docs
│   ├── requirements.md   # 요구사항 명세서
│   ├── design.md         # 설계 문서
│   └── inspection.md     # 품질 인스펙션 결과
├── 📁 src
│   └── index.html        # 메인 소스코드
├── index.html            # GitHub Pages 배포용
└── README.md
\`\`\`

## 개발 기간

2026년 5월 ~ 2026년 6월

## 관련 문서

- [요구사항 명세서](docs/requirements.md)
- [설계 문서](docs/design.md)
- [품질 인스펙션 결과](docs/inspection.md)