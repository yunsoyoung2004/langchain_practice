
# 🧠 AI 에이전트 프레임워크 가이드북 요약

이 문서는 AutoGPT, LangChain, LangGraph, CrewAI, LlamaIndex 등의 주요 AI 에이전트 프레임워크와 API 키 발급 및 구글 코랩 환경 구성에 대한 실습 내용을 시각적으로 요약한 README 파일입니다.

---

## 🔧 Chapter 7. AI 에이전트를 사용하기 위한 준비

### 7.1 코랩 환경 구성

#### ✅ 코랩 접속하기
- [Colab URL](https://colab.research.google.com/?hl=ko)에 접속
- 로그인 후 `File > New Notebook` 선택
- 새 셀에 코드 입력 후 `Shift + Enter`로 실행

#### ✅ 구글 드라이브 연동
- [Google Drive](https://drive.google.com) 접속 → '내 드라이브' 클릭
- 새 폴더 `store` 생성 후 실습용 PDF 업로드

---

### 7.2 API 키 발급

#### 🔐 7.2.1 OpenAI API 키 생성
- [OpenAI 플랫폼](https://platform.openai.com) → 로그인
- Dashboard → API Keys → `Create new secret key`

#### 🔐 7.2.2 Tavily API 키 생성
- [Tavily](https://app.tavily.com/home) → Sign up → Dashboard → API Keys 클릭

#### 🔐 7.2.3 LangSmith API 키 생성
- [LangSmith](https://www.langchain.com/langsmith) → Google 계정으로 로그인
- Get Started 클릭 → `Generate API Key`

#### 🔐 7.2.4 Serper API 키 생성
- [Serper](https://serper.dev) → 계정 생성 후 이메일 인증
- Dashboard → API Key 복사

---

## 🤖 주요 프레임워크 개요

### 6.1 오토젠 (AutoGen)
- 멀티에이전트 AI 시스템 구성용 오픈소스 프레임워크
- 예: `UserProxyAgent → AssistantAgent → LLM` 흐름
- 특징: 역할 기반 구조

### 6.2 랭체인 (LangChain)
- LLM 기반 앱을 빠르게 개발
- 기능: Prompt 관리, 체인 구성, 도구 호출, 메모리 저장, 문서 로더, 검색

### 6.3 랭그래프 (LangGraph)
- 상태 기반 워크플로 관리
- 기능: 작업 재계획 (Replan), 반복 (Iterate), 분기 (Branch)

### 6.4 크루AI (CrewAI)
- 팀 기반 에이전트 구성 (Agent, Task, Crew로 조직)
- Python 예시:
```python
from crewai import Agent, Task
writer_agent = Agent(role='Writer', goal='보고서 작성', tools=['문서 편집기'])
write_task = Task(description='결과 기반 보고서 작성', agent=writer_agent)
```

### 6.5 라마인덱스 (LlamaIndex)
- LLM과 외부 데이터를 연결하는 라이브러리
- 기능: 인덱싱, 질의 응답, 에이전트 통합

### 6.6 오토GPT (AutoGPT)
- 자율형 AI 에이전트
- 예: "1주일 다이어트 식단 계획 + PDF 저장"
    1. 인터넷 트렌드 검색
    2. 식단 구성
    3. PDF 변환 후 저장

---

## 📦 LangSmith 연동 예제 코드

```bash
pip install -U langchain langchain-openai
```

```env
LANGCHAIN_TRACING_V2=true
LANGCHAIN_ENDPOINT=https://api.smith.langchain.com
LANGCHAIN_API_KEY=<your-api-key>
LANGCHAIN_PROJECT=pr-definite-burden-66
```

```python
from langchain_openai import ChatOpenAI
llm = ChatOpenAI()
llm.invoke("Hello, world!")
```