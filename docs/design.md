설계 문서 (v2)

1. 아키텍처 설계

적용 패턴: MVC (Model-View-Controller)
적용 근거: Chap 07 아키텍처 스타일 중 MVC 패턴 적용

Model -> TodoModel, 할 일 데이터 관리 (CRUD, 필터, 정렬, 통계)
View -> TodoView, 화면 렌더링 (통계, 목록, 상태 반영)
Controller -> TodoController, 사용자 입력 처리 (추가, 삭제, 수정, 필터, 정렬)

2. 클래스 설계

TodoModel 주요 메서드
- save(): localStorage에 데이터 저장
- add(title, priority, dueDate): 할 일 추가
- delete(id): 할 일 삭제
- deleteCompleted(): 완료 항목 일괄 삭제
- toggle(id): 완료 상태 토글
- update(id, title, priority, dueDate): 할 일 수정
- filter(type): 상태별 필터링 (전체/진행중/완료/오늘/우선순위)
- sort(todos, type): 정렬 (기본순/우선순위순/마감일순)
- isOverdue(dueDate): 마감 초과 여부 확인
- getStats(): 통계 계산 (전체/진행중/완료 카운트)

TodoView 주요 속성/메서드
- currentFilter: 현재 필터 상태
- currentSort: 현재 정렬 상태
- render(): 전체 렌더링
- renderStats(): 통계 업데이트
- renderList(): 할일 목록 렌더링

TodoController 주요 메서드
- addTodo(): 할 일 추가
- deleteTodo(id): 할 일 삭제
- deleteCompleted(): 완료 항목 일괄 삭제
- completeAll(): 전체 완료 처리
- toggleTodo(id): 완료 상태 토글
- filterTodos(type, btn): 필터 변경
- sortTodos(type): 정렬 변경
- openEdit(id): 수정 모달 열기
- closeModal(): 수정 모달 닫기
- saveEdit(): 수정 저장
- toggleDark(): 다크모드 토글
- selectPriority(priority, btn): 우선순위 선택
- selectEditPriority(priority, btn): 수정 모달 우선순위 선택

3. 설계 원리 적용 (Chap 06)

SOLID 원칙 적용
- SRP (단일 책임): Model은 데이터만, View는 렌더링만, Controller는 입력 처리만 담당
- OCP (개방 폐쇄): filter() 메서드에 타입 추가만으로 필터 확장 가능
- ISP (인터페이스 분리): 각 객체가 필요한 메서드만 보유
- DIP (의존관계 역전): Controller가 Model/View를 직접 생성하지 않고 참조

결합도/응집도
- 낮은 결합도: Model/View/Controller가 독립적으로 동작
- 높은 응집도: 각 객체가 하나의 역할에 집중

4. UI 설계 원리 적용 (Chap 08)

- 단순하고 자연스럽게: Notion+Apple 스타일 미니멀 디자인
- 즉각적인 피드백: 추가/삭제/수정 즉시 화면 반영
- 오류 회복 용이: 삭제 전 confirm, 빈 입력 빨간 테두리
- 일관성 유지: 동일한 디자인 시스템 (색상, 폰트, 버튼)
- 단축 명령: 엔터키로 할 일 추가
- 접근성: 다크모드, 모바일 반응형

5. 기술 스택

- Frontend: HTML, CSS, JavaScript (순수 웹)
- 데이터 저장: localStorage (서버 없이 브라우저에 저장)
- 배포: GitHub Pages
- AI 도구: Claude (바이브코딩)

작성일: 2026-05-24