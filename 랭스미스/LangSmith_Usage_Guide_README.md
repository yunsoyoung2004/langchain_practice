
# LangSmith 플랫폼 사용 가이드

LangSmith는 LLM 기반 애플리케이션의 **디버깅, 테스트, 모니터링**을 지원하는 플랫폼입니다. LangChain과 통합하여 LLM 애플리케이션의 품질을 높이는 데 유용합니다.

---

## 📌 1. LangSmith란?

LLM 앱 개발 시 필요한 다음과 같은 기능들을 제공합니다:

| 기능 | 설명 |
|------|------|
| ✅ 실행 횟수(run count) | 각 실행 단위의 횟수를 집계 |
| ✅ 지연 시간(latency) | P50, P99 기준 응답 지연 시간 측정 |
| ✅ 토큰 사용량(token usage) | 애플리케이션 요청당 사용한 토큰 수 분석 |

- LLM 응답에 대한 평가 기준(metric)을 LangChain 코드에 연동 가능
- 체인, 프롬프트, 대화 이력 등을 기록하여 비교 및 분석 가능

---

## 🧩 2. LangSmith vs Playground

| 항목 | LangChain Playground | LangSmith |
|------|----------------------|-----------|
| 주요 목적 | LLM 앱 프로토타입 개발 | LLM 앱 모니터링, 디버깅 |
| 기능 | 체인 실행, 실험 | 실행 로그, 성능 평가, 지속적 개선 |
| 특징 | 실행 기능 중심 | 성능과 문제 분석 중심 |

---

## 🔧 3. LangSmith 설정 및 디버깅

### 📦 필수 라이브러리 설치

```bash
pip install langchain langsmith langchainhub langchain-openai tiktoken pandas duckduckgo-search langchain_community
```

---

### ⚙️ 환경 변수 설정

```python
import os
os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_PROJECT"] = "your_project_name"
os.environ["LANGCHAIN_ENDPOINT"] = "https://api.smith.langchain.com"
os.environ["LANGCHAIN_API_KEY"] = "..."
os.environ["OPENAI_API_KEY"] = "sk-..."
```

---

### 🌐 LangSmith 클라이언트 생성

```python
from langsmith import Client
client = Client()
```

---

## 🔍 4. LangSmith + Agent 디버깅 예시

### 🧠 DuckDuckGo + GPT-4o 기반 ReAct 에이전트 구성

```python
from langchain import hub
from langchain.agents import AgentExecutor, create_react_agent
from langchain_community.tools import DuckDuckGoSearchResults
from langchain_openai import ChatOpenAI
from langchain_core.prompts import PromptTemplate

llm = ChatOpenAI(model="gpt-4o", temperature=0)
tools = [DuckDuckGoSearchResults(name="duck_duck_go")]

template = '''
가능한 최선의 답변을 제공하되, 다음 도구들을 사용하세요:
{tools}
Question: {input}
Thought: 먼저 문제를 분석해야 합니다.
Action: 적절한 도구 선택 → 실행
...
'''

prompt = PromptTemplate.from_template(template)
agent = create_react_agent(llm, tools, prompt)
executor = AgentExecutor(agent=agent, tools=tools)
```

---

## 🧪 5. 실행 결과 디버깅 (Tracing)

1. [LangSmith 접속](https://smith.langchain.com)
2. 왼쪽 메뉴에서 `Tracing projects` 클릭
3. 프로젝트 선택 (`pr-vengeful-questionnaire-*`)
4. 실행 결과에서 `AgentExecutor` 클릭
5. 실행 단계별 Input, Output, 오류 발생 시점, 토큰 사용량 등 확인 가능

스크린샷 참고:
```
[✓] 실행 단계 트리
[✓] 중간 Thought/Action 로그
[✓] 토큰 사용량 비교
```

