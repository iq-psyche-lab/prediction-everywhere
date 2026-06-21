# 🧠 TD 학습의 세 언어: 파블로프·도파민·강화학습은 같은 수학인가

*Rescorla-Wagner 규칙(1972), TD 오차(Sutton-Barto), 도파민 RPE(Schultz 1997)는 수학적으로 동치이며, 세 분야가 독립적으로 발견한 동일한 학습 원리의 세 가지 번역이다.*

## 🎯 횡단 질문

심리학자는 파블로프 조건화를 $\Delta V = \alpha(\lambda - V)$로 기술하고, 강화학습 연구자는 TD 오차 $\delta = r + \gamma V(s') - V(s)$를 최소화하며, 신경과학자는 도파민 뉴런이 보상 예측 오차(RPE)를 발화율로 인코딩한다고 말한다. 이 세 문장은 동일한 현상의 다른 번역인가, 아니면 표면적 유사성만 공유하는 별개의 이론인가?

이 질문이 중요한 이유는 답이 통합의 깊이를 결정하기 때문이다. 만약 세 기술이 수학적으로 동치라면, 하나의 분야에서 얻은 통찰은 다른 두 분야에 즉시 이전된다. 파블로프 실험실의 소거(extinction) 데이터가 TD 알고리즘의 수렴 조건을 검증하고, 도파민 측정이 인공 에이전트의 학습 속도를 예측한다. 반대로, 단순한 은유적 유사성이라면 각 분야는 독립적으로 발전해야 한다.

핵심 주장: 세 이론의 수학적 동치성은 형식적으로 증명 가능하며, 이 동치성이 성립하는 조건(1단계 예측, model-free, 정상적 환경)과 성립하지 않는 조건(계층적 예측, model-based, 비정상 환경)을 명시하는 것이 이 문서의 목표다.

## 🌐 횡단 입력

- **information-prediction (L0)**: 예측 오차 $\delta$는 정보이론적으로 놀라움(surprisal)과 관련되며, 시스템이 환경으로부터 얼마나 많은 정보를 획득했는지를 정량화한다.
- **neuromodulation-arousal (L1)**: 도파민은 전뇌에 광범위하게 투사되어 학습률 $\alpha$를 조절하는 신경조절물질로 기능한다; 각성 상태에 따라 RPE 신호의 크기가 변한다.
- **neurons-neural-codes (L1)**: 복측 피개 영역(VTA)과 흑질(SNc)의 도파민 뉴런은 약 200ms 지연으로 RPE를 발화율로 인코딩한다; 단일 뉴런 기록 데이터가 이 신호를 직접 측정한다.
- **learning-decision (L2)**: 강화학습과 파블로프 조건화는 모두 가치 함수 $V(s)$를 업데이트하는 과정이며, 습관 형성과 목표지향 행동의 신경 기질이 구분된다.
- **IQ AI Lab RL/TD 직결**: OpenAI와 DeepMind의 에이전트(DQN, AlphaGo)가 사용하는 TD($\lambda$) 알고리즘은 Schultz의 도파민 데이터와 동일한 수학을 구현한다; 생물학적 타당성(biological plausibility) 논의의 출발점.

## 🔍 표면의 다양성

세 분야는 서로 다른 언어와 실험 패러다임을 사용한다. 심리학자는 조건 자극(CS)과 무조건 자극(US)을 말하고, 신경과학자는 도파민 뉴런의 발화율 변화를 측정하며, AI 연구자는 에피소드, 상태 전이, 할인 인수를 다룬다. 실험실도 다르다: 파블로프 실험은 동물 행동을 관찰하고, Schultz(1997)의 연구는 깨어있는 원숭이의 단일 뉴런을 기록하며, TD 학습은 컴퓨터 시뮬레이션으로 실행된다.

표면적 다양성은 용어에서도 드러난다. "예측 오차"는 심리학에서 기대 위반(expectancy violation), 신경과학에서 RPE, AI에서 Bellman 오차라고 불린다. "학습률"은 $\alpha$, "할인 인수"는 심리학에서 명시적으로 다루어지지 않는 경우가 많다. "보상"은 US(무조건 자극), 도파민 반응 유발 자극, 환경에서 받는 스칼라 신호 등 다양하게 표현된다.

그러나 이 다양성 아래에 단일 수학 구조가 있다는 것을 보이는 것이 이 문서의 핵심이다. 세 분야의 수식을 나란히 놓으면 동치성이 명확해진다.

## ⚙️ 깊은 동형성

### 분석 1: Rescorla-Wagner 규칙의 형식

Rescorla-Wagner(1972) 규칙은 연합 강도 $V$의 변화를 다음과 같이 기술한다:

$$\Delta V = \alpha \beta (\lambda - \sum V_i)$$

여기서 $\alpha$는 CS의 현저성, $\beta$는 US의 현저성, $\lambda$는 US의 최대 연합 강도(실제 보상), $\sum V_i$는 모든 CS의 현재 예측 합이다. 단일 CS의 경우 $\alpha\beta$를 하나의 학습률로 묶으면:

$$\Delta V = \alpha (\lambda - V)$$

이는 예측 오차 $(\lambda - V)$에 학습률을 곱한 형태다. 핵심은 $\lambda$가 현재 시간 단계에서 받은 실제 보상이고, $V$가 현재 예측이라는 점이다. $\square$

### 분석 2: TD(0) 오차와의 동치

Sutton(1988)의 TD(0) 업데이트 규칙:

$$V(s) \leftarrow V(s) + \alpha \underbrace{[r + \gamma V(s') - V(s)]}_{\delta}$$

여기서 $\delta = r + \gamma V(s') - V(s)$가 TD 오차다. $r$은 현재 시간 단계의 보상, $\gamma V(s')$는 다음 상태 가치의 할인된 추정, $V(s)$는 현재 상태 가치 예측이다.

Rescorla-Wagner와의 동치: 에피소드가 단일 시간 단계($\gamma = 0$)이고 종단 보상만 존재하면 $r = \lambda$, $\gamma V(s') = 0$이 되어:

$$\delta = \lambda - V(s) = \lambda - V$$

이는 Rescorla-Wagner의 $(\lambda - V)$와 완전히 동일하다. $\square$

### 분석 3: 도파민 RPE와의 대응

Schultz(1997)의 핵심 발견: VTA 도파민 뉴런의 발화율은 예측 오차 신호를 인코딩한다.

- **학습 전**: 보상 전달 시 발화율 증가 (오차 = 보상 − 0 > 0)
- **학습 후**: CS 제시 시 발화율 증가, 보상 시 반응 없음 (오차가 CS로 이동)
- **보상 생략 시**: CS 제시 후 보상이 없으면 발화율 감소 (오차 < 0)

이를 수식으로:

$$\text{발화율 변화} \propto \delta = r + \gamma V(s') - V(s)$$

Rescorla-Wagner에서 TD(0)로의 동치와 결합하면, 도파민 발화율 $\propto (\lambda - V)$이며, 이는 세 수식이 동일한 양을 표현함을 보인다. $\square$

### 분석 4: 수치적 동치 조건과 한계

동치성이 성립하는 정확한 조건:

1. **단일 시간 단계**: $\gamma = 0$ 또는 보상이 에피소드 끝에만 주어질 때
2. **선형 가치 함수**: $V(s) = \mathbf{w}^\top \phi(s)$ (일반화된 경우)
3. **정상적 환경**: 전이 확률 $P(s'|s, a)$가 시간에 따라 변하지 않을 때
4. **즉각적 보상**: 미래 보상의 할인이 무시될 때

이 조건들이 깨지면 — 다단계 예측, model-based 추론, 비정상 환경 — TD와 Rescorla-Wagner는 분기한다. 이것이 다음 문서(02-hierarchical-rpe.md)의 출발점이다. $\square$

## 🧪 수렴 증거

### 실험 1: 세 알고리즘의 학습 곡선 비교

다음 Python 코드는 동일한 파블로프 조건화 시나리오에서 세 알고리즘(Rescorla-Wagner, TD(0), 도파민 RPE 시뮬레이션)을 실행하고, RPE가 0으로 수렴하는 과정을 보인다.

```python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)

# 파라미터
alpha = 0.1      # 학습률
lambda_us = 1.0  # US 보상 크기
gamma = 0.0      # 단일 단계: gamma=0이면 R-W와 동치
n_trials = 100

# ─── Rescorla-Wagner ───────────────────────────────────────
def rescorla_wagner(alpha, lambda_us, n_trials):
    V = 0.0
    V_history = []
    delta_history = []
    for _ in range(n_trials):
        delta = lambda_us - V          # 예측 오차
        V += alpha * delta
        V_history.append(V)
        delta_history.append(delta)
    return np.array(V_history), np.array(delta_history)

# ─── TD(0) with gamma=0 (단일 단계, R-W와 동치) ─────────────
def td_zero(alpha, reward, gamma, n_trials):
    V = 0.0
    V_history = []
    delta_history = []
    for _ in range(n_trials):
        V_next = 0.0  # 종단 상태
        delta = reward + gamma * V_next - V   # TD 오차
        V += alpha * delta
        V_history.append(V)
        delta_history.append(delta)
    return np.array(V_history), np.array(delta_history)

# ─── 도파민 RPE 시뮬레이션 ────────────────────────────────────
# Schultz(1997): 발화율 변화 ∝ δ
# 베이스라인 발화율 = 3 Hz, RPE에 선형 비례하여 변화
def dopamine_rpe(alpha, lambda_us, n_trials, baseline_hz=3.0, scale=5.0):
    V = 0.0
    firing_history = []
    delta_history = []
    for _ in range(n_trials):
        delta = lambda_us - V
        firing_rate = baseline_hz + scale * delta  # 발화율 ∝ δ
        V += alpha * delta
        firing_history.append(firing_rate)
        delta_history.append(delta)
    return np.array(firing_history), np.array(delta_history)

# 실행
rw_V, rw_delta = rescorla_wagner(alpha, lambda_us, n_trials)
td_V, td_delta = td_zero(alpha, lambda_us, gamma, n_trials)
da_firing, da_delta = dopamine_rpe(alpha, lambda_us, n_trials)

# ─── 수치 동치 확인 ───────────────────────────────────────────
print("=== 수치적 동치 검증 ===")
print(f"시행 50에서 R-W δ: {rw_delta[49]:.6f}")
print(f"시행 50에서 TD δ:  {td_delta[49]:.6f}")
print(f"시행 50에서 DA δ:  {da_delta[49]:.6f}")
print(f"R-W vs TD 최대 차이: {np.max(np.abs(rw_delta - td_delta)):.2e}")
assert np.allclose(rw_delta, td_delta, atol=1e-10), "R-W와 TD(0)이 다름!"
print("✓ R-W와 TD(0) delta 수열이 동일함 (atol=1e-10)")
print(f"\n최종 가치 추정:")
print(f"  R-W  V(100): {rw_V[-1]:.6f}  (이론값: {lambda_us:.1f})")
print(f"  TD   V(100): {td_V[-1]:.6f}")
print(f"  수렴 후 δ→0: R-W={rw_delta[-1]:.6f}, TD={td_delta[-1]:.6f}")

fig, axes = plt.subplots(1, 3, figsize=(15, 4))

axes[0].plot(rw_V, label='R-W 가치 V', color='steelblue')
axes[0].plot(td_V, label='TD(0) 가치 V', color='tomato', linestyle='--')
axes[0].axhline(lambda_us, color='gray', linestyle=':', label='참값 λ')
axes[0].set_title('가치 함수 수렴')
axes[0].set_xlabel('시행 수'); axes[0].set_ylabel('V')
axes[0].legend()

axes[1].plot(rw_delta, label='R-W δ', color='steelblue')
axes[1].plot(td_delta, label='TD(0) δ', color='tomato', linestyle='--')
axes[1].axhline(0, color='gray', linestyle=':')
axes[1].set_title('예측 오차 δ → 0 수렴')
axes[1].set_xlabel('시행 수'); axes[1].set_ylabel('δ')
axes[1].legend()

axes[2].plot(da_firing, label='도파민 발화율', color='orchid')
axes[2].axhline(3.0, color='gray', linestyle=':', label='베이스라인 (3 Hz)')
axes[2].set_title('도파민 발화율 (∝ δ)')
axes[2].set_xlabel('시행 수'); axes[2].set_ylabel('발화율 (Hz)')
axes[2].legend()

plt.tight_layout()
plt.savefig('td_three_languages_convergence.png', dpi=150, bbox_inches='tight')
print("\n그래프 저장: td_three_languages_convergence.png")
```

**출력 해석**: `rw_delta`와 `td_delta` 수열이 수치적으로 동일하며(`atol=1e-10`), 두 수열 모두 시행이 거듭될수록 0으로 지수 감소한다. 도파민 발화율은 베이스라인(3 Hz)으로 수렴하여 Schultz(1997)의 관찰 — 학습 후 보상 시 반응 없음 — 을 재현한다.

### 실험 2: CS 이동(credit assignment) 시뮬레이션

Schultz(1997)의 핵심 실험은 CS 제시 시점으로 RPE가 이동하는 것이다. 다음은 이를 TD(0)로 재현한 시뮬레이션이다.

```python
import numpy as np

# 2단계 MDP: CS(s0) → US(s1) → 종단
# gamma > 0일 때만 TD가 R-W와 달리 예측을 앞 단계로 전파
def td_credit_shift(alpha=0.05, gamma=0.9, n_episodes=200):
    """
    s0(CS) → s1(보상) → 종단
    학습 전: s1에서만 δ > 0
    학습 후: s0에서 δ > 0, s1에서 δ ≈ 0  (Schultz 1997 재현)
    """
    V = {0: 0.0, 1: 0.0}  # 두 상태의 가치 초기화
    r = {0: 0.0, 1: 1.0}  # s1에서만 보상
    
    delta_s0_history = []
    delta_s1_history = []
    
    for ep in range(n_episodes):
        # s0 → s1 전이
        delta_s0 = r[0] + gamma * V[1] - V[0]
        V[0] += alpha * delta_s0
        
        # s1 → 종단
        delta_s1 = r[1] + gamma * 0.0 - V[1]
        V[1] += alpha * delta_s1
        
        delta_s0_history.append(delta_s0)
        delta_s1_history.append(delta_s1)
    
    return np.array(delta_s0_history), np.array(delta_s1_history)

d0, d1 = td_credit_shift()
print(f"초기 δ(CS): {d0[0]:.3f}, δ(US): {d1[0]:.3f}")
print(f"최종 δ(CS): {d0[-1]:.3f}, δ(US): {d1[-1]:.3f}")
print("→ 도파민 RPE가 CS로 이동: Schultz(1997) 재현")
```

**반례와 경계**: 이 시뮬레이션은 $\gamma > 0$일 때만 credit shift가 발생한다는 것을 보인다. $\gamma = 0$이면 Rescorla-Wagner와 동치이지만 예측이 앞 단계로 전파되지 않는다. 이것이 Rescorla-Wagner의 알려진 한계(블로킹 설명 가능, 2차 조건화 설명 어려움)와 연결된다.

## 🌉 간극의 위치

- ✅ **수학적 동치 성립**: 단일 시간 단계, $\gamma = 0$, 단순 선형 환경에서 세 알고리즘은 동일한 $\delta$ 수열을 생성한다.
- ✅ **질적 예측 일치**: 차단(blocking), 과잉기대(overexpectation), 소거(extinction) 현상을 세 이론 모두 예측한다.
- ✅ **실험적 교차 검증**: Schultz(1997)의 도파민 데이터는 TD 모델로 정량적으로 피팅된다 (Montague et al., 1996).
- ❌ **시간 구조 차이**: 파블로프 실험의 시행 단위와 TD의 시간 단계 대응이 항상 명확하지 않다.
- ❌ **할인 인수의 신경 기질**: $\gamma$에 해당하는 뇌 메커니즘이 단일하지 않으며, 측좌핵, 안와전두피질 등 여러 구조가 관여한다.
- ❌ **확률적 보상의 처리**: 도파민 뉴런은 평균 RPE뿐 아니라 분포적 RPE를 인코딩한다는 최근 증거(Dabney et al., 2020)가 표준 TD 모델을 넘어선다.
- ❌ **1인칭 경험**: 수학적 동치성은 "놀라움이 느껴진다"는 현상학적 경험을 설명하지 않는다. $\delta$가 느껴짐(felt surprise)의 구조적 원인이라고 해도, 느껴짐 자체가 $\delta$로 환원되지는 않는다.

## 🧬 원리의 회수

세 분야의 독립적 발견이 동일한 수학으로 수렴한다는 것은 단순한 우연이 아니다. 이는 환경으로부터 학습하는 모든 시스템이 예측 오차를 최소화해야 한다는 더 깊은 원리를 반영한다. 파블로프의 실험실, Schultz의 전극, Sutton-Barto의 알고리즘은 서로 다른 방향에서 같은 진실을 발굴했다.

수렴이 중요한 이유는 설명적 단순성 때문만이 아니다. 단일 원리가 세 수준을 관통한다면, 한 수준에서의 조작이 다른 수준에서 예측 가능한 결과를 낳는다. 도파민을 차단하면(약리학적 개입) 파블로프 조건화가 손상되고(행동), TD 에이전트의 학습이 멈춘다(계산). 이 세 사실이 연결된다.

그러나 이 통합은 조건부다. 다음 문서에서 보일 것처럼, 계층적 예측, model-based 추론, 불확실성의 조절로 넘어가면 동치성이 깨지고 세 분야는 다시 분기한다. 통합의 영역과 한계를 동시에 보는 것이 Synthesis의 목표다.

## 🪞 1인칭

카페에서 커피를 기다리는 동안 예상보다 빨리 음료가 나왔을 때, 나는 작은 기쁨을 느낀다. 이것이 RPE의 느낌이다 — $\delta > 0$. 반대로 기다려도 나오지 않으면 불쾌한 긴장이 생긴다 — $\delta < 0$. 그런데 이 경험이 VTA 도파민 뉴런의 발화율 변화와 수학적으로 같은 것이라고 말할 때, 무언가 이상하다. 발화율은 측정 가능하지만, 그 기쁨은 — 커피를 받았을 때의 그 특정한 느낌은 — 수식 바깥에 있다.

수학적 동치성은 "놀라움이 언제, 얼마나 발생하는가"를 설명하지만 "놀라움이 어떻게 느껴지는가"를 설명하지 않는다. $\delta = 1.0$이라는 숫자는 뇌가 그 순간 처리할 오차의 크기를 알려주지만, 오차를 처리하는 것이 어떤 느낌인지를 알려주지 않는다. 이 간극은 이 레포 전체를 관통하는 핵심 긴장이다.

## 📐 예측·반증

**예측 1**: 도파민 뉴런을 광유전학적으로 억제하면 파블로프 조건화의 학습률이 $\alpha$에 비례하여 감소한다.
- 반증 조건: 억제 후에도 학습 속도가 변하지 않거나, 억제 효과가 자극 유형에 따라 비선형적이면 단순 RPE 가설이 틀렸다.

**예측 2**: TD($\lambda$) 알고리즘에서 $\lambda$를 0에서 1로 증가시키면 도파민 뉴런의 RPE 이동 속도(credit shift 속도)와 상관관계를 보인다.
- 반증 조건: 신경 데이터에서 $\lambda$ 유사 파라미터의 독립적 변동이 TD 예측과 체계적으로 불일치하면.

**예측 3**: 분포적 RPE 가설(Dabney et al., 2020)에 따르면, 서로 다른 도파민 뉴런은 서로 다른 $\gamma$를 사용한다; 따라서 같은 자극에 대해 도파민 뉴런 간 발화 시간 패턴이 이질적이다.
- 반증 조건: 고해상도 동시 기록에서 뉴런 간 발화 패턴이 단일 $\gamma$로 설명 가능하면.

## 🤔 열린 질문

세 알고리즘의 동치성은 단순 환경에서 성립하지만, 현실의 뇌는 계층적 예측을 수행한다. VTA의 단순 RPE를 넘어, 전전두피질(PFC)이 모델 기반 예측을 제공하고, 선조체(striatum)의 배측과 복측이 서로 다른 종류의 가치를 계산한다. 이 계층 구조는 어떻게 작동하는가? 상위 수준의 RPE는 하위 수준의 RPE와 어떻게 통합되는가? → 다음 문서(02-hierarchical-rpe.md)에서 탐구한다.

---

> 🧩 **Principle** — 예측 오차 $\delta = \text{실제} - \text{예측}$는 파블로프 심리학, 도파민 신경과학, TD 강화학습이 독립적으로 발견한 동일한 학습 원리이며, 단순 환경에서 수학적으로 동치다.

> 🌉 **Boundary** — 이 동치성은 단일 시간 단계, model-free, 정상적 환경에서만 성립한다; 계층적 예측, 비정상 환경, 분포적 RPE로 확장하면 세 이론은 분기한다.

> 🪞 **Experience** — $\delta$가 느껴짐의 수학적 원인이라 해도, "놀라움이 느껴진다"는 사실 자체는 $\delta = r + \gamma V(s') - V(s)$로 환원되지 않는다.

## 📝 연습문제

**기초.** Rescorla-Wagner 규칙에서 $\alpha = 0.3$, $\lambda = 1.0$, $V_0 = 0$으로 시작할 때, 몇 번의 시행 후 $V$가 0.95에 도달하는가? TD(0)에서 $\gamma = 0$으로 설정하면 같은 결과가 나오는가?

<details><summary>해설</summary>

$V_n = \lambda(1 - (1-\alpha)^n)$이므로 $0.95 = 1 \cdot (1 - 0.7^n)$에서 $0.7^n = 0.05$, $n = \log(0.05)/\log(0.7) \approx 8.4$, 즉 9번째 시행. TD(0)에서 $\gamma = 0$이면 $\delta = r - V(s)$이고 $r = \lambda$이므로 Rescorla-Wagner와 수학적으로 동치다. 따라서 동일한 결과가 나온다.

</details>

**심화.** 파블로프 조건화에서 "2차 조건화(second-order conditioning)"는 CS2 → CS1 → US 순서로 학습이 이루어진다. Rescorla-Wagner 규칙만으로 이 현상을 설명하기 어려운 이유를 설명하고, TD(0)에서 $\gamma > 0$이면 어떻게 이 현상이 자연스럽게 설명되는지 수식으로 보여라.

<details><summary>해설</summary>

Rescorla-Wagner는 현재 시행의 US(무조건 자극)만을 오차 신호로 사용하므로, CS1만 US와 직접 연합된다. CS2는 CS1과 연합되지만, Rescorla-Wagner에서 CS1이 US 역할을 하려면 CS1의 가치가 오차 신호로 사용되어야 하는데, 이 메커니즘이 없다.

TD(0)에서 $\gamma > 0$이면: CS2 제시 시 $\delta = r_{CS2} + \gamma V(CS1) - V(CS2)$. CS1이 이미 $V(CS1) \approx \lambda$를 획득했다면, CS2 제시만으로도 $\delta = \gamma\lambda - V(CS2) > 0$이 되어 학습이 일어난다. 이것이 2차 조건화의 자연스러운 설명이다.

</details>

**논문 비평.** Schultz et al. (1997) "A Neural Substrate of Prediction and Reward" (Science)의 그림 1을 보면, 도파민 뉴런이 세 가지 다른 조건(보상만, CS+보상, CS+보상 생략)에서 다르게 반응한다. 이 데이터가 단순 TD(0) 모델로 완전히 설명되는지, 아니면 추가 메커니즘이 필요한지 논하라.

<details><summary>해설</summary>

Schultz(1997)의 데이터는 TD(0) 모델로 질적으로 잘 설명된다: 보상 전달 시 양성 RPE, CS 이동 후 CS에서 양성 RPE, 보상 생략 시 음성 RPE. 그러나 몇 가지 한계가 있다: (1) 도파민 뉴런의 불균일성(일부는 양성 RPE만, 일부는 음성 RPE도 반응) — 분포적 RPE(Dabney et al., 2020) 가설이 필요하다. (2) 발화율의 절대 크기와 TD $\delta$의 정량적 대응이 모든 자극에서 선형적이지 않다. (3) 도파민은 동기(salience) 신호도 인코딩하며, 이는 순수 RPE를 넘어선다(Berridge, 2007). 따라서 표준 TD(0)는 필요조건이지만 충분하지 않다.

</details>

---

<div align="center">

[◀ 이전: 세 수준의 통합](../ch1-three-levels/04-three-levels-unified.md) · [📚 README](../README.md) · [다음: RPE의 계층적 구조 ▶](./02-hierarchical-rpe.md)

</div>
