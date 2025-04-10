
# 정치인 & 랭그래프로 AI 에이전트 개발하기 (요약)

## 멀티 에이전트 구조 실습

- **user_proxy**는 Hub 역할, 여러 AssistantAgent를 호출
- **design_agent**, **marketing_agent**, **pm_agent**는 각각 디자인, 마케팅, 프로젝트 매니징 역할
- 각 Agent는 순차적으로 메시지를 전달받아 그룹챗 형태로 작업 수행

```python
groupchat = autogen.GroupChat(
    agents=[user_proxy, design_agent, marketing_agent, pm_agent],
    max_round=4,
    speaker_selection_method=state_transition
)
```

## 에이전트 프롬프트 예시

### design_agent
- 신제품의 디자인 및 특징 강조
- 다양한 디자인 옵션 및 소비자 타깃 고려

### marketing_agent
- 슬로건: "Step into Excellence"
- 온라인/오프라인 전략 병행
- 이벤트, 프로모션 기획

### pm_agent
- 각 팀 제안 종합 및 추가 분석 지시
- 고객 피드백 시스템 개선 요청

## 랭그래프 LangGraph 워크플로우

- 상태 기반 흐름 제어 및 반복적 모델 호출 가능
- Mermaid로 워크플로 시각화

```python
workflow = StateGraph(MessagesState)
workflow.add_node("agent", call_model)
workflow.add_node("tools", tool_node)
workflow.add_edge("__start__", "agent")
workflow.add_edge("tools", "agent")
```

## 디버깅 & 성능 평가

- **LangSmith** 대시보드 연동
- 실행 과정 시각화 및 디버깅 가능
- 성능 평가 위한 Prompt 및 정답 셋 정의 필요

## LangChain + ChatOpenAI 에이전트

- `ChatPromptTemplate`을 통한 시스템/유저 메시지 구조 정의
- `StrOutputParser()`로 출력 처리
- 질문 리스트 순회하여 LLM 결과 출력

```python
prompt = ChatPromptTemplate.from_messages([...])
output_parser = StrOutputParser()
```

## AI 에이전트 정의

- 반복 작업 자동화, 데이터 분석, 의사결정 지원
- 다양한 분야(고객 분석, 로봇 운영, 마케팅 등)에서 활용 가능

### 일반적 구현 단계
1. 목적 정의
2. 에이전트 유형 선택
3. 설정 및 초기화
4. 데이터 준비
5. 학습/평가
6. 피드백을 통한 개선
