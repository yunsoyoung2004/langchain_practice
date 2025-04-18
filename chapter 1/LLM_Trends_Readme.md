
# 📘 LLM 트렌드 이해하기: 요약 및 시각화 중심 정리

이 문서는 LLM(Large Language Model)의 개념, 발전 과정, 멀티모달 처리, 오픈소스 역할, 모델 확장성 등에 대한 핵심 내용을 시각 중심으로 정리한 것입니다.

---

## 1. LLM의 탄생
- **트랜스포머 모델의 등장(2017)**  
  - Attention 메커니즘: 중요 단어에 집중하도록 설계
- **LLM의 핵심 특징**
  | 특징 | 설명 |
  |------|------|
  | 거대한 학습 데이터 | 인터넷 기반 대규모 텍스트 |
  | 많은 파라미터 | 수십억~수천억 개 |
  | 다양한 작업 수행 | 번역, 요약, 생성 등 |

---

## 2. GPT 시리즈의 발전
- **GPT-1 (2018)**: 최초 트랜스포머 기반 언어 모델
- **GPT-2 (2019)**: 더 많은 데이터 학습
- **GPT-3 (2020)**: 1750억 개 파라미터
- **ChatGPT (2022)**: GPT-3 기반 대화 특화
- **GPT-4 (2023)**: 멀티모달 지원 시작
- **GPT-4o (2024)**: Omni 모델, 텍스트·음성·이미지 통합

---

## 3. 멀티모달 LLM의 발전
- 텍스트 + 이미지 + 음성 → 통합 이해
- 예: Whisper API를 통한 음성 인식 통합

### ✅ 멀티모달 융합 사례
- 이미지 설명 생성 (예: 강아지가 해변에서 뛰는 모습)
- 텍스트+센서+VR 데이터 활용 (자율주행, 가상현실 등)

---

## 4. LLM의 발전: 모델 규모의 확장
- **파라미터(Parameter)**: AI가 학습에 사용하는 가중치
- **모델 크기 비교**

| 모델 | 출시 연도 | 파라미터 수 |
|------|-----------|-------------|
| GPT-2 | 2019 | 1.5억 |
| GPT-3 | 2020 | 1750억 |
| BERT(Base) | 2018 | 1.1억 |
| BERT(Large) | 2018 | 3.4억 |
| LLaMA 1 | 2023 | 70억~130억 |
| LLaMA 2 | 2023 | 최대 700억 |

---

## 5. 오픈소스와 커뮤니티의 역할
- 누구나 사용 가능한 모델 등장
- 대표 예시: GPT-J, BLOOM, LLaMA, Falcon, BERT 등
- Hugging Face, LangChain 커뮤니티 → 생태계 확대

### 독점 vs 오픈소스 비교

| 항목 | 독점형 LLM | 오픈소스 LLM |
|------|------------|---------------|
| 접근성 | 제한적 (API 필요) | 누구나 사용 가능 |
| 비용 | 유료 | 무료 |
| 투명성 | 낮음 | 높음 |
| 사용자 정의 | 제한적 | 자유로움 |

---

## 6. AI의 민주화
- 다양한 커뮤니티의 기여로 누구나 AI 활용 가능
- GitHub, Hugging Face, LangChain 등 생태계 확장
