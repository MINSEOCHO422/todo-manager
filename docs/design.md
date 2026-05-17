\설계 문서



\1. 아키텍처 설계



\- 적용 패턴: MVC (Model-View-Controller)

\- 적용 근거: Chap 07 아키텍처 스타일 중 MVC 패턴 적용

&#x20; - Model: 할 일 데이터 관리 (TodoModel)

&#x20; - View: 화면 렌더링 (TodoView)

&#x20; - Controller: 사용자 입력 처리 (TodoController)



\2. 클래스 설계



\TodoModel

| 속성/메서드 | 설명 |

|------------|------|

| id | 할 일 고유 번호 |

| title | 할 일 제목 |

| priority | 우선순위 (높음/중간/낮음) |

| dueDate | 마감일 |

| completed | 완료 여부 |

| createdAt | 생성일 |



\TodoController

| 메서드 | 설명 |

|--------|------|

| addTodo() | 할 일 추가 |

| updateTodo() | 할 일 수정 |

| deleteTodo() | 할 일 삭제 |

| toggleComplete() | 완료 상태 변경 |

| filterTodos() | 상태별 필터링 |



\TodoView

| 메서드 | 설명 |

|--------|------|

| render() | 화면 전체 렌더링 |

| renderTodoItem() | 개별 할 일 카드 렌더링 |

| showForm() | 입력 폼 표시 |



\3. 설계 원리 적용



\- \*\*단일 책임 원칙 (SRP)\*\*: Model/View/Controller 역할 분리

\- \*\*개방 폐쇄 원칙 (OCP)\*\*: 필터링 기능 확장 가능한 구조

\- \*\*낮은 결합도\*\*: Controller가 Model과 View를 연결하되 직접 의존 최소화

\- \*\*높은 응집도\*\*: 각 클래스가 하나의 역할만 수행



\4. UI 설계 원리 적용 (Chap 08)



\- 단순하고 자연스러운 인터페이스

\- 즉각적인 피드백 (추가/삭제 즉시 반영)

\- 오류 회복 용이 (삭제 전 확인)

\- 일관된 UI 요소 사용



\## 작성일



2026-05-17

