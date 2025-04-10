
# LangSmith 모니터링 기능 요약

LangSmith에서는 LLM 애플리케이션 성능을 다양한 지표로 모니터링하고 시각화할 수 있는 대시보드를 제공한다.

---

## 📊 대시보드 생성 절차

1. 좌측 메뉴에서 `Dashboards` 클릭
2. `+Dashboard` 클릭 후 이름 입력 → `Create`
3. 생성된 대시보드에서 `Chart` 클릭
4. New Chart 생성:
   - Chart name: Trace
   - Project 선택 (예: `pr-vengeful-questionnaire-9`)
   - Metric: `Total Cost` 선택
   - Create 클릭 → 대시보드에 시각화 생성됨

---

## 📈 주요 모니터링 지표

- **성능 평가 지표 (Performance Metrics)**: 정확도, 유용성, 관련성 등 LLM 애플리케이션 품질 지표 포함
- **사용자 피드백 (User Feedback)**: 사용자 만족도 기반 애플리케이션 개선 인사이트 제공
- **오류율 (Error Rates)**: 애플리케이션 내 오류 발생률 추적
- **비용 (Cost)**: 모델 호출 및 API 사용에 따른 총비용 확인
- **실행 횟수 (Run Count)**: 애플리케이션이 실행된 횟수
- **지연 시간 (Latency)**: 응답 시간 측정 → 성능 최적화 활용

---

## ✅ 대시보드 활용 요약

- 커스텀 대시보드를 통해 관심 항목 중심 모니터링 가능
- 각 지표는 프로젝트 단위로 분리 시각화 가능
- 실시간 추적 및 성능 개선에 유용한 도구

