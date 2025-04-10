# LangChain 기반 AI 에이전트 가이드

본 문서는 LangChain을 활용한 AI 에이전트 구성 방식과 유형별 실행 예시를 시각적으로 정리한 README입니다.

## 📌 목차
1. [8.1 랭체인 에이전트](#8.1-랭체인-에이전트)
2. [8.1.1 랭체인 AI 에이전트 동작 방식](#8.1.1-랭체인-ai-에이전트-동작-방식)
3. [8.1.2 랭체인으로 에이전트 구현하기](#8.1.2-랭체인으로-에이전트-구현하기)
4. [Zero-shot ReAct](#zero-shot-react)
5. [Conversational ReAct](#conversational-react)
6. [Self-ask with Search](#self-ask-with-search)
7. [ReAct Docstore](#react-docstore)
8. [실행 예시: LLM-Math를 활용한 나이 계산](#실행-예시:-llm-math를-활용한-나이-계산)
9. [실행 예시: Tavily로 검색하기](#실행-예시:-tavily로-검색하기)
10. [실행 예시: Docstore로 위키 검색하기](#실행-예시:-docstore로-위키-검색하기)
11. [실행 예시: 에이전트 반복 한계 (max_iterations)](#실행-예시:-에이전트-반복-한계-(max_iterations))


---

## 1. 🧠 랭체인 에이전트란?

- 다양한 프레임워크에서 에이전트 구성 가능.
- LangChain 기반 에이전트는 `AgentExecutor`를 사용해 환경 관찰 → 판단 → 행동의 사이클을 구현.

![agent cycle](https://i.imgur.com/kl0MJBi.png)  
*에이전트 Thought → Action → Observation 순환 다이어그램*

---

## 2. ⚙️ 랭체인 에이전트 동작 흐름 (8.1.1)

```text
Thought → Action → Observation → Final Answer
```

**예시 질문:** What is an AI Agent?

- Action: wikipedia 검색
- Observation: 지식 수집
- Final Answer: 자율적 판단과 행동이 가능한 시스템

---

## 3. 🧪 Zero-shot ReAct

```python
agent = initialize_agent(
    tools,
    llm,
    agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
    handle_parsing_errors=True,
    verbose=True,
)
agent.invoke("소나무 옮겨심기 좋은 계절은?")
```

- 도구: Wikipedia, llm-math
- 목적: 간단한 자연어 명령 수행

---

## 4. 💬 Conversational ReAct

```python
agent = initialize_agent(
    agent='conversational-react-description',
    tools=tools,
    llm=llm,
    memory=ConversationBufferMemory(memory_key="chat_history"),
    max_iterations=3,
    verbose=True
)
agent.invoke("에드 시런은 누구이며 2025년 현재 나이는 몇 살이야?")
```

- 메모리 기반 멀티턴 대화
- 수학 계산도구 활용 예시 포함

---

## 5. 🔍 Self-Ask with Search

```python
agent = create_self_ask_with_search_agent(llm, tools, prompt)
agent_executor = AgentExecutor(agent=agent, tools=tools)
agent_executor.invoke({"input": "AI Agent를 세 문장으로 설명해줘"})
```

- Tavily API 기반 검색
- `create_self_ask_with_search_agent`로 구현

---

## 6. 📚 ReAct Docstore

```python
from langchain.docstore.wikipedia import Wikipedia
docstore = DocstoreExplorer(Wikipedia())

tools = [
    Tool(name="Search", func=docstore.search, description="docstore에서 용어 검색")
]
```

- 위키 기반 문서 검색 및 조회
- DocstoreExplorer로 구현

---

## 7. 🧮 LLM-Math 예시: 나이 계산

```python
Action: Calculator
Action Input: 2025 - 1991
Observation: Answer: 34
```

- 에이전트가 계산 도구를 선택해 정확한 나이 출력
- 멀티턴 대화 히스토리를 기반으로 응답 강화

---

## 8. ❗ 반복 한계 예외 처리

> Agent stopped due to iteration limit or time limit.

- max_iterations 또는 max_execution_time 값 조정 필요
