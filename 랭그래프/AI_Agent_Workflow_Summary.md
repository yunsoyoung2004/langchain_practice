
# LangGraph 기반 AI 에이전트 워크플로우 요약

## 1. 플래너 에이전트 구성
- **목표 입력**: 사용자 질문을 받아 계획 수립
- **계획 수립**: 단계별 수행 계획 생성 (`first_plan_step`)
- **계획 실행**: 단계별 실행 및 결과 저장 (`execute_step`)
- **계획 갱신**: 필요시 응답 또는 계획 갱신 (`edited_plan_step`)
- **종료 조건**: 응답이면 종료, 아니면 계속 실행 (`should_end`)

## 2. RAG 기반 검색 에이전트 구성
- 웹 데이터 및 문서 데이터를 활용한 검색 기반 응답 생성
- 주요 컴포넌트
  - `WebBaseLoader`: 웹 페이지 텍스트 수집
  - `RecursiveCharacterTextSplitter`: 긴 문서를 청크로 분할
  - `Chroma`: 벡터 저장소 생성 및 검색
  - `PromptTemplate`: LLM 입력 템플릿
  - `JsonOutputParser`: 응답 평가에 사용
- 워크플로우 노드: `retrieve → relevant_documents → websearch (조건부) → write`

## 3. 멀티에이전트 구성
- **질문 분석 에이전트** (`analyze_question`)
  - 질문이 기술 관련이면 `code_agent`, 일반 질문이면 `generic_agent`로 분기
- **code_agent**: 코드 생성형 응답 생성
- **generic_agent**: 일반 질문에 대한 응답 생성
- 분기 조건은 LLM이 프롬프트 기반으로 판단 (`PromptTemplate` 사용)

## 4. 워크플로우 시각화 및 실행
- `graph.get_graph().draw_mermaid_png()`로 시각화
- `app.stream()` 또는 `graph.invoke()`로 실행
- `StateGraph`를 통해 노드 및 조건부 흐름 설정

## 예시 질문 처리 흐름
- “일본 온천 여행하기 좋은 계절은?” → 플래너 에이전트로 계절별 조건 조사 및 추천
- “프롬프트란?” → generic_agent로 설명 제공
- “숫자를 입력받아 Python 코드 작성” → code_agent로 단계별 코드 응답 생성


