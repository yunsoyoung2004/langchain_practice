# 📘 LLM 입문 실습 기록: 책 + 실습 자료 정리

## 🔗 관련 자료

- **📖 교재:** [『당신도 챗GPT보다 똑똑해질 수 있습니다』 (Yes24)](https://www.yes24.com/product/goods/143646468)
- **🖥️ 발표자료:**  
  - [PPT 1: LLM 입문 개요](https://docs.google.com/presentation/d/1aRkbexhdbVy_s5BcocQ_aCpDU09awT3s/edit?usp=drive_link)  
  - [PPT 2: 실습 중심 LLM 활용](https://docs.google.com/presentation/d/1dVja6fhrn5VecR6jmct-zqa1g4KinShG/edit?usp=drive_link)
- **🎥 전체 실습 영상:**  
  [실습 동영상 보기 (Google Drive)](https://drive.google.com/file/d/1ViQ2zMo9Syz2_u1Tiehza4eSpP1Lhxt0/view?usp=drive_link)

---

## 📌 프로젝트 개요

이 저장소는 『당신도 챗GPT보다 똑똑해질 수 있습니다』 책 내용을 기반으로 한 **LLM 입문 실습 기록**을 정리한 공간입니다.  
책에서 소개하는 주요 개념, 실습 과정, 발표 자료, 그리고 직접 실습한 결과물까지 함께 담았습니다.

---

## 📚 목차

1. [프로젝트 목표](#프로젝트-목표)
2. [실습 요약](#실습-요약)
3. [사용 도구 및 환경](#사용-도구-및-환경)
4. [폴더 구조](#폴더-구조)
5. [실행 방법](#실행-방법)
6. [참고 자료](#참고-자료)

---

## ✅ 프로젝트 목표

- LLM(대규모 언어 모델)의 기본 개념 이해
- 실습을 통해 LLM의 활용 방식 익히기
- 발표자료 및 실습 영상을 통해 기초 흐름 복습
- 개인화된 응용 예제 작성 및 결과 공유

---

## 💡 실습 요약

| 실습 주제 | 내용 |
|-----------|------|
| LLM 구조 이해 | Transformer, Attention, Pretraining-Finetuning 개념 |
| 챗GPT 실습 | 프롬프트 작성법, 응답 품질 개선 |
| LangChain 실습 | 체인 구성, Agent, Tool 사용 방법 |
| Embedding & Vector Store | 텍스트 벡터화 및 유사도 검색 실습 |
| OpenAI API 활용 | GPT API를 활용한 자동화 예제 |
| 간단한 챗봇 만들기 | Streamlit, LangChain으로 챗봇 인터페이스 구현 |

---

## 🧰 사용 도구 및 환경

- Python 3.10+
- LangChain
- OpenAI API
- FAISS / Chroma (벡터 저장소)
- Streamlit (UI)
- Jupyter Notebook

> 상세 환경은 `requirements.txt` 참고 예정

---

## 📁 폴더 구조 (예시)

```
llm-intro-practice/
├── notebooks/             # Jupyter 노트북 실습
├── streamlit_app/         # 챗봇 UI 코드
├── data/                  # 테스트용 데이터
├── assets/                # 발표 자료, 이미지 등
├── README.md
└── requirements.txt
```

---

## ▶️ 실행 방법

```bash
# 패키지 설치
pip install -r requirements.txt

# Streamlit 앱 실행
cd streamlit_app
streamlit run app.py
```

---

## 🔍 참고 자료

- [LangChain 공식 문서](https://docs.langchain.com/)
- [OpenAI API 문서](https://platform.openai.com/docs)
- [책 구매 링크 (Yes24)](https://www.yes24.com/product/goods/143646468)
