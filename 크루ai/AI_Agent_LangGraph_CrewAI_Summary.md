
# AI 에이전트, 랭그래프, 크루AI 요약

## 1. 광고 캠페인 설계에 활용된 에이전트 협업 예시

- 각 역할(디자인, 마케팅, PM)이 user_proxy를 통해 제안 → chat_manager가 통합.
- 제안 내용:
  - 타겟 소비자 세분화 (연령, 성별, 수준, 라이프스타일 등)
  - 시장 분석, 경쟁사 분석, 제품 차별화 전략 제안
  - 옴니채널 전략 (소셜미디어, 이메일, 검색광고 등)
  - 피드백 기반 메시지 개선 루프 시스템 도입

## 2. LangGraph 기반 에이전트 워크플로우

- StateGraph와 MessagesState를 기반으로 흐름 관리.
- 노드 정의: agent, tool
- 조건부 흐름 설정: should_continue에 따라 반복 혹은 종료
- Mermaid 다이어그램 시각화 가능
- Smith Langchain을 통한 디버깅 및 트레이싱

## 3. AI 에이전트의 정의와 활용

- 정의: 특정 작업을 수행하기 위해 설계된 소프트웨어 시스템
- 주요 기능:
  - 자동화
  - 데이터 분석 및 예측
  - 추천 시스템 및 맞춤화
  - 목적 기반 에이전트 설계
- 적용 사례: 고객 서비스, 의료, 금융, 교육, 게임 등

## 4. 크루AI(CrewAI) 개념과 구성

- 여러 에이전트를 팀으로 묶어 복잡한 작업 수행
- 구성 요소:
  - Agent (에이전트)
  - Tool (도구)
  - Task (작업)
  - Process (작업 흐름)
  - Crew (팀 단위 프레임워크)

## 5. CrewAI 실습 예시

### 실습 1: 웹 검색 기반 기사 작성
- Agent:
  - Searching: 주제 검색
  - Writing: 기사 작성
- Task:
  - search_task: 키워드 중심 웹 검색
  - answer_task: 구조화된 기사 작성
- Process: 순차적 실행 (sequential)
- Tools: Serper API (구글 검색 API)

### 실습 2: 유튜브 영상 분석 기사 작성
- Agent:
  - searching: 유튜브에서 전문가 수준 콘텐츠 검색
  - answer: 유튜브 주제 기반 기사 작성
- Tool: YoutubeChannelSearchTool
- 목표: 특정 채널의 영상 요약 및 기사 생성

## 6. 랭그래프 + Langsmith 디버깅 및 평가

- Tracing Projects에서 실습 실행 상태 확인
- LangGraph 사용 시 상태 흐름 및 비용(토큰) 확인
- LLM 응답 평가 위한 정답 생성 코드 제공

---

> 본 요약은 마케팅 캠페인 설계 예시부터 LangGraph 기반 AI 에이전트 실행, 크루AI 프레임워크 적용 및 실습 예시까지를 종합적으로 다룹니다.
