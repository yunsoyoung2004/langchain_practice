
# 오토젠 기반 멀티에이전트 시스템 실습 요약

## 1. 오토젠 기본 개념

- **오토젠(Autogen)**: Microsoft에서 개발한 프레임워크로 다양한 AI 에이전트가 협업해 문제를 해결하도록 설계됨.
- **UserProxyAgent**: 사용자 입력을 이해하고, 이를 변환하여 다른 에이전트에게 전달.
- **AssistantAgent**: 실제 작업 수행. 예: 코드 작성, 분석, 시각화 등.

### 기본 흐름
1. 사용자 → UserProxyAgent
2. UserProxyAgent → AssistantAgent
3. AssistantAgent → LLM
4. LLM → AssistantAgent → UserProxyAgent → 사용자

## 2. 실습: 단일 AssistantAgent로 소수 계산

- Python 코드로 1부터 10,000까지 소수의 개수를 세는 작업 수행.
- `proxy.initiate_chat()`을 통해 AssistantAgent와 대화 시작.
- 결과로 에라토스테네스의 체 알고리즘 기반 코드 생성됨.

## 3. 실습: 멀티 에이전트 시스템 설계

### 목표
- 제품 디자인, 마케팅, PM 팀이 참여하여 **운동화 신제품 광고 전략** 수립.

### 에이전트 구성
- `design_agent`: 제품 디자인 관련 의견 제시
- `marketing_agent`: 마케팅 전략 및 채널 제안
- `pm_agent`: 전체 전략 조율 및 피드백

### 구성 방식
```python
groupchat = autogen.GroupChat(
    agents=[user_proxy, design_agent, marketing_agent, pm_agent],
    messages=[],
    max_round=4,
    speaker_selection_method=state_transition
)
```

## 4. 각 역할별 제안 요약

### 🔧 디자인 팀 제안
- 타겟: 18~35세, 활동적이며 건강과 스타일을 중시하는 사람들
- 제품 전략: 최신 기술과 소재 사용, 차별화된 USP 강조
- 시각화: 감성적인 브랜드 스토리와 맞춤형 디자인 옵션 제시

### 📢 마케팅 팀 제안
- 광고 메시지: "Step into Excellence"
- 채널 전략:
  - 온라인: 인스타그램/틱톡/유튜브
  - 오프라인: 팝업스토어, 체험 행사
- 초기 프로모션: 쿠폰 제공, 패키지 할인
- 피드백 루프: 온라인 리뷰, 고객 응대 시스템 구축

### 📊 PM 제안 (분석 및 총괄)
- 추가 작업 요청: 고객 세그먼트 세분화, USP 구체화
- 메시지 정제: 슬로건 중심의 단순명료한 전달 강조
- 피드백 시스템: 리뷰 기반 개선 루프 체계화

## 5. 종합 전략 제안

- 메시지-캠페인-플랫폼 통합 관리
- 세분화된 타겟 전략으로 맞춤형 광고 집행
- 시장/경쟁사 분석을 통한 차별화 전략 수립

> 이러한 전략을 바탕으로 각 에이전트의 협업을 통해 효과적이고 실행 가능한 광고 캠페인을 기획할 수 있음.
