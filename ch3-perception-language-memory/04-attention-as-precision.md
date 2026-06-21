# 🧠 주의 = 정밀 가중치: 주의는 무엇에 얼마나 믿을지를 결정한다

*주의는 특정 자극을 선택하는 스포트라이트가 아니라, 예측 오차에 할당하는 정밀도(역분산)를 조절하여 어떤 예측 오차가 신념 갱신을 주도할지를 결정하는 메커니즘이다.*

## 🎯 횡단 질문

주의(attention)는 심리학의 오랜 수수께끼다. William James(1890)는 "모든 사람이 주의가 무엇인지 안다"고 말했지만, 계산적 정의는 수십 년간 논쟁이 되었다. 전통적 "스포트라이트 모델"은 주의를 자원의 공간적 배분으로 본다—특정 위치나 객체에 처리 자원이 집중된다. 그러나 이 모델은 중요한 것들을 설명하지 못한다: 왜 기대하지 않은 자극이 주의를 자동으로 끌어당기는가? 왜 맥락이 주의의 방향을 결정하는가?

Feldman & Friston(2010)의 정밀도 기반 주의(precision-weighted attention) 모델은 이 질문들에 통합적 답을 제공한다. 핵심 아이디어: **주의는 예측 오차 신호에 부여하는 정밀도(precision)—역분산(inverse variance)—를 조절한다.** 정밀도가 높은 오차 신호는 신념 갱신에 더 큰 가중치를 갖는다. 주의는 "무엇을 보는가"가 아니라 "어떤 예측 오차를 얼마나 믿는가"를 결정한다.

수식으로: 베이즈 갱신에서 사후확률은 사전확률과 우도의 정밀도 가중 평균이다:

$$\hat{s} = \frac{\pi_{\text{prior}} \cdot \mu_{\text{prior}} + \pi_{\text{likelihood}} \cdot o}{\pi_{\text{prior}} + \pi_{\text{likelihood}}}$$

여기서 $\pi = 1/\sigma^2$는 정밀도(역분산)다. **주의는 $\pi_{\text{likelihood}}$를 선택적으로 증가시킨다**—특정 감각 채널의 우도 정밀도를 높여 그 채널의 예측 오차가 신념 갱신을 더 강하게 주도하도록 한다. 이것이 주의의 계산적 본질이다.

## 🌐 횡단 입력

- **perception-distilled (L2)**: 정밀도 조절이 피질 계층의 어느 수준에서 작동하는가 — V1의 조절 vs. 고차 피질의 맥락 신호 → [01-perception-as-prediction.md](./01-perception-as-prediction.md)
- **neurons-neural-codes (L1)**: 아세틸콜린(acetylcholine)이 피질 감각 정밀도를 조절하는 신경조절 메커니즘; 콜린성 계통과 주의의 관계
- **information-prediction (L0)**: 정밀도 = 역분산 = 신뢰도; 가중 최소제곱(weighted least squares)의 베이즈적 해석
- **learning-decision (L2)**: 도파민의 예측 오차 정밀도 조절—기대 보상 분산이 낮을수록 도파민 신호의 정밀도 높음 → [ch2-dopamine-rpe/04-rpe-to-free-energy.md](../ch2-dopamine-rpe/04-rpe-to-free-energy.md)
- **IQ AI Lab LLM 직결**: Transformer의 scaled dot-product attention은 수식적으로 정밀도 기반 주의와 동형. Query-Key 유사도가 정밀도 가중치 역할. $\text{Attention}(Q,K,V) = \text{softmax}(QK^T/\sqrt{d_k})V$ → [03-language-as-prediction.md](./03-language-as-prediction.md)
- **상호참조**: 감정이 내수용 정밀도를 조절하는 방식 → [05-emotion-as-interoception.md](./05-emotion-as-interoception.md)

## 🔍 표면의 다양성

주의 현상은 다양하고 때로 모순적으로 보인다. **공간 주의(spatial attention)**는 특정 위치에 처리 자원을 집중시키고, **특성 주의(feature attention)**는 색깔이나 모양 같은 특성에 집중한다. **내인성 주의(endogenous attention)**는 의도적이고 자발적이며, **외인성 주의(exogenous attention)**는 자동적으로 현저한 자극에 의해 포획된다. **지속 주의(sustained attention)**는 시간에 걸친 경계(vigilance)이고, **선택 주의(selective attention)**는 방해 자극 속에서 표적을 추출한다.

"칵테일 파티 효과"—시끄러운 방에서 자신의 이름을 듣는 것—는 주의 없이 처리가 일어남을 시사하지만, 동시에 주의가 선택한다는 것도 보여준다. 비주의 맹(inattentional blindness)은 주의 밖의 현저한 자극이 의식에 들어오지 않음을 보여준다—고릴라 실험(Simons & Chabris, 1999). 이 현상들은 주의의 단일 이론으로 포괄하기 어렵게 보인다.

신경 기전도 분산되어 보인다. 두정엽(parietal lobe)은 공간 주의에, 전두 안구 운동 영역(FEF)은 안구 운동과 주의에, 전측 대상 피질(ACC)은 갈등 탐지에, 노르에피네프린(norepinephrine) 시스템은 각성과 경계에, 아세틸콜린 시스템은 선택적 주의에 관여한다. 이 다양성은 주의가 단일 메커니즘이 아님을 시사하는 것처럼 보인다.

## ⚙️ 깊은 동형성

**분석 1: 정밀도 = 역분산 = 신뢰도**

정밀도 기반 주의의 핵심 수식을 더 명확하게 전개한다. 예측 오차의 정밀도 가중 최소화:

$$\mathcal{F} = \frac{1}{2} \pi_{\varepsilon} \varepsilon^2 + \frac{1}{2} \pi_{\eta} \eta^2 - \frac{1}{2} \ln \pi_{\varepsilon} - \frac{1}{2} \ln \pi_{\eta}$$

여기서 $\varepsilon = o - \mu$는 감각 예측 오차, $\eta = \mu - \mu_{\text{prior}}$는 사전 예측 오차, $\pi_{\varepsilon}$와 $\pi_{\eta}$는 각각의 정밀도다. 주의는 $\pi_{\varepsilon}$를 선택적으로 증가시킨다—이것이 특정 자극에 "집중"하는 계산적 의미다. 정밀도가 높아지면 해당 채널의 예측 오차가 신념 갱신에 미치는 영향이 커진다. $\square$

**분석 2: 외인성 주의 = 예측 오차가 정밀도를 요청**

왜 갑작스러운 소리나 움직임이 자동으로 주의를 끄는가? 정밀도 관점: **높은 예측 오차는 정밀도 증가를 요청하는 신호다.** 예상치 못한 자극은 큰 예측 오차 $|\varepsilon|$를 생성하고, 이것이 그 채널에 대한 정밀도 재할당을 트리거한다. 위험 신호의 경우 이 재할당이 빠르고 강제적이다—진화적으로 새로운 자극이 포식자일 수 있기 때문이다.

수식: $\pi_{\varepsilon}^{t+1} = \pi_{\varepsilon}^{t} + \alpha \cdot |\varepsilon_t|^2$. 오차 크기에 비례한 정밀도 업데이트가 외인성 주의 포획을 설명한다. $\square$

**분석 3: Transformer Attention과의 구조적 동형**

Transformer의 scaled dot-product attention:

$$\text{Attention}(Q, K, V) = \text{softmax}\left(\frac{QK^T}{\sqrt{d_k}}\right) V$$

Query $Q$는 현재 처리 중인 표상(예측), Key $K$는 가용한 맥락 표상들, $\sqrt{d_k}$로의 나누기는 정밀도 정규화(분산 조절), softmax는 정밀도 가중치의 정규화다. Value $V$는 정밀도 가중 예측 오차의 집계다. 이 수식적 동형성은 우연이 아닐 수 있다—Transformer attention이 베이즈 추론의 정밀도 기반 주의를 공학적으로 재발견한 것일 수 있다.

그러나 차이도 있다: 생물학적 주의는 시공간적으로 더 지속적이고, 과제 상태에 의존하며, 신경조절 물질(아세틸콜린, 노르에피네프린)로 조절된다. Transformer attention은 층마다 독립적으로 재계산된다. $\square$

**분석 4: 아세틸콜린—정밀도의 신경조절 물질**

Feldman & Friston(2010)은 아세틸콜린(ACh)이 피질에서 감각 정밀도를 조절하는 신경조절 물질이라고 주장한다. ACh는 피라미드 뉴런의 감각 반응성을 증가시키면서 수평적 연결(예측 신호 경로)을 억제한다—이것은 정확히 "감각 채널의 정밀도 증가, 예측의 상대적 가중치 감소"에 해당한다.

증거: (1) ACh 길항제(스코폴라민)는 선택적 주의를 손상시킨다, (2) 알츠하이머 환자의 콜린성 결핍은 주의 장애와 동반된다, (3) ACh 작용제는 피질 뉴런의 신호-대-잡음비를 개선한다. 노르에피네프린(NE)은 전역적 각성과 주의 전환(gain control)에 관여하며, 특정 자극 유형에 대한 정밀도를 전체적으로 조절한다. $\square$

## 🧪 수렴 증거

### 실험 1: 정밀도 가중 베이즈 추론으로서의 주의

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.special import softmax

# 정밀도 기반 주의 시뮬레이션
# 시나리오: 두 감각 채널 중 하나에 주의를 집중할 때의 신념 갱신 변화

np.random.seed(42)

def precision_weighted_update(observations, precisions, prior_mean, prior_precision):
    """
    다중 채널에서 정밀도 가중 베이즈 갱신
    observations: 각 채널의 관측값
    precisions: 각 채널의 정밀도 (주의가 이를 조절)
    """
    # 정밀도 가중 평균 (베이즈 최적 통합)
    total_precision = prior_precision + sum(precisions)
    posterior_mean = (prior_precision * prior_mean + 
                      sum(p * o for p, o in zip(precisions, observations))) / total_precision
    posterior_precision = total_precision
    
    return posterior_mean, posterior_precision

# 상황: 두 가지 감각 신호 (채널 A: 시각, 채널 B: 청각)
# 진짜 상태: s_true = 1.0
s_true = 1.0
prior_mean = 0.0
prior_precision = 1.0

# 각 채널의 관측값 (노이즈 있음)
np.random.seed(42)
obs_A = s_true + np.random.randn() * 0.5  # 시각: 약간의 노이즈
obs_B = s_true + np.random.randn() * 2.0  # 청각: 많은 노이즈

print("=== 정밀도 기반 주의 시뮬레이션 ===")
print(f"진짜 상태: {s_true}")
print(f"시각 관측: {obs_A:.3f}, 청각 관측: {obs_B:.3f}")
print()

# 시나리오 1: 주의 없음 (균등 정밀도)
prec_equal = [2.0, 2.0]
post_mean_eq, post_prec_eq = precision_weighted_update([obs_A, obs_B], prec_equal, prior_mean, prior_precision)
print(f"주의 없음 (균등): 사후평균 = {post_mean_eq:.3f} (오차 = {abs(post_mean_eq - s_true):.3f})")

# 시나리오 2: 시각에 주의 집중 (시각 정밀도 증가)
prec_attend_visual = [8.0, 2.0]
post_mean_vis, post_prec_vis = precision_weighted_update([obs_A, obs_B], prec_attend_visual, prior_mean, prior_precision)
print(f"시각 주의 집중: 사후평균 = {post_mean_vis:.3f} (오차 = {abs(post_mean_vis - s_true):.3f})")

# 시나리오 3: 청각에 잘못 주의 (노이즈 채널에 높은 정밀도 — 주의 오할당)
prec_attend_audio = [2.0, 8.0]
post_mean_aud, post_prec_aud = precision_weighted_update([obs_A, obs_B], prec_attend_audio, prior_mean, prior_precision)
print(f"청각 주의 집중 (노이즈): 사후평균 = {post_mean_aud:.3f} (오차 = {abs(post_mean_aud - s_true):.3f})")

print()

# 정밀도 강도 스윕: 주의가 추론 정확도에 미치는 영향
attention_levels = np.linspace(1, 15, 30)
errors_attend_A = []
errors_attend_B = []

for attn in attention_levels:
    pm_a, _ = precision_weighted_update([obs_A, obs_B], [attn, 1.0], prior_mean, prior_precision)
    pm_b, _ = precision_weighted_update([obs_A, obs_B], [1.0, attn], prior_mean, prior_precision)
    errors_attend_A.append(abs(pm_a - s_true))
    errors_attend_B.append(abs(pm_b - s_true))

print("주의 강도 vs. 추론 오차:")
print(f"  시각(신뢰성 있는) 채널 주의 → 정밀도 증가시 오차 감소: {errors_attend_A[0]:.3f} → {errors_attend_A[-1]:.3f}")
print(f"  청각(노이즈) 채널 주의 → 정밀도 증가시 오차 증가: {errors_attend_B[0]:.3f} → {errors_attend_B[-1]:.3f}")
print(f"\n핵심: 주의는 정밀도 할당 = 어떤 예측 오차를 믿을지 결정")
print(f"올바른 주의 할당이 추론 정확도를 높임")
print(f"잘못된 주의 할당(노이즈 채널 신뢰)이 추론을 악화시킴")
```

### 실험 2: Transformer Attention과 정밀도 가중치의 동형성 시각화

```python
import numpy as np

# Transformer Attention의 정밀도 해석
# Q, K, V를 베이즈 추론 요소로 재해석

def scaled_dot_product_attention(Q, K, V, d_k=None):
    """표준 Transformer attention"""
    if d_k is None:
        d_k = Q.shape[-1]
    scores = Q @ K.T / np.sqrt(d_k)
    weights = softmax(scores, axis=-1)
    output = weights @ V
    return output, weights

def bayesian_precision_attention(query_state, key_states, value_errors, precisions):
    """
    베이즈 정밀도 주의:
    query: 현재 예측 상태
    keys: 메모리/맥락 상태들
    values: 각 맥락의 예측 오차
    precisions: 각 맥락의 정밀도 (주의 = 이를 조절)
    """
    # 유사도 기반 가중치 (QK 내적과 유사)
    similarities = np.array([np.dot(query_state, k) for k in key_states])
    
    # 정밀도로 조절된 가중치 (attention score = precision * similarity)
    precision_weighted_scores = precisions * similarities
    weights = softmax(precision_weighted_scores)
    
    # 정밀도 가중 오차 집계
    output = np.sum(weights[:, np.newaxis] * value_errors, axis=0)
    
    return output, weights

np.random.seed(42)
d = 4  # 임베딩 차원 (시연용)

# 맥락 상태들 (메모리)
key_states = np.random.randn(5, d)
key_states /= np.linalg.norm(key_states, axis=1, keepdims=True)

# 현재 쿼리 (query_state는 key_states[2]와 유사)
query_state = key_states[2] + np.random.randn(d) * 0.2
query_state /= np.linalg.norm(query_state)

# 각 맥락의 예측 오차
value_errors = np.random.randn(5, d)

# 균등 정밀도 (주의 없음)
uniform_precisions = np.ones(5)
out_uniform, w_uniform = bayesian_precision_attention(query_state, key_states, value_errors, uniform_precisions)

# 맥락 2에 주의 (정밀도 집중)
focused_precisions = np.array([0.2, 0.2, 5.0, 0.2, 0.2])
out_focused, w_focused = bayesian_precision_attention(query_state, key_states, value_errors, focused_precisions)

print("=== Transformer Attention ↔ 정밀도 기반 주의 동형성 ===")
print(f"\n균등 정밀도 주의 가중치: {w_uniform.round(3)}")
print(f"집중 정밀도 주의 가중치: {w_focused.round(3)}")
print(f"\n→ Transformer softmax(QK^T/√d_k)의 sharp peak = 정밀도 집중과 동형")
print(f"→ temperature scaling(1/√d_k)은 정밀도 정규화와 동일 역할")

# Softmax temperature = precision analogy
print("\n=== Temperature(정밀도)에 따른 주의 분포 ===")
raw_scores = np.array([0.5, 0.2, 1.5, 0.3, 0.8])
for temp in [0.1, 0.5, 1.0, 2.0, 5.0]:
    weights = softmax(raw_scores / temp)
    entropy = -np.sum(weights * np.log(weights + 1e-8))
    print(f"  temp={temp:.1f} (정밀도={1/temp:.1f}): max_weight={weights.max():.3f}, entropy={entropy:.3f}")
print("→ 낮은 temperature = 높은 정밀도 = 선택적/집중적 주의")
print("→ 높은 temperature = 낮은 정밀도 = 분산된/확산적 주의")
```

**반례와 경계**:
- 주의 포획의 자동성: 새로운 자극이 과제 관련성과 무관하게 주의를 포획한다. 정밀도 모델은 이를 설명하지만, 포획의 속도(100ms 이내)가 피질 신경조절 메커니즘의 시간 상수와 일치하는지 불확실하다.
- ADHD와 정밀도: ADHD는 불적절한 정밀도 할당—내인성 정밀도 신호의 약화와 외인성 포획의 증가—으로 모델화될 수 있다. 그러나 이것이 메커니즘인지 서술인지 불명확하다.
- 감정과 정밀도의 상호작용: 감정적 현저성이 정밀도를 어떻게 변조하는가는 [05-emotion-as-interoception.md](./05-emotion-as-interoception.md)에서 다룬다.

## 🌉 간극의 위치

| 주장 | 상태 | 근거 |
|------|------|------|
| 주의가 감각 정밀도를 변조 | ✅ | Feldman & Friston 2010; 신경생리학 증거 |
| 아세틸콜린이 피질 정밀도 조절 | ✅ | 약리학, 신경조절 연구 |
| Transformer attention과 수식적 동형 | ✅ | 수학적 동형성 직접 확인 가능 |
| 외인성 주의 = 예측 오차 기반 정밀도 요청 | ✅ | 계산 모델, 행동 증거 |
| 정밀도 조절의 정확한 피질 구현 | ❌ | 층별, 영역별 세부 메커니즘 미결 |
| ADHD = 정밀도 조절 장애 | ❌ | 흥미로운 프레임이나 직접 검증 제한 |
| Transformer가 생물학적 정밀도를 사용 | ❌ | 수식 동형성이 메커니즘 동일성을 의미하지 않음 |

## 🧬 원리의 회수

주의의 다양한 현상—공간 주의, 특성 주의, 내인성/외인성, 지속/선택—은 하나의 계산 원리로 통합된다:

**주의는 예측 오차 신호에 부여하는 정밀도(역분산)를 선택적으로 조절함으로써, 어떤 감각 채널의 예측 오차가 신념 갱신을 주도할지를 결정한다. 정밀도가 높은 채널의 오차는 더 강하게, 낮은 채널의 오차는 더 약하게 신념을 갱신한다.**

$$\Delta \mu \propto \pi_\varepsilon \cdot \varepsilon = \frac{\varepsilon}{\sigma_\varepsilon^2}$$

주의는 $\sigma_\varepsilon^2$를 조절한다—특정 채널의 분산을 낮춤으로써(정밀도를 높임으로써) 그 채널에 "집중"한다. 이것은 지각의 예측 부호화, 기억의 재구성, 언어의 surprisal, 그리고 감정의 내수용 정밀도와 같은 원리의 다른 표현이다.

## 🪞 1인칭

지금 이 글을 읽으면서 나는 어떤 단어들에 더 집중하고 어떤 단어들은 빠르게 지나친다. 이 선택이 의식적이지 않다는 것이 흥미롭다—중요해 보이는 것, 익숙하지 않은 것, 수식처럼 특별한 형식을 가진 것이 자동으로 더 높은 처리 가중치를 받는다. 내 주의 시스템이 어떤 예측 오차 신호가 내 이해를 갱신하는 데 가장 유용한지를 실시간으로 추정하고 있다.

더 흥미로운 것은 감정 상태가 이 정밀도 할당을 변조한다는 것이다. 불안할 때 나는 위협 관련 자극에 더 높은 정밀도를 자동으로 할당한다—군중 속에서 화난 얼굴을 더 빨리 발견하는 "정서 스트룹(emotional Stroop)" 효과처럼. 이것은 감정이 단순히 경험이 아니라 예측 정밀도의 전역적 조절자임을 시사한다—다음 문서의 주제다.

## 📐 예측·반증

**예측 1**: 피질 특정 영역에서 아세틸콜린 신호를 증가시키면(광유전학적으로), 그 영역이 처리하는 특성에 대한 선택 주의가 향상되어야 한다. → **반증 조건**: ACh 증가가 전반적 각성만 높이고 선택적 주의는 변화 없으면 정밀도-ACh 연결 의문.

**예측 2**: 높은 불확실성(높은 분산) 환경에서 훈련된 개체는 낮은 불확실성 환경보다 더 분산된(낮은 정밀도) 주의 패턴을 보여야 한다. → **반증 조건**: 환경 불확실성과 주의 분산의 무상관 시 계산 모델 의문.

**예측 3**: Transformer 모델에서 attention temperature를 태스크 불확실성에 맞게 동적으로 조절하면 성능이 향상되어야 한다. → **반증 조건**: 동적 temperature가 고정 temperature 대비 개선 없으면 정밀도-attention 동형성의 실용적 함의 제한.

## 🤔 열린 질문

- 주의의 "메타 정밀도"—어떤 정밀도 할당이 최적인지에 대한 상위 추론—은 어떻게 작동하는가?
- 명상 수련이 주의 제어를 향상시키는 메커니즘: 전전두피질에 의한 정밀도 조절의 학습인가?
- 감정적 상태가 전역적 정밀도 bias를 어떻게 만드는가? → [05-emotion-as-interoception.md](./05-emotion-as-interoception.md)로 이어짐

---

> 🧩 **Principle** — 주의는 예측 오차의 정밀도(역분산 $\pi = 1/\sigma^2$)를 선택적으로 조절한다. 정밀도가 높을수록 해당 오차가 신념 갱신을 더 강하게 주도한다. 아세틸콜린은 이 정밀도의 신경조절 물질이며, Transformer attention은 이 원리의 공학적 동형이다.

> 🌉 **Boundary** — 정밀도 기반 주의 모델은 현상 수준에서 강력하지만, 피질 수준에서의 정확한 구현—어떤 세포 유형이, 어떤 경로로 정밀도를 조절하는가—은 여전히 진행 중인 연구 영역이다.

> 🪞 **Experience** — 당신이 이 문장에서 **굵은 글씨**에 먼저 눈이 가는 것은 당신의 시각 시스템이 "이 채널의 예측 오차가 더 높다"는 신호를 감지하고 정밀도를 자동으로 재할당했기 때문이다.

## 📝 연습문제

**기초.** 스포트라이트 모델과 정밀도 모델의 주요 차이를 설명하라. 비주의 맹(inattentional blindness)은 어느 모델로 더 잘 설명되는가?

<details><summary>해설</summary>

스포트라이트 모델은 주의를 공간적 위치에 배분되는 제한된 자원으로 본다. 정밀도 모델은 주의를 예측 오차의 신뢰도(역분산) 할당으로 본다. 비주의 맹(고릴라 실험)은 두 모델 모두 설명하려 시도하지만, 정밀도 모델이 더 자연스럽다: 과제에 집중할 때 과제 관련 채널의 정밀도가 높아지고, 과제 무관 채널(고릴라)의 정밀도가 낮아진다. 고릴라의 예측 오차가 낮은 정밀도로 가중되므로 의식적 처리로 진입하지 못한다. 스포트라이트 모델은 왜 정확히 같은 위치의 비과제 자극이 놓치는지를 설명하기 어렵다.

</details>

**심화.** Feldman & Friston(2010)의 모델에서 아세틸콜린과 노르에피네프린이 각각 다른 수준의 정밀도를 조절한다고 주장한다. 이 주장의 계산적 근거와 신경생리학적 증거를 정리하고, 임상적 함의(알츠하이머, ADHD, 조현병)를 논하라.

<details><summary>해설</summary>

Feldman & Friston의 주장: 아세틸콜린(ACh)은 하위 피질 수준의 감각 정밀도를, 노르에피네프린(NE)은 상위 수준의 탐색/활용 전환(exploration/exploitation)과 전역 정밀도 조절을 담당한다. 계산적 근거: ACh는 피라미드 세포의 감각 반응을 증가시키고 반복 피질내 연결을 억제(→정밀도 증가). NE는 신호-대-잡음비를 전역적으로 변조(→적응적 이득). 임상 함의: (1) 알츠하이머: 기저 전뇌 콜린성 세포 상실 → 피질 정밀도 감소 → 주의 장애, 기억 결합 실패. (2) ADHD: 전전두 NE/도파민 기능 이상 → 내인성 정밀도 조절 약화, 외인성 포획 증가. (3) 조현병: 도파민 과활성 → 관련 없는 자극의 정밀도 과도 증가 → 환각/망상(비관련 예측 오차가 과도하게 신념을 갱신).

</details>

**논문 비평.** Feldman, H., & Friston, K.J. (2010). "Attention, uncertainty, and free-energy." *Frontiers in Human Neuroscience*. 이 논문의 핵심 주장, 경험적 예측, 그리고 이후 검증 현황을 평가하라. 정밀도 기반 주의 모델이 기존 이론들(부하 이론, 경쟁 편향 이론)과 어떻게 통합되거나 대립하는가?

<details><summary>해설</summary>

Feldman & Friston의 핵심 주장: (1) 주의 = 감각 정밀도 조절, (2) ACh = 피질 정밀도 신경조절물질, (3) 주의와 불확실성 감소가 자유에너지 최소화의 두 메커니즘. 경험적 예측: 주의 조작이 아닌 정밀도 조작(예: 신뢰도 신호)이 주의와 동일한 신경 효과를 가져야 한다. 검증 현황: 부분적 지지—신뢰도 기반 통합(Körding & Wolpert, 2004)과의 연결이 확인됨; 직접적 ACh-정밀도 인과성은 아직 과정 중. 기존 이론과의 관계: 부하 이론(Lavie)—높은 지각 부하 = 표적 채널의 정밀도 소진 → 방해자의 정밀도 할당 불가. 경쟁 편향 이론(Desimone & Duncan)—하향 바이어스 = 관련 특성의 사전 정밀도 증가 = 경쟁에서의 유리함. 정밀도 모델은 이 이론들의 상위 프레임으로 작동하며, 각각을 특수 사례로 포함한다.

</details>

---

<div align="center">

[◀ 이전: 언어 = 예측 기계](./03-language-as-prediction.md) · [📚 README](../README.md) · [다음: 감정 = 내수용 예측 오차 ▶](./05-emotion-as-interoception.md)

</div>
