
# LangSmith를 활용한 질문-정답 AI 평가 자동화 요약

이 문서는 LangSmith를 사용하여 질문-정답 쌍으로 구성된 데이터셋을 생성하고, 자동 평가(Auto-Evaluator)를 통해 성능을 검증하는 전체 절차를 요약한 것이다.

---

## 📌 데이터셋 생성

```python
inputs = [
  (question[0], correct_answers[0]),
  (question[1], correct_answers[1]),
  (question[2], correct_answers[2])
]

dataset_name = "qanda"
dataset = client.create_dataset(
    dataset_name=dataset_name, 
    description="Questions and Answers"
)

for input_prompt, output_answer in inputs:
    client.create_example(
        inputs={"question": input_prompt},
        outputs={"answer": output_answer},
        dataset_id=dataset.id
    )
```

> ⚠️ 동일한 이름의 데이터셋을 재생성하려 하면 충돌 오류 발생 가능 → 이름을 변경하거나 삭제 필요

---

## 🧪 성능 평가 준비

1. [https://smith.langchain.com](https://smith.langchain.com) 접속
2. `Datasets & Experiments` 메뉴 클릭
3. `qanda` 데이터셋 생성 여부 확인 후 클릭
4. 오른쪽 상단 `Add Auto-Evaluator` 클릭
5. Evaluator 유형: `LLM-as-a-Judge` 선택
6. Evaluator 설정:
   - Name: `qanda-evaluator`
   - Provider: `OpenAI`
   - Model: `gpt-4o`
   - Temperature: 0

---

## ⚙️ 평가 프롬프트 생성 및 실행

7. Prompt 메뉴에서 `Create a prompt from scratch` 클릭
8. Variable Mapping 설정 (예: input → question, output → answer, reference_output → answer)
9. API 키 입력 및 저장
10. `Test over dataset` 클릭
11. 데이터셋으로 `qanda` 선택
12. `Start` 클릭 후 평가 실행

---

## 📊 평가 결과 확인

- `Datasets & Experiments`로 돌아가서 `qanda` 선택
- `Correctness` 지표 확인
  - 값이 1에 가까울수록 정확한 응답
  - 지표는 모델 응답과 기대 정답의 일치도를 나타냄

---

## ✅ 요약

LangSmith를 통해 질문-정답 쌍을 기반으로 LLM 평가 자동화가 가능하며,
간단한 코드와 웹 UI를 조합해 손쉽게 평가 결과를 시각화할 수 있다.
