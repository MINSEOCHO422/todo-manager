개발 토의 기록

1. 프로젝트 방향 설정 (2026-05-17)

협업툴 기획 논의 중 과제용 SW로 할 일 관리 웹앱 선정
선정 이유: 소프트웨어 공학 프로세스 전 단계 적용 가능, 구현 난이도 적절
개발 언어: HTML/CSS/JavaScript (순수 웹 프론트엔드)
아키텍처: MVC 패턴 적용
형상관리: GitHub 레포 생성 (MINSEOCHO422/todo-manager)
AI 도구: Claude (Anthropic)


2. 요구분석 단계 토의 (2026-05-17)

Chap 04 요구분석 방법론 적용
액터: 사용자 1명 (단일 사용자 앱)
유스케이스 7개 도출 (UC-01 ~ UC-07)
포함 관계: UC-01 할일 추가 -> UC-05 우선순위 설정, UC-06 마감일 설정
확장 관계: UC-04 완료 처리 -> UC-07 필터링
기능 요구사항 7개, 비기능 요구사항 4개 정의


3. 설계 단계 토의 (2026-05-17)

Chap 07 MVC 패턴 선택 이유: UI와 비즈니스 로직 분리로 유지보수성 향상
Chap 06 SOLID 원칙 적용 계획 수립
SRP: Model/View/Controller 역할 분리
OCP: filter() 메서드 확장 가능한 구조
결합도 낮추기: Controller가 Model/View를 직접 생성하지 않고 참조


4. 구현 단계 토의 (2026-05-19 ~ 05-22)

바이브코딩으로 Claude에게 코드 생성 요청
초기 구현 후 발견된 문제점 및 개선 사항 토의

문제1: toggleDark() 함수가 TodoController 객체 외부에 정의되는 오류 발생
원인: 설계 없이 기능 추가하다 발생한 구조적 오류
해결: saveEdit() 함수 다음에 올바른 위치에 재배치

문제2: iOS에서 min 속성이 무시되어 과거 날짜 선택 가능
원인: iOS 내장 달력 피커가 브라우저 속성 무시
해결: JS 유효성 검사로 방어적 코딩 적용 (오늘 이후 날짜만 추가 가능)

문제3: 맥/윈도우 간 작업 시 Merge Conflict 발생
원인: 두 환경에서 동시에 작업하여 GitHub 충돌
해결: git pull --rebase 후 push


5. UI/UX 개선 토의 (2026-05-20 ~ 05-22)

초기 UI가 단순하고 사용자 친화적이지 않다는 판단
Chap 08 UI설계 원칙 재검토
개선 방향: Notion + Apple 스타일 (미니멀, 직관적)
주요 변경사항
- 드롭다운 우선순위 선택 -> 탭 버튼 3개로 변경 (직접 조작, 즉각 피드백 원칙)
- 통계 카드 추가 (전체/진행중/완료)
- 다크모드 추가 (localStorage 유지)
- 모바일 반응형 추가


6. 품질관리 토의 (2026-05-21 ~ 05-23)

Chap 12 인스펙션 방법론 적용
교수님 강조 사항 반영
- 인스펙션은 행위(실행) 기반이 아닌 정적 분석으로 수행
- 사이클로매틱 복잡도 분석으로 코드 안전성 증명
- 테스트 조건 먼저 설정 후 범위 한정하여 검증

정적 분석 결과
- filter() 함수: V(G) = 6, 허용 범위 내
- addTodo() 함수: V(G) = 5, 적정 수준
- isOverdue() 함수: V(G) = 2, 단순하고 안전

코드 안전성 확인
- isOverdue(): dueDate null 체크 후 false 반환 -> null 참조 오류 없음
- filter(): 알 수 없는 type 입력 시 전체 목록 반환 -> 예외 상황 안전
- toggle(), update(): id 미발견 시 조기 반환 -> null 참조 오류 없음


7. Polyglot Architecture 토의 (2026-05-24)

현재 구조: 단일 언어(JavaScript) 단순 구조
단일 사용자 로컬 환경이므로 JavaScript 단일 언어 구조 적합
향후 확장 시 필요한 Polyglot 구조
- Node.js (서버)
- JavaScript (클라이언트)
- SQL (데이터베이스)
분산 병렬 환경 확장 시 Erlang 계열 언어 도입 검토 필요


8. 최종 점검 (2026-05-24)

GitHub Pages 배포 완료
URL: https://MINSEOCHO422.github.io/todo-manager/
모바일/데스크탑 동작 확인
다크모드 localStorage 유지 확인
최종 커밋 기록 정리 완료