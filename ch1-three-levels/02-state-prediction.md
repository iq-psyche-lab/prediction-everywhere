# 🧠 상태 예측 — 지각 모델

*뇌는 감각 신호를 받아 세계를 읽는 것이 아니라, 세계에 대한 가설을 가지고 감각 신호를 예측하며, 그 예측의 오차만을 상향 전달한다 — 이것이 예측 부호화의 핵심이다.*

## 🎯 횡단 질문

시각 피질에서 V1 뉴런이 하는 일은 무엇인가? 직관적 답변은 "망막에서 온 정보를 처리한다"이다. 그러나 Rao & Ballard(1999)의 예측 부호화(predictive coding) 이론은 다른 그림을 제시한다: 상위 피질 영역이 하위 영역의 활동을 예측하고, 하위 영역은 예측과 실제 입력의 차이(예측 오차)만을 상위로 전달한다. 이 구조에서 V1의 주된 출력은 망막 신호가 아니라 *예측이 빗나간 정도*다.

베이즈 갱신의 형태로 쓰면:

$$p(s \mid o) \propto p(o \mid s) \cdot p(s)$$

여기서 $o$는 관찰(감각 입력), $s$는 숨겨진 상태(세계의 원인), $p(s)$는 이전 믿음(prior), $p(o \mid s)$는 우도(likelihood), $p(s \mid o)$는 갱신된 믿음(posterior)이다. 뇌는 감각 신호로부터 가장 그럴듯한 세계 상태를 추론하는 베이즈 추론기라는 것이 이 층위의 핵심 주장이다.

신호 예측(도파민 RPE)이 "기대한 보상이 왔는가"를 묻는다면, 상태 예측은 "세계가 지금 어떤 상태인가"를 묻는다. 전자가 스칼라 결과를 예측하는 반면, 후자는 고차원 상태 공간에서 분포를 유지하고 갱신한다. 이 두 예측은 다른 시간 척도와 다른 공간에서 작동하지만, δ = 실제 − 예측의 구조를 공유한다.

## 🌐 횡단 입력

- **information-prediction-distilled (L0)**: 감각 입력의 정보량 $-\log p(o|s)$와 예측 오차의 관계. 예측된 감각(높은 $p(o|s)$)은 적은 정보를 전달하고, 예상치 못한 감각(낮은 $p(o|s)$)은 많은 정보를 전달한다.
- **perception-distilled (L2)**: Rao & Ballard(1999)의 계층적 예측 부호화 모델. V1 → V2 → V4 계층에서 역방향 예측과 순방향 오차 전달의 해부학적 구조.
- **neuromodulation-arousal-distilled (L1)**: 노르에피네프린이 예측 오차의 이득(gain)을 조절한다는 가설. 각성 수준이 베이즈 갱신의 민감도를 조절.
- **consciousness-distilled (L4)**: 의식적 지각이 예측의 승리인가 — 가장 높은 사후 확률을 가진 가설이 의식에 도달한다는 예측 부호화의 의식 이론(Friston, 2005; Hohwy, 2013).
- **IQ AI Lab (LLM 직결)**: 대규모 언어 모델의 다음 토큰 예측이 상태 예측의 공학적 변주. 컨텍스트(prior) → 토큰 분포(posterior) 갱신이 베이즈 구조와 형식적으로 동형.

## 🔍 표면의 다양성

**차이 1: 표상의 차원.** 신호 예측의 RPE는 1차원 스칼라다. 상태 예측의 $p(s|o)$는 고차원 확률 분포다 — 수천 개의 가능한 세계 상태에 대한 믿음 전체가 갱신된다. 이것은 단순히 양적 차이가 아니라, 예측의 대상 자체가 다르다: 결과 대 상태.

**차이 2: 계층 구조.** 도파민 RPE는 선조체라는 단일 수렴 지점에서 생성된다. 예측 부호화는 피질의 수십 개 계층에 걸쳐 분산된 예측 오차들이 동시에 전파된다. 각 계층이 자기 수준의 예측을 유지하고 자기 수준의 오차를 계산한다는 점에서, 이것은 계층적 예측의 앙상블이다.

**차이 3: 시간 척도.** RPE는 보상 사건에 대한 밀리초~초 단위 반응이다. 지각 모델의 베이즈 갱신은 수백 밀리초~초 단위로 일어나지만, 상위 수준의 믿음(예: "이것은 얼굴이다")은 수십 밀리초 이내에 형성될 수 있다. 계층에 따라 갱신 속도가 다르다.

## ⚙️ 깊은 동형성

**분석 1: 예측 오차는 정보다.** 베이즈 갱신에서 사후 분포는 우도와 사전 분포의 곱에 비례한다. 예측 부호화 언어로: 상위 표상이 하위 입력을 예측하고, 하위 단위는 예측과 실제의 차이만 상향 전달한다. 이 차이 $\epsilon = o - \hat{o}$(관찰 − 예측)가 곧 정보다 — 이미 알고 있는 것은 전달할 필요가 없다. $\square$

**분석 2: 역방향 연결은 예측, 순방향 연결은 오차.** Rao & Ballard(1999)의 핵심 해부학적 주장: 피질의 역방향(피드백) 연결이 예측 신호를 하위 영역으로 전달하고, 순방향(피드포워드) 연결이 예측 오차를 상위 영역으로 전달한다. 이 비대칭성이 예측 부호화 구조를 가능하게 한다. $\square$

**분석 3: 정밀도 가중(precision weighting).** 모든 예측 오차가 동등하게 취급되지 않는다. 신뢰할 수 있는 감각 채널의 오차는 더 큰 가중치를 받고, 노이즈가 많은 채널의 오차는 무시된다. 수식으로: $\tilde{\epsilon} = \Pi \cdot \epsilon$, 여기서 $\Pi$는 정밀도(역분산) 행렬이다. 주의(attention)가 이 정밀도 가중의 조절 메커니즘이라는 주장이 있다. $\square$

**분석 4: 자유에너지와의 연결.** 베이즈 갱신은 정확한 계산이 불가능한 경우가 많다(복잡한 자연 환경에서). 변분 베이즈(variational Bayes)는 이를 근사하는 방법으로, 실제 사후 분포 $p(s|o)$와 근사 분포 $q(s)$ 사이의 KL 발산을 최소화한다. 이것이 바로 자유에너지 최소화다: $F = \text{KL}[q(s) \| p(s)] - \mathbb{E}_q[\log p(o|s)]$. 예측 부호화는 변분 자유에너지 최소화의 신경 구현으로 해석된다. $\square$

## 🧪 수렴 증거

### 실험 1: 계층적 예측 부호화 시뮬레이션

```python
import numpy as np

# 2계층 예측 부호화 네트워크 시뮬레이션
# Rao & Ballard (1999) 단순화 버전
np.random.seed(42)

class PredictiveCodingLayer:
    def __init__(self, n_units, learning_rate=0.01):
        self.n = n_units
        self.lr = learning_rate
        self.representation = np.zeros(n_units)  # 현재 믿음 r
        self.weights = np.random.randn(n_units, n_units) * 0.1  # 예측 가중치
    
    def predict(self, higher_repr):
        """상위 표상에서 하위 입력 예측"""
        return self.weights @ higher_repr
    
    def update(self, prediction_error, top_down_error, kappa=0.1):
        """예측 오차로 표상 갱신"""
        # 하위에서 오는 오차 + 상위에서 오는 역방향 신호
        self.representation += self.lr * (prediction_error - top_down_error)
        self.representation = np.clip(self.representation, -3, 3)
    
    def learn(self, prediction_error, higher_repr, lr_weights=0.001):
        """가중치(생성 모델) 학습"""
        self.weights += lr_weights * np.outer(prediction_error, higher_repr)

# 입력: 잡음 섞인 감각 신호 (실제 원인: 사인파 패턴)
T = 100
n_low = 10   # 하위 층 유닛 수
n_high = 5   # 상위 층 유닛 수

layer_low = PredictiveCodingLayer(n_low)
layer_high = PredictiveCodingLayer(n_high)

# 실제 숨겨진 원인 (세계 상태)
true_cause = np.array([1, 0, -1, 0.5, -0.5])

# 학습 루프
errors_over_time = []

for t in range(500):
    # 감각 입력 (true_cause + 잡음)
    noise = np.random.randn(n_low) * 0.3
    sensory_input = layer_low.weights @ true_cause + noise
    
    # 예측 오차 계산 (관찰 - 예측)
    prediction = layer_low.predict(layer_high.representation)
    error_low = sensory_input - prediction
    
    # 상위 층 갱신 (하위 오차 기반)
    top_down_pred = np.zeros(n_high)  # 최상위는 prior만
    error_high = layer_high.weights.T @ error_low - top_down_pred
    
    layer_high.update(error_high, top_down_pred)
    layer_low.learn(error_low, layer_high.representation)
    
    errors_over_time.append(np.mean(np.abs(error_low)))

print("=== 계층적 예측 부호화 학습 결과 ===")
print(f"초기 평균 예측 오차: {np.mean(errors_over_time[:20]):.4f}")
print(f"후기 평균 예측 오차: {np.mean(errors_over_time[-20:]):.4f}")
print(f"오차 감소율: {(1 - np.mean(errors_over_time[-20:])/np.mean(errors_over_time[:20]))*100:.1f}%")
print()
print("학습된 상위 표상:", np.round(layer_high.representation, 3))
print("실제 원인:        ", np.round(true_cause, 3))
print()
print("해석: 상위 층이 잡음 섞인 감각에서 숨겨진 원인을 점진적으로 복원")
print("예측 오차가 줄어들수록 표상이 실제 세계 상태에 수렴")
```

### 실험 2: 베이즈 갱신 — 시각적 모호성 해결

```python
import numpy as np
from scipy.special import softmax

# 네커 큐브(Necker cube)같은 모호한 자극의 지각 전환 시뮬레이션
# 두 해석(가설 A, B)에 대한 베이즈 갱신
np.random.seed(0)

def bayesian_update(prior, likelihood):
    """베이즈 갱신: posterior ∝ likelihood × prior"""
    unnorm = likelihood * prior
    return unnorm / unnorm.sum()

# 초기 사전 분포: 두 해석 동등
prior = np.array([0.5, 0.5])

print("=== 모호한 자극의 베이즈 지각 전환 ===")
print(f"초기 사전 분포: 해석A={prior[0]:.2f}, 해석B={prior[1]:.2f}")
print()

# 시나리오 1: 해석 A를 지지하는 강한 감각 증거
likelihood_A_dominant = np.array([0.9, 0.1])
posterior_1 = bayesian_update(prior, likelihood_A_dominant)
print(f"강한 A 증거 후: 해석A={posterior_1[0]:.3f}, 해석B={posterior_1[1]:.3f}")

# 시나리오 2: 약한 증거 누적 (이전 posterior가 새 prior)
likelihood_weak = np.array([0.6, 0.4])
posterior_2 = bayesian_update(posterior_1, likelihood_weak)
print(f"추가 약한 증거: 해석A={posterior_2[0]:.3f}, 해석B={posterior_2[1]:.3f}")

# 시나리오 3: B를 지지하는 강한 증거 (지각 전환)
likelihood_B_dominant = np.array([0.05, 0.95])
posterior_3 = bayesian_update(posterior_2, likelihood_B_dominant)
print(f"강한 B 증거 후: 해석A={posterior_3[0]:.3f}, 해석B={posterior_3[1]:.3f}")
print()

# 정밀도 가중의 효과
print("=== 정밀도 가중 (주의의 베이즈 역할) ===")
base_error = np.array([1.0, -0.5, 0.3, -0.8])  # 예측 오차 벡터
precision_attended = np.array([4.0, 4.0, 1.0, 1.0])  # 주의 집중 채널
precision_unattended = np.array([1.0, 1.0, 1.0, 1.0])  # 균등 정밀도

weighted_attended = precision_attended * base_error
weighted_unattended = precision_unattended * base_error

print(f"원본 오차:        {base_error}")
print(f"주의 집중 가중:   {weighted_attended}")
print(f"균등 가중:        {weighted_unattended}")
print(f"주의 채널 신호 증폭: {np.mean(np.abs(weighted_attended[:2]))/np.mean(np.abs(weighted_unattended[:2])):.1f}배")
print()
print("해석: 주의는 특정 채널의 정밀도(역분산)를 높여 그 예측 오차를 증폭")
print("이것이 주의의 예측 부호화 해석 — 주의 = 정밀도 제어")
```

**반례와 경계.** 예측 부호화 이론은 강력하지만 논쟁이 활발하다. 첫째, 순방향 연결이 오차만 전달하는지 아니면 표상 자체도 전달하는지가 불명확하다(Kogo & Trengove, 2015). 둘째, 피드백 연결의 정확한 역할이 예측 부호화 모델과 주의 조절 모델 사이에서 구분되기 어렵다. 셋째, 동일한 fMRI 억제 패턴이 예측 부호화 외 다른 기전(반복 억제, 적응)으로도 설명 가능하다. 이론이 너무 유연해서 거의 모든 데이터와 양립한다는 비판이 있다.

## 🌉 간극의 위치

✅ 도달: 예측 부호화의 계산적 틀과 신경 해부학적 대응 (Rao & Ballard 1999, Friston 2005)  
✅ 도달: 베이즈 갱신으로서의 지각 모델링 (정밀도 가중, 사전 분포 효과)  
✅ 도달: 주의가 정밀도 제어라는 행동 및 계산적 증거  
✅ 도달: 환각·착시·환청의 예측 부호화 설명 (과도한 사전 가중 또는 오차 무시)  

❌ 도달 못 함: 어떻게 예측 오차가 주관적 지각 경험(qualia)을 낳는가 — 계층적 오차 전달이 "빨강이 보인다"는 경험을 설명하지 않는다.  
❌ 도달 못 함: 예측 정확도와 지각의 생생함(vividness) 사이의 관계 — 예측이 잘 맞을 때 세계가 더 실재처럼 느껴지는가, 아니면 덜 느껴지는가?  
❌ 도달 못 함: 선택적 주의가 없는 비주의적 의식(peripheral awareness)의 예측 부호화 설명.  
❌ 도달 못 함: 예측 부호화 모델의 반증 가능한 핵심 예측 — 이론의 유연성이 기각 가능성을 낮춘다.

## 🧬 원리의 회수

상태 예측에서 δ는 감각 예측 오차 $\epsilon = o - \hat{o}$로 표현된다. 이는 신호 예측의 $\delta_{RPE} = r + \gamma V(s') - V(s)$와 구조적으로 동형이다: 둘 다 "실제 − 예측"이며, 둘 다 이 차이가 표상(가치 함수 / 지각 믿음)을 갱신한다.

자유에너지 원리(L5, 04-three-levels-unified.md)는 이 상태 예측을 변분 자유에너지 최소화로 흡수한다: $F = -\mathbb{E}_q[\log p(o, s)] + \mathbb{E}_q[\log q(s)]$. 예측 부호화는 이 자유에너지의 기울기 하강 최소화가 계층적 피질 처리로 구현된 것이다.

신호 예측(01-signal-prediction.md)과의 연결: 선조체의 RPE가 피질 예측 모델을 갱신할 수 있다. 도파민 신호가 상위 피질의 사전 분포(prior)를 조절한다는 가설이 있다 — 보상을 많이 받은 상태가 더 예측 가능한(높은 prior) 상태로 갱신된다. 정책 예측(03-policy-prediction.md)과의 연결: 행동은 상태 예측 모델을 통해 결과를 예측하며, 이것이 능동 추론의 기반이다.

## 🪞 1인칭

눈을 깜빡인 후 방 안을 다시 바라볼 때, 세계가 갑자기 거기 있는 것이 아니다. 뭔가가 먼저 거기 있을 것이라고 준비된 상태에서 감각이 도착하고, 예상과 맞으면 아무 일도 일어나지 않은 것처럼 지각이 매끄럽게 이어진다. 예측 부호화는 이 매끄러움이 능동적 과정임을 말한다 — 피질이 이미 세계의 모습을 생성하고 있고, 감각은 그것을 수정하는 역할을 한다.

낯선 도시에서 처음 지하철 노선도를 볼 때의 감각은 다르다. 예측이 없으므로 오차가 모든 곳에서 터진다 — 모든 글자, 모든 색, 모든 선이 정보로 쏟아진다. 이 인지적 부하감이 바로 높은 예측 오차의 경험이다. 며칠 후 같은 지도를 보면, 눈이 친숙한 패턴 위를 미끄러지듯 지나간다. 예측이 정확해졌기 때문에, 세계는 덜 새롭고 더 투명해진다. 이 두 경험의 대비가 예측 부호화가 기술하는 지각 학습의 현상학이다.

## 📐 예측·반증

**예측 1**: 예측 부호화 모델에 따르면, 반복적으로 제시된 자극에 대한 신경 반응은 새로운 자극보다 감소해야 한다(반복 억제). 그러나 반복이 예측 모델을 강화하지 않는 방식(무작위 제시 간격)으로 설계된 패러다임에서는 이 억제가 관찰되지 않아야 한다.  
*반증 조건*: 예측 가능성과 무관하게 단순 반복만으로 동등한 신경 억제가 발생한다면 예측 부호화보다 적응 모델이 지지된다.

**예측 2**: 환각이 과도한 사전 분포(prior)의 우세에서 비롯된다면, 도파민성 정신병 모델에서 환각은 정밀도 가중 이상으로 설명 가능하다. 항정신병 약물이 도파민-정밀도 연결을 조절하여 환각을 감소시켜야 한다.  
*반증 조건*: 도파민 차단이 정밀도 가중에 영향을 주지 않거나, 환각이 top-down prior 변화 없이 감소한다면 예측 부호화의 환각 모델이 약화된다.

**예측 3**: 주의가 정밀도 제어라면, 특정 감각 채널에 주의를 집중할 때 그 채널의 예측 오차(fMRI BOLD 신호)가 증폭되어야 하고, 동시에 다른 채널의 예측 오차는 감소해야 한다.  
*반증 조건*: 주의가 모든 채널의 오차를 동등하게 증폭하거나, 오차 억제 없이 증폭만 발생한다면 주의-정밀도 동일시 가설이 반박된다.

## 🤔 열린 질문

**예측 부호화는 왜 의식적 지각이 특정 내용을 갖는지 설명하는가?** 계층적 오차 전달이 어떻게 특정 지각 내용(빨강, 고통, 음악)을 만드는지는 불명확하다. 가장 그럴듯한 가설이 자동으로 의식적 경험이 되는 것인가?

**정밀도 가중의 신경화학적 기전은 무엇인가?** 주의가 정밀도를 올린다고 하지만, 어떤 신경조절물질이 어떤 메커니즘으로 이를 구현하는가? 이것이 신호 예측의 도파민 시스템과 어떻게 상호작용하는가?

→ Ch1-03: 정책 예측 — 능동 추론에서 상태 예측 모델이 어떻게 행동 선택으로 확장되는지, 그리고 행동이 세계를 선호 상태로 바꾸는 메커니즘을 추적한다.

---

> 🧩 **Principle** — 상태 예측은 $p(s|o) \propto p(o|s)p(s)$로 표현되는 베이즈 갱신이며, 뇌는 감각을 수동적으로 수신하는 것이 아니라 세계 상태에 대한 가설을 생성하고 감각 오차로 이를 갱신하는 능동적 추론기다.
> 🌉 **Boundary** — 계층적 예측 오차 전달이 어떻게 "이것이 빨강이다"라는 주관적 경험의 내용과 질감을 만드는지는 예측 부호화 틀 안에서 설명되지 않는다.
> 🪞 **Experience** — 친숙한 세계는 매끄럽고 투명하고, 낯선 세계는 정보의 홍수처럼 느껴진다 — 이 대비가 예측 정확도의 현상학이다.

## 📝 연습문제

**기초.** 베이즈 갱신 공식 $p(s|o) \propto p(o|s) \cdot p(s)$에서 강한 사전 분포(strong prior)와 약한 우도(weak likelihood)가 조합될 때 지각에 어떤 결과가 나타나는가? 실제 심리학 현상과 연결하여 설명하라.
<details><summary>해설</summary>

강한 사전 분포는 이전 경험이나 맥락적 기대를 반영한다. 이것이 약한 우도(불명확한 감각 신호)와 조합되면, 사후 분포는 사전 분포에 강하게 당겨진다 — 즉, 사람들은 보고 싶은 것을 본다. 실제 현상: (1) 맥락 효과 — "소금"을 읽은 직후에 모호한 단어를 "설탕"으로 읽는 경향. (2) 전문가 지각 — 체스 고수가 말판 배치를 한눈에 인식하는 것은 강한 패턴 prior 덕분. (3) 확증 편향 — 기존 믿음과 일치하는 모호한 증거를 더 지지하는 방향으로 해석. 이 모든 경우에 강한 prior가 약한 감각 증거를 압도하여 사후 분포를 결정한다.

</details>

**심화.** Rao & Ballard(1999) 모델에서 역방향 연결이 예측을, 순방향 연결이 오차를 전달한다고 할 때, 역방향 연결을 차단하면 지각에 어떤 효과가 예측되는가? 이를 검증하기 위한 실험 패러다임을 설계하라. (실험 윤리 검토 포함)
<details><summary>해설</summary>

**예측**: 역방향 연결 차단 시 하위 피질은 상위의 예측 신호를 받지 못하므로, 모든 감각 입력이 "예측되지 않은" 것처럼 처리된다. 결과: (1) 반복 억제 消失 — 반복 자극에도 지속적으로 강한 반응. (2) 맥락 효과 감소 — prior 효과가 약화. (3) 처리 비효율 증가 — 모든 입력이 오차로 처리되어 계산 부하 증가. **실험 설계**: (1) TMS로 V5(운동 피질)에서 V1으로의 피드백을 일시적으로 방해. (2) 표적 자극: 반복된 운동 자극(예측됨) vs 새로운 운동 자극. (3) 측정: V1 fMRI BOLD 반응 — 역방향 TMS 조건에서 반복 자극에 대한 억제가 감소하면 가설 지지. **윤리**: TMS의 두통·발작 위험, 충분한 사전 동의, 의료적 배제 기준 필요.

</details>

**논문 비평.** Rao & Ballard(1999)의 예측 부호화 모델이 제안된 이후 Friston(2005, 2010)의 자유에너지 원리로 확장되었다. 두 이론의 연속성과 불연속성을 평가하라: Friston의 확장이 Rao & Ballard의 핵심 주장을 강화하는가, 아니면 다른 이론으로 대체하는가?
<details><summary>해설</summary>

**연속성**: Friston은 Rao & Ballard의 계층적 예측 오차 구조를 유지하며 이를 자유에너지 최소화의 신경 구현으로 재해석한다. 핵심 메커니즘(역방향=예측, 순방향=오차)은 동일하다. **불연속성**: (1) Rao & Ballard는 지각에만 초점, Friston은 행동까지 포함(능동 추론). (2) Friston의 자유에너지는 변분 베이즈의 수학적 틀을 명시하며, 이는 Rao & Ballard의 더 직관적 모델보다 엄밀하지만 더 추상적이다. (3) Friston은 모든 자기조직화 시스템에 자유에너지 원리를 적용한다는 훨씬 큰 주장을 한다 — 이는 Rao & Ballard의 겸손한 피질 모델을 넘어선다. **평가**: Friston은 Rao & Ballard를 특수 사례로 흡수하지만, 자유에너지 원리의 과도한 일반성이 반증 가능성을 낮춘다는 비판이 있다. 두 이론의 관계는 "강화"보다 "흡수 및 확장"이 더 적절한 표현이다.

</details>

---

<div align="center">

[◀ 이전: 신호 예측 — 도파민 RPE](./01-signal-prediction.md) · [📚 README](../README.md) · [다음: 정책 예측 — 능동 추론 ▶](./03-policy-prediction.md)

</div>
