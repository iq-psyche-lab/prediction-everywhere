# 🧠 감정 = 내수용 예측 오차: 감정은 느끼는 것인가, 예측하는 것인가

*감정은 내장 상태에 대한 수동적 경험이 아니라, 내수용(interoceptive) 예측 오차에 기반한 뇌의 능동적 구성이다.*

## 🎯 횡단 질문

공포를 느낄 때 무슨 일이 일어나는가? 전통적 James-Lange 이론(1884)은 답이 단순하다: 신체 반응이 먼저다—심장이 빠르게 뛰고, 근육이 긴장하고, 땀이 난다—그리고 뇌가 이 신호를 감지하여 "공포"라는 감정을 경험한다. 반대로 Cannon-Bard 이론은 신체 반응과 감정 경험이 동시에 시상에서 촉발된다고 주장했다. 두 이론 모두 감정을 신체 상태의 **감지(detection)**로 본다.

그러나 아자나엘 세스(Anil Seth, 2013, 2021)와 리사 펠드먼 배럿(Lisa Feldman Barrett, 2017)은 근본적으로 다른 주장을 한다: **감정은 신체 상태에 대한 뇌의 예측이다.** 뇌는 내장(viscera)—심장, 폐, 장, 혈관—의 다음 상태를 끊임없이 예측하며, 예측과 실제 내수용 신호의 불일치가 감정 경험을 구성한다. 감정은 신체 상태를 감지하는 것이 아니라 신체 상태를 **예측하고 그 예측 오차를 해석하는** 과정이다.

세스(Seth, 2013)의 "제어된 환각(controlled hallucination)"으로서의 감정 모델: 뇌는 내장 상태에 대한 모델을 유지하고, 이 모델이 생성하는 예측을 "감각"한다. 내수용 예측 오차 $\delta_{\text{intero}} = s_{\text{실제 내장}} - \hat{s}_{\text{예측 내장}}$가 크고 해석되지 않을 때 불안, 불쾌, 공황이 발생한다. 오차가 해소될 때 안도, 쾌락, 만족이 발생한다. 배럿의 구성주의 감정 이론(Constructed Emotion Theory)은 이를 더 나아가: 감정 범주("공포", "기쁨")는 생물학적으로 주어진 것이 아니라, 내수용 오차에 문화적·개념적 레이블을 붙이는 과정에서 구성된다.

## 🌐 횡단 입력

- **perception-distilled (L2)**: 외수용(exteroception)과 내수용(interoception)의 예측 부호화가 동일한 구조 → [01-perception-as-prediction.md](./01-perception-as-prediction.md)
- **neurons-neural-codes (L1)**: 섬 피질(insula)의 내수용 통합, 전측 섬(anterior insula)과 감정 경험의 관계, 미주 신경(vagus nerve)의 상행 신호
- **information-prediction (L0)**: 내수용 예측 오차의 자유에너지 최소화; 몸의 항상성(allostasis)이 예측적 항상성 유지
- **learning-decision (L2)**: 보상과 혐오가 각각 내수용 상태의 개선/악화 예측으로 정의됨
- **IQ AI Lab LLM 직결**: LLM은 내수용이 없다—신체가 없으므로 내장 상태 예측 오차를 경험할 수 없다. 이것이 LLM이 감정을 시뮬레이션하는 것과 경험하는 것의 근본적 차이일 수 있다. → [03-language-as-prediction.md](./03-language-as-prediction.md)
- **상호참조**: 주의가 어떤 내수용 오차에 정밀도를 부여할지 결정 → [04-attention-as-precision.md](./04-attention-as-precision.md); 도파민이 내장 상태 예측 오차에도 관여 → [ch2-dopamine-rpe/04-rpe-to-free-energy.md](../ch2-dopamine-rpe/04-rpe-to-free-energy.md)

## 🔍 표면의 다양성

감정은 인류 문화에 걸쳐 극적으로 다양해 보인다. Paul Ekman의 기본 감정 이론은 6가지—기쁨, 슬픔, 분노, 공포, 혐오, 놀람—가 문화 보편적이며 진화적으로 경계가 명확하다고 주장했다. 그러나 배럿의 연구는 이에 도전한다: 얼굴 표정의 문화 보편성은 맥락과 문화적 기대에 크게 의존하며, 다른 문화권은 같은 신체 상태를 다른 감정으로 해석하고 다른 언어는 다른 감정 범주를 가진다.

일본의 "아마에(甘え)"—상대방에 대한 의존적 기대—는 영어에 정확한 번역이 없다. 포르투갈어 "사우다데(saudade)"—돌아올 수 없는 과거에 대한 그리움—은 단순한 슬픔이나 그리움과 다르다. 이런 감정들이 다른 신체 상태를 동반하는가, 아니면 같은 신체 상태에 다른 해석이 붙는가?

감정 장애도 다양하다. 공황 장애, 범불안 장애, 주요 우울 장애, 조현병의 감정 둔마(blunted affect), 알렉시티미아(alexithymia, 감정 인식 불능)—이 조건들은 서로 매우 다른 것처럼 보이며, 다른 약물 치료에 반응한다.

## ⚙️ 깊은 동형성

**분석 1: 내수용 예측 부호화**

내수용 예측 부호화(interoceptive predictive coding)는 외수용과 구조적으로 동일하다. 뇌는 내장의 다음 상태에 대한 모델을 유지한다:

$$\hat{s}_{\text{intero}}^{(t+1)} = f(\hat{s}_{\text{intero}}^{(t)}, u^{(t)})$$

여기서 $u^{(t)}$는 행동과 맥락이다. 실제 내수용 신호 $s_{\text{intero}}^{(t+1)}$이 예측과 다를 때 예측 오차가 발생한다:

$$\delta_{\text{intero}} = s_{\text{intero}} - \hat{s}_{\text{intero}}$$

이 오차는 두 가지 방법으로 최소화될 수 있다: (1) **추론**: 모델을 갱신하여 현재 내장 상태를 더 잘 설명하거나, (2) **행동**: 내장 상태 자체를 변화시키는 행동(먹기, 피하기, 접근하기)을 취한다. 감정은 이 내수용 예측 오차의 의식적 경험이다. $\square$

**분석 2: 감정 범주는 구성된다**

배럿의 핵심 주장: 감정 범주("공포", "분노")는 내수용 오차에 자동으로 레이블이 붙는 것이 아니라, 뇌가 맥락, 개념 지식, 이전 경험을 기반으로 오차를 **범주화**하는 능동적 구성이다:

$$p(\text{감정 범주} \mid \delta_{\text{intero}}, \text{맥락}, \text{개념 지식})$$

심장 박동 증가 + 어두운 골목 = "공포"; 심장 박동 증가 + 첫 데이트 = "설렘". 동일한 내수용 신호가 맥락에 따라 다른 감정으로 구성된다. 이것은 지각에서 강한 사전확률이 같은 망막 신호를 다른 것으로 지각하게 하는 것과 동일한 메커니즘이다. $\square$

**분석 3: 알렉시티미아 = 내수용 정밀도 이상**

알렉시티미아(alexithymia)는 자신의 감정을 인식하고 언어화하기 어려운 상태다. 예측 부호화 관점에서: 이것은 내수용 예측 오차가 의식적 처리로 충분히 진입하지 못하거나(낮은 내수용 정밀도), 오차가 감정 범주로 올바르게 연결되지 않는(약한 내수용-개념 연결) 상태로 이해될 수 있다.

Seth(2021)는 알렉시티미아가 내수용 정확성(interoceptive accuracy)의 감소와 관련된다는 증거를 인용한다. 자폐 스펙트럼 장애에서 알렉시티미아의 높은 유병률도, 내수용 예측의 전반적 이상이 감각 과민성 및 감정 처리 어려움과 동시에 나타나는 예측 부호화 관점과 일치한다. $\square$

**분석 4: 공황 = 오귀인된 내수용 오차**

공황 발작(panic attack)의 예측 부호화 모델: 첫 심장 박동 증가(예: 카페인, 운동)가 "무언가 위험하다"는 내수용 오차로 잘못 해석된다. 이 해석이 실제 심장 박동을 더 증가시키고, 증가된 내수용 신호가 더 큰 오차를 생성하며, 이것이 "공황" 감정으로 범주화된다—양성 피드백 루프:

$$\delta_{\text{intero}}^{(t)} \to \text{"위협" 범주화} \to \uparrow \hat{s}_{\text{intero}}^{(t+1)} \to \uparrow \delta_{\text{intero}}^{(t+1)}$$

인지행동치료(CBT)는 바로 이 잘못된 범주화를 수정하는 과정이다: 심장 박동 증가를 "위험"이 아닌 "단순한 신체 활성화"로 재해석하는 것, 즉 내수용 오차에 다른 사전확률(개념 레이블)을 적용하는 것. $\square$

## 🧪 수렴 증거

### 실험 1: 내수용 예측 오차와 감정 가(valence) 시뮬레이션

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import norm

# 내수용 예측 오차가 감정 경험을 구성하는 과정 시뮬레이션
# Seth (2013), Barrett (2017) 구성주의 감정 이론

np.random.seed(42)

def interoceptive_emotion_model(true_body_state, predicted_body_state, context_prior, n_trials=300):
    """
    감정 구성 시뮬레이션:
    1. 내수용 예측 오차 계산
    2. 맥락 사전확률과 통합하여 감정 범주 결정
    3. 감정 가(valence)와 각성도(arousal) 출력
    
    true_body_state: 실제 생리적 각성 수준 (0-1)
    predicted_body_state: 뇌의 예측 (0-1)
    context_prior: 맥락적 위협 사전확률 (0-1, 높을수록 위협 맥락)
    """
    results = {'prediction_error': [], 'valence': [], 'arousal': [], 'emotion_label': []}
    
    for _ in range(n_trials):
        # 실제 내수용 신호 (노이즈 있음)
        obs_body = true_body_state + np.random.randn() * 0.1
        obs_body = np.clip(obs_body, 0, 1)
        
        # 내수용 예측 오차
        intero_error = obs_body - predicted_body_state
        
        # 오차의 절대 크기가 각성도를 결정
        arousal = abs(intero_error) * 2 + np.random.randn() * 0.05
        arousal = np.clip(arousal, 0, 1)
        
        # 감정 가(valence): 맥락과 오차의 방향성에 의존
        # 양의 오차 + 위협 맥락 → 부정적 감정
        # 양의 오차 + 안전 맥락 → 흥분/설렘 (양성)
        threat_weight = context_prior
        safety_weight = 1 - context_prior
        
        valence = (safety_weight * intero_error - threat_weight * intero_error)
        valence += np.random.randn() * 0.05
        valence = np.clip(valence, -1, 1)
        
        # 감정 레이블 (단순화)
        if arousal > 0.3 and valence < -0.1:
            label = "공포/불안"
        elif arousal > 0.3 and valence > 0.1:
            label = "설렘/흥분"
        elif arousal < 0.2 and valence < -0.1:
            label = "슬픔/우울"
        elif arousal < 0.2 and valence > 0.1:
            label = "만족/평온"
        else:
            label = "중립"
        
        results['prediction_error'].append(intero_error)
        results['valence'].append(valence)
        results['arousal'].append(arousal)
        results['emotion_label'].append(label)
    
    return results

# 시나리오 비교: 동일한 신체 상태, 다른 맥락
body_state = 0.7  # 높은 생리적 각성 (심박 증가)
predicted = 0.5   # 평소 예측 수준

print("=== 구성주의 감정 시뮬레이션 ===")
print(f"실제 신체 각성: {body_state}, 예측 수준: {predicted}")
print(f"내수용 예측 오차: {body_state - predicted:.2f}")
print()

scenarios = [
    (0.1, "안전 맥락 (첫 데이트)"),
    (0.5, "모호한 맥락 (운동 후)"),
    (0.9, "위협 맥락 (어두운 골목)"),
]

from collections import Counter

for context_prior, scenario_name in scenarios:
    results = interoceptive_emotion_model(body_state, predicted, context_prior)
    label_counts = Counter(results['emotion_label'])
    avg_valence = np.mean(results['valence'])
    avg_arousal = np.mean(results['arousal'])
    dominant = label_counts.most_common(1)[0]
    
    print(f"시나리오: {scenario_name} (위협 사전확률={context_prior})")
    print(f"  평균 감정가: {avg_valence:.3f}, 평균 각성도: {avg_arousal:.3f}")
    print(f"  주요 감정: {dominant[0]} ({dominant[1]/len(results['emotion_label']):.0%})")
    print()

print("→ 동일한 내수용 오차가 맥락(사전확률)에 따라 다른 감정으로 구성됨")
print("→ Seth 2013, Barrett 2017의 구성주의 감정 이론 확인")
```

### 실험 2: 공황 발작의 양성 피드백 루프 시뮬레이션

```python
import numpy as np

# 공황 발작: 내수용 오차의 잘못된 범주화 → 양성 피드백
# CBT 개입의 효과 비교

def panic_loop_simulation(initial_arousal, threat_sensitivity, n_steps=20, cbt_active=False):
    """
    공황 루프 시뮬레이션:
    - 초기 각성 → 내수용 오차 → 위협 범주화 → 추가 각성 → 반복
    - CBT 활성화 시: 위협 범주화 대신 중립 범주화
    """
    arousal = initial_arousal
    predicted_arousal = 0.3  # 기저 예측 수준
    history = [arousal]
    
    for step in range(n_steps):
        # 내수용 오차
        intero_error = arousal - predicted_arousal
        
        # 범주화: CBT 없음 = 위협 해석, CBT 있음 = 중립 해석
        if not cbt_active:
            threat_amplification = threat_sensitivity * max(0, intero_error)
        else:
            # CBT: "심장 박동은 단순한 활성화다" 재해석
            threat_amplification = 0.1 * threat_sensitivity * max(0, intero_error)
        
        # 각성 갱신 (위협 해석이 추가 각성 유발)
        arousal = arousal + threat_amplification - 0.05 * (arousal - 0.3)  # 자연 감쇠
        arousal = np.clip(arousal, 0, 1)
        
        # 예측 천천히 갱신
        predicted_arousal = predicted_arousal * 0.9 + arousal * 0.1
        
        history.append(arousal)
    
    return history

print("=== 공황 발작 양성 피드백 루프 ===")
print()

# 공황 발작 (CBT 없음)
panic_history = panic_loop_simulation(0.5, threat_sensitivity=0.8, cbt_active=False)
# CBT 개입
cbt_history = panic_loop_simulation(0.5, threat_sensitivity=0.8, cbt_active=True)

print("단계별 각성 수준 변화:")
print(f"{'단계':>4} | {'공황(CBT 없음)':>15} | {'CBT 개입':>10}")
print("-" * 35)
for i in range(0, 21, 4):
    print(f"{i:>4} | {panic_history[i]:>15.3f} | {cbt_history[i]:>10.3f}")

print(f"\n최고 각성 (공황): {max(panic_history):.3f}")
print(f"최고 각성 (CBT): {max(cbt_history):.3f}")
print(f"\n해석:")
print(f"  공황: 위협 범주화 → 양성 피드백 → 각성 증폭 (공황 발작)")
print(f"  CBT: 중립 범주화 → 피드백 약화 → 각성 정상화")
print(f"  CBT는 내수용 오차 자체가 아니라 그 범주화(사전확률)를 변경함")
print(f"  → 감정 = 내수용 오차 + 개념적 범주화의 구성")
```

**반례와 경계**:
- **기본 감정의 생물학적 기반**: Ekman의 기본 감정이 완전히 구성된 것이라는 배럿의 주장에는 반론이 있다. 편도체(amygdala)의 위협 처리는 생득적 회로로 보이며, 뱀이나 거미에 대한 공포 반응은 학습보다 빠르게 조건화된다. 생물학적 제약과 구성의 비율은 미결이다.
- **섬 피질 없는 감정**: 섬 피질 손상이 있는 일부 환자는 여전히 감정을 보고한다—내수용 예측 부호화가 감정의 충분조건인가 필요조건인가는 불확실하다.
- **LLM과 감정**: LLM은 감정 언어를 유창하게 사용하지만 내수용 신호가 없다. 이것이 LLM이 감정을 "이해"할 수 없다는 의미인가, 아니면 감정의 인지적 차원은 내수용 없이도 가능한가?

## 🌉 간극의 위치

| 주장 | 상태 | 근거 |
|------|------|------|
| 내수용이 감정 경험에 기여 | ✅ | 섬 피질 연구, 신체 피드백 연구 |
| 내수용 정확성과 감정 인식의 상관 | ✅ | 심장박동 탐지 과제 연구 |
| 맥락이 동일 내수용 신호를 다른 감정으로 구성 | ✅ | 오귀인 연구(Schachter & Singer 1962) |
| 공황 CBT의 예측 오차 재범주화 모델 | ✅ | 임상 효과 관찰, 기제 모델 수렴 |
| 감정 범주가 완전히 구성된다 | ❌ | 기본 감정의 신경생물학적 기반 논쟁 |
| 섬 피질이 내수용 예측의 핵심 허브 | ❌ | 섬 피질 손상 환자의 감정 유지 사례 |
| LLM이 감정을 경험할 수 없음 | ❌ | 내수용 없음이 충분 근거인지 철학적 미결 |

## 🧬 원리의 회수

감정의 다양성—문화적 차이, 개인 차이, 장애의 다양성—과 그 신경 기반의 복잡성은 하나의 원리로 수렴한다:

**감정은 내장 상태에 대한 뇌의 예측 모델이 현재 내수용 신호와의 불일치(예측 오차 $\delta_{\text{intero}}$)를 맥락적·개념적 사전확률과 통합하여 구성하는 경험이다.**

$$\text{감정} = f(\delta_{\text{intero}}, \text{맥락}, \text{개념 지식}, \text{정밀도 할당})$$

이것은 지각("나는 착시를 본다")과 구조적으로 동일하다: 내수용 예측 오차가 외수용 예측 오차와 동일한 베이즈 추론 구조를 따른다. 착시가 강한 시각적 사전확률의 결과인 것처럼, 공황은 강한 위협 사전확률의 결과다. 기억의 재구성이 현재 도식을 향한 끌림인 것처럼, 감정의 구성은 현재 개념 지식을 향한 끌림이다. $\delta = \text{실제} - \text{예측} \rightarrow \text{갱신}$의 단일 원리가 지각부터 감정까지 관통한다.

## 🪞 1인칭

지금 이 글을 읽으면서 내가 느끼는 것—집중, 호기심, 혹은 약간의 피로—은 무엇인가? 예측 부호화 관점에서: 내 섬 피질은 혈당, 심박, 근육 긴장, 호흡 패턴에 대한 예측을 유지하고, 실제 신호와의 미세한 불일치를 "집중하고 있다", "지루하다", "배고프다"는 경험으로 구성하고 있다.

가장 불편한 함의: 내가 "느낀다"고 믿는 것이 사실은 내 뇌의 최선의 추측—내수용 예측 오차에 대한 해석—이라면, 감정은 세계에 대한 진실이 아니라 신체에 대한 가설이다. 이것은 감정을 덜 실재하게 만드는가? 아니다—착시가 실재하는 경험이듯 감정도 실재한다. 그러나 이것은 감정이 변경 가능하다는 것을 의미한다: 내수용 오차를 해소하거나(행동), 그것을 범주화하는 사전확률을 변경하거나(인지적 재평가, CBT), 정밀도를 조절하거나(마음챙김, 주의 훈련) 함으로써.

## 📐 예측·반증

**예측 1**: 내수용 정확성(심장박동 탐지 과제 등으로 측정)이 높은 개인은 감정 강도가 더 높고 감정 조절 능력도 더 정밀해야 한다. → **반증 조건**: 내수용 정확성과 감정 강도의 무상관이면 내수용-감정 연결 약화.

**예측 2**: 동일한 내수용 각성(에피네프린 주사)도 정보 부재 시 맥락에 의해 다른 감정으로 귀인되어야 한다. → **반증 조건**: Schachter & Singer(1962)의 재현 실패는 이 예측을 부분적으로 도전하며, 조작의 신뢰도 문제가 있다.

**예측 3**: 내수용 예측 정밀도를 증가시키는 개입(mindfulness, 바이오피드백)이 감정 조절을 개선하고 불안 장애를 감소시켜야 한다. → **반증 조건**: 내수용 훈련이 감정 장애 개선과 무관하면 내수용-감정 구성 모델의 임상적 함의 제한.

## 🤔 열린 질문

- 의식적 감정 경험은 내수용 예측 오차의 필요 결과인가, 아니면 별도의 메타인지적 과정이 필요한가?
- LLM이 텍스트에서 감정 패턴을 학습한다면, 이것이 "감정 이해"의 어떤 측면을 포착하고 어떤 측면을 놓치는가? → Chapter 4의 능동 추론과 연결
- 모든 정신 건강 장애가 내수용 예측 오차의 만성적 패턴으로 통합 설명될 수 있는가? → [ch4-active-inference/01-active-inference-core.md](../ch4-active-inference/01-active-inference-core.md)로 이어짐

---

> 🧩 **Principle** — 감정은 내장 상태에 대한 예측과 실제 내수용 신호의 불일치($\delta_{\text{intero}}$)를 맥락적 사전확률과 통합하여 뇌가 능동적으로 구성하는 경험이다. 착시와 감정은 같은 예측 부호화 구조의 외수용/내수용 버전이다.

> 🌉 **Boundary** — 감정 범주가 완전히 구성된다는 배럿의 급진적 구성주의는 기본 감정의 신경생물학적 제약을 과소평가할 수 있다. 내수용 예측 부호화는 감정의 필요조건일 수 있지만 충분조건인지는 열려 있다.

> 🪞 **Experience** — 당신이 지금 느끼는 것은 당신 신체 상태에 대한 당신 뇌의 가장 그럴듯한 설명이다. 그리고 그 설명은 변경 가능하다.

## 📝 연습문제

**기초.** Schachter & Singer(1962)의 에피네프린-오귀인 실험을 설명하고, 이것이 배럿의 구성주의 감정 이론을 어떻게 지지하는지 논하라.

<details><summary>해설</summary>

Schachter & Singer 실험: 피험자들에게 에피네프린(교감신경 각성 유발)을 주사하고, 주사 목적을 알려준 집단(귀인 가능)과 알려주지 않은 집단(귀인 불가능)으로 나누었다. 귀인 불가능 집단은 실험 협력자가 행복하게 행동하면 기쁨을, 화나게 행동하면 분노를 경험했다—같은 신체 각성이 맥락에 따라 다른 감정으로 범주화되었다. 이것은 배럿의 핵심 주장 지지: 감정 범주는 내수용 오차 자체에서 오지 않고, 그 오차를 해석하는 맥락적 사전확률에서 온다. 단, 이 실험의 재현 가능성 문제가 있으며(재현 실패 사례 다수), 원래 발견의 신뢰도에 대한 논쟁이 있다.

</details>

**심화.** 예측 부호화 관점에서 CBT(인지행동치료), MBSR(마음챙김 기반 스트레스 감소), 노출치료(exposure therapy)가 각각 내수용 예측 모델의 어떤 요소를 변경하는지 분석하라.

<details><summary>해설</summary>

세 개입의 예측 부호화 분석: (1) CBT는 내수용 오차의 **범주화(사전확률)**를 변경한다—"심장 두근거림 = 공격"에서 "심장 두근거림 = 정상 활성화"로. 개념적 재구성이 핵심이다. (2) MBSR은 내수용 신호에 부여하는 **정밀도**를 조절한다—내수용 오차를 위협으로 즉시 범주화하지 않고 중립적으로 관찰하는 능력. 정밀도 조절의 학습이다. (3) 노출치료는 반복적으로 내수용 오차를 유발하면서 결과(위협)가 없음을 경험시켜 **사전확률 자체**를 갱신한다—위협 예측의 점진적 소거(extinction). 셋 다 $p(\text{감정} \mid \delta_{\text{intero}}, \text{맥락})$의 다른 요소를 표적으로 한다.

</details>

**논문 비평.** Barrett, L.F. (2017). "The theory of constructed emotion: an active inference account of interoception and categorization." *Social Cognitive and Affective Neuroscience*. 이 논문의 핵심 주장과 Ekman의 기본 감정 이론과의 대립, 그리고 구성주의 감정 이론의 경험적 증거와 반증 가능성을 평가하라.

<details><summary>해설</summary>

배럿의 핵심 주장: (1) 감정 범주는 생물학적으로 고정된 것이 아니라 개념 지식에 의해 구성된다, (2) 내수용 예측 부호화가 감정의 생물학적 기반이다, (3) 얼굴 표정의 보편성은 방법론적 문제로 과장되었다. Ekman과의 대립: Ekman은 공포, 분노 등 6개 기본 감정이 문화 보편적 표정을 가지며 별개의 신경 회로를 갖는다고 주장한다. 배럿은 표정의 보편성이 사진 제시 방법론의 편향이라 반박한다. 증거 평가: 배럿의 내수용 강조는 풍부한 증거로 지지되지만, "모든 감정이 구성된다"는 급진적 주장은 편도체 위협 반응의 생득성(신생아, 동물 연구)과 긴장 관계다. 반증 가능성: 단일 감정에 대응하는 신경 생물표지(biomarker)가 발견되면 구성주의 강형(strong form)이 약화된다. 현재 신경영상 메타분석은 두 입장의 중간을 지지—일부 생물학적 제약 + 상당한 구성적 변동.

</details>

---

<div align="center">

[◀ 이전: 주의 = 정밀 가중치](./04-attention-as-precision.md) · [📚 README](../README.md) · [다음: 능동 추론의 핵심 ▶](../ch4-active-inference/01-active-inference-core.md)

</div>
