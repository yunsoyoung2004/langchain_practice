
# 📘 Auto-GPT 설치 및 실행 요약

---

## 📌 개요
Auto-GPT는 LLM을 활용한 에이전트 프레임워크로, 사용자가 목표(goal)만 입력하면 해당 목표를 이루기 위한 작업을 스스로 수행하는 자동화 시스템입니다. 여기서는 Auto-GPT를 GitHub에서 클론하고 실행하는 방법을 단계별로 설명합니다.

---

## 🧱 설치 단계

1. **GitHub에서 Auto-GPT 클론**
```bash
git clone https://github.com/Significant-Gravitas/Auto-GPT.git
cd Auto-GPT
```

2. **버전 확인 및 최신 안정 버전으로 변경**
```bash
git tag -l
git checkout tags/v0.4.7
```

---

## ⚙️ 환경 설정

1. `.env.template` 파일을 열고, `OPENAI_API_KEY` 값을 자신의 OpenAI API 키로 변경합니다.
```env
OPENAI_API_KEY=sk-xxxxxx
```

2. `.env.template` 파일 이름을 `.env`로 변경하여 환경 설정이 인식되도록 합니다.

---

## 🚀 실행 방법

1. 다음 중 하나의 명령어로 실행
```bash
./run.sh
# 또는
python -m autogpt
```

2. 실행 후 “I want Auto-GPT to:” 프롬프트에서 에이전트에게 원하는 작업을 영어로 입력
- 예: `I want Auto-GPT to remove duplicate characters from a string.`

---

## 🧠 예시 프롬프트와 응답

- **Name:** `CodeTeachGPT`  
- **Role:** 코딩 개념을 설명해주는 AI  
- **Goals:**  
  - 코딩 개념을 명확히 설명  
  - 실습 제공  
  - 코딩 오류 피드백  
  - 최신 트렌드 반영  
- **실행 결과 예시:**  
  - Python으로 중복 문자 제거하는 코드 생성 및 실행  
  - 웹 검색을 통한 코드 관련 정보 수집

---

## 💡 활용 팁

- `.env`에 다양한 설정 옵션 존재 (API 키, 명령 허용 등)
- ChatGPT 기반 AutoGPT는 대화형 명령을 기반으로 다양한 작업을 자동화 가능
- 실행 중 추가 명령 입력 가능 (`Input:` 프롬프트)
