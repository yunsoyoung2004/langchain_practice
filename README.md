# 🤖 랭체인 & 랭그래프로 AI 에이전트 개발하기 실습 저장소

## 📚 책 정보

- **제목:** [랭체인 & 랭그래프로 AI 에이전트 개발하기](https://www.yes24.com/product/goods/143646468)
- **저자:** 김형진, 장원석
- **출판사:** 제이펍 (2024)
- **책 소개:** LangChain과 LangGraph를 활용해 생성형 AI 기반 에이전트를 직접 설계하고 구현할 수 있도록 구성된 실습 중심 입문서입니다. 주요 개념 이해부터 실제 서비스 수준의 에이전트 제작까지 안내합니다.

---

## 📂 포함 자료

- **📑 발표자료**
  - [LLM 입문 개요](https://docs.google.com/presentation/d/1aRkbexhdbVy_s5BcocQ_aCpDU09awT3s/edit?usp=drive_link)
  - [실습 중심 LLM 활용](https://docs.google.com/presentation/d/1dVja6fhrn5VecR6jmct-zqa1g4KinShG/edit?usp=drive_link)

- **🎬 전체 실습 영상**
  - [Google Drive에서 보기](https://drive.google.com/file/d/1ViQ2zMo9Syz2_u1Tiehza4eSpP1Lhxt0/view?usp=drive_link)

---

## 🚀 책 요약 및 실습 흐름

| 파트 | 주요 내용 |
|------|-----------|
| Part 1 | LLM 기초 이론: Transformer, Attention, 프롬프트 엔지니어링 |
| Part 2 | LangChain 기본 구성요소: Chain, Agent, Tools |
| Part 3 | LangGraph로 워크플로 자동화하기 |
| Part 4 | 다양한 에이전트 만들기 (ReAct, Retrieval, Multi-agent 등) |
| Part 5 | LangSmith로 평가, 디버깅 및 모니터링 |

---

## 🧪 실습 정리

| 실습 주제 | 요약 |
|-----------|------|
| 텍스트 기반 QA 에이전트 | 문서 임베딩, FAISS, LangChain Retriever 사용 |
| 수학 문제 해결 에이전트 | 계산기 도구 및 memory 사용 |
| 멀티 에이전트 협업 | AutoGen/CrewAI 기반 상호작용 |
| LangSmith 연동 | 평가 및 디버깅을 위한 통합 실습 |

---

## 🛠 환경 및 실행 방법

### 1. 패키지 설치

```bash
pip install -r requirements.txt
```

### 2. Streamlit 앱 실행

```bash
cd streamlit_app
streamlit run app.py
```

### 3. Jupyter 노트북 실행

```bash
jupyter lab
```

---

## 📁 폴더 구조 예시

```
llm-ai-agent-practice/
├── notebooks/             # 실습용 노트북
├── streamlit_app/         # 웹 앱 코드
├── data/                  # 테스트용 문서 및 임베딩
├── assets/                # 발표자료 및 이미지
├── README.md
└── requirements.txt
```

---

## 🔗 참고 링크

- [책 구매 링크 (YES24)](https://www.yes24.com/product/goods/143646468)
- [LangChain 공식 문서](https://docs.langchain.com/)
- [LangGraph 소개](https://www.langchain.com/langgraph)
- [LangSmith 사용법](https://docs.smith.langchain.com/)
