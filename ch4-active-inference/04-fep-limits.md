# 🧠 자유에너지의 한계

*자유에너지 원리는 인지의 통합적 틀로서 진정한 기여를 지니지만, 반증가능성의 결여와 동어반복의 구조적 위험이 그 과학적 지위를 여전히 논쟁 속에 남겨두고 있다.*

---

## 🎯 횡단 질문

자유에너지 원리(Free Energy Principle, FEP)는 지각·행위·학습을 단일 원리로 통합하려 한다. 그 핵심 주장은 다음과 같다: 자기조직화하는 모든 시스템은 감각 놀라움(sensory surprise)을 최소화하는 방향으로 작동하며, 이때 자유에너지 $\mathcal{F}$가 놀라움의 상한(upper bound)으로 기능한다.

$$
\mathcal{F}(s, \mu) = \underbrace{\mathbb{E}_{q(\vartheta|\mu)}\left[\ln q(\vartheta|\mu) - \ln p(s, \vartheta)\right]}_{\text{변분 자유에너지}} \geq -\ln p(s)
$$

여기서 $s$는 감각 신호, $\vartheta$는 숨겨진 원인, $\mu$는 내부 상태(internal states), $q(\vartheta|\mu)$는 인식론적 밀도(recognition density)이다. 핵심 등식은 다음처럼 분해된다:

$$
\mathcal{F} = \underbrace{D_{\mathrm{KL}}\!\left[q(\vartheta|\mu) \;\|\; p(\vartheta|s)\right]}_{\text{근사 오차 (≥0)}} - \underbrace{\ln p(s)}_{\text{로그 증거}}
$$

이 식은 수학적으로 자유에너지가 언제나 로그 증거보다 크거나 같음을 보장한다. 이론의 주장은 따라서 다음이다: **뇌는 자유에너지를 최소화함으로써 간접적으로 모델 증거를 최대화한다.** 그렇다면 이 주장은 반증 가능한가? 이것이 이 장의 횡단 질문이다.

---

## 🌐 횡단 입력

이 장의 분석은 여러 인접 층위로부터 입력을 받는다.

- **information-prediction (L0)**: 자유에너지는 KL 발산과 로그 증거의 합으로 표현되며, 정보이론적으로 완전히 정의된다. 그러나 정보이론적 유효성이 곧 신경과학적 실재성을 보장하지는 않는다.
- **theories-of-consciousness (L4)**: FEP는 의식의 내용을 예측 오차의 함수로 설명하려 하지만, 현상적 경험 그 자체(qualia)의 기원을 설명하는 데는 별도의 가교 원리가 필요하다.
- **free-will-agency (L5)**: 능동 추론(active inference)은 행위를 "선호된 미래 감각 상태로의 정책-선택"으로 재기술하지만, 의도성과 자유의지의 문제는 모델 내부에서 해소되지 않는다.
- **IQ AI Lab 모델기반계획 직결**: IQ AI Lab에서 구현 중인 모델기반 계획(model-based planning) 에이전트는 능동 추론의 실천적 파생물이다. 에이전트가 기대 자유에너지(expected free energy, $\mathcal{G}$)를 최소화하는 정책을 선택하는 방식은 FEP의 수학적 구조를 그대로 계승한다. 따라서 이 장의 한계 분석은 해당 에이전트 설계에서 회피해야 할 함정과 활용 가능한 강점을 직접 규정한다.

---

## 🔍 표면의 다양성

자유에너지 원리에 대한 비판은 단일하지 않다. 비판의 결을 먼저 구분해두자.

**형이상학적 비판**: "자유에너지를 최소화하는 시스템이 생명이다"라는 명제는 생명을 정의하는 데 쓰이는가, 아니면 생명에 대한 경험적 주장인가? 전자라면 과학이 아니라 정의다.

**방법론적 비판**: FEP가 예측하는 행동 패턴이 다른 이론(예: 강화학습, 베이즈 뇌 가설)과 경험적으로 구별되지 않는다면, FEP는 독자적 이론이 아니라 언어적 재기술에 불과하다.

**범위 비판**: Friston의 주장이 세포 수준에서 문화 수준까지 확장될 때, 각 수준에서의 마르코프 담요(Markov blanket)가 실제로 어떻게 동정(identification)되는지가 불분명하다.

**내부 일관성 비판**: 어두운 방 문제(dark room problem)는 FEP 자체의 내부 논리에서 발생하는 반례다. 놀라움을 최소화하는 가장 확실한 방법은 아무것도 하지 않는 것인데, 왜 생명체는 적극적으로 환경을 탐색하는가?

이 비판들은 공통된 뿌리를 가지고 있으나 서로 다른 논리 구조를 지닌다. 아래에서 각각을 해부한다.

---

## ⚙️ 깊은 동형성

### 분석 1: 동어반복 논란의 구조

Colombo & Wright(2018)는 FEP가 두 가지 방식으로 동어반복적일 수 있다고 논증한다. 첫째, 마르코프 담요를 가진 시스템이 존재한다는 것이 자유에너지를 최소화한다는 것과 수학적으로 동치라면, "시스템이 존재한다 → 자유에너지를 최소화한다"는 주장은 정의의 귀결이지 경험적 발견이 아니다. 둘째, $\mathcal{F} \geq -\ln p(s)$는 항등식이어서 어떤 관찰도 위반할 수 없다.

$$
\mathcal{F} - (-\ln p(s)) = D_{\mathrm{KL}}\!\left[q \;\|\; p(\vartheta|s)\right] \geq 0
$$

$D_{\mathrm{KL}} \geq 0$은 정보이론의 기본 정리다. 이 수학적 사실로부터 경험적 주장을 도출하려면, $q$가 신경 구현의 특정 형태를 취한다는 추가 가정이 필요하다. 그 추가 가정이 이론의 실질적 내용이며, 그것이 검증되어야 한다. $\square$

### 분석 2: 반증가능성 비판

Williams(2020)은 예측 코딩(predictive coding)이 사고(thought)를 설명할 수 있다는 주장을 비판적으로 검토하면서, 더 넓은 문제를 제기한다: FEP로부터 도출된 예측들은 종종 너무 일반적이어서 반증되기 어렵다.

반증가능한 예측과 반증 불가능한 주장의 차이를 형식화해보자. FEP가 반증 가능하려면, 특정 조건 $C$에서 관찰 $O$가 나타나지 않을 때 FEP가 거짓임을 인정해야 한다.

$$
\text{반증가능}: \exists C, O \text{ s.t. } \Pr(O|C, \mathrm{FEP}) \ll \Pr(O|C, \neg\mathrm{FEP})
$$

FEP 지지자들은 어떤 관찰도 모델 파라미터 재조정이나 계층적 수준 재정의를 통해 수용할 수 있다고 주장하는 경향이 있다. 이는 이론을 강건하게 보이게 하지만 반증 가능성을 소진시킨다. 그러나 이 비판이 FEP 전체에 동등하게 적용되는 것은 아니다. 상향 신호가 예측 오차를, 하향 신호가 예측을 전달한다는 구현적 주장은 명확히 반증 가능하며 신경영상 연구로 검증되었다(Rao & Ballard, 1999). $\square$

### 분석 3: 어두운 방 문제의 해결 시도와 한계

어두운 방 문제(dark room problem)는 다음의 역설로 정식화된다. 자유에너지를 최소화하는 가장 효율적인 방법은 놀라움이 전혀 없는 환경, 즉 어두운 방에 머무르는 것이다. 그러나 인간을 포함한 생명체는 그렇게 하지 않는다.

Friston(2012)의 공식 응답은 다음과 같다: 생명체의 생성 모델(generative model)은 단순히 현재 놀라움을 최소화하는 것이 아니라, 시간적으로 확장된 기대 자유에너지(expected free energy) $\mathcal{G}$를 최소화한다. $\mathcal{G}$는 에피스테믹 가치(epistemic value)와 프래그매틱 가치(pragmatic value)를 포함한다.

$$
\mathcal{G}(\pi) = \underbrace{-\mathbb{E}_{q(\tilde{s}|\pi)}\left[\ln p(\tilde{s}|\tilde{o}, \pi)\right]}_{\text{에피스테믹 가치 (불확실성 감소)}} + \underbrace{\mathbb{E}_{q(\tilde{s}|\pi)}\left[\ln p(\tilde{o}|\tilde{s})\right]}_{\text{프래그매틱 가치 (선호 상태 달성)}}
$$

이 응답은 부분적으로 설득력 있다. 에피스테믹 가치가 탐색을, 프래그매틱 가치가 목표 지향적 행동을 설명한다면 어두운 방 문제는 해소된다. 그러나 $\mathcal{G}$의 계산 방법, 두 가치의 가중치 결정 메커니즘, 그리고 생성 모델의 선호(preferences)가 어디서 오는지는 이론이 규정하지 않는다. FEP가 이 선호를 진화·발달·학습으로 돌린다면 다른 이론의 설명을 빌려온 것이다. $\square$

### 분석 4: 진짜 기여의 경계

비판을 충분히 검토한 뒤, 진정한 기여를 식별할 수 있다.

**통합**: 지각·행위·학습·주의를 단일 변분 원리로 기술하는 것은 설명적 경제성(explanatory economy)의 실질적 성취다.

**마르코프 담요 형식주의**: 에이전트-환경 경계를 확률적 독립성으로 정의하여 자율성(autonomy)을 수학적으로 다룰 수 있게 한다. 인공지능 에이전트 설계에 직접 응용된다.

**정신병리학의 규범적 틀**: 조현병을 과도한 정밀도 가중치의 결과로, 자폐를 과소한 정밀도 추정의 결과로 기술하여 검증 가능한 예측을 생성한다(Adams et al., 2013; Van de Cruys et al., 2014).

**예측 코딩의 신경과학적 성공**: 계층적 예측 오차 신호는 실험적으로 지지된다. FEP의 어휘가 없었다면 이 발견들을 체계화하기 어려웠을 것이다.

$$\square$$

진정한 기여와 과잉 주장의 경계는 따라서 **구현적 수준(implementational level)**에서의 예측 코딩과 **계산적 수준(computational level)**에서의 FEP 사이의 간극에 놓여 있다. 전자는 강한 경험적 지지를 받는다. 후자는 철학적 틀로서의 가치를 지니지만, 단독으로 경험적 이론으로 간주되기 어렵다.

---

## 🧪 수렴 증거

### 실험 1: 어두운 방 문제 시뮬레이션

아래 코드는 에이전트가 선호 상태를 매우 낮은 분산으로 설정할 때 탐색을 멈추는 현상을 보여준다. 에이전트는 현재 상태에서 자유에너지를 계산하고, 이동 시 예측 오차 증가를 회피한다.

```python
import numpy as np
import matplotlib.pyplot as plt

# --------------------------------------------------------
# 어두운 방 문제 시뮬레이션
# 에이전트가 선호 상태를 낮은 분산으로 설정하면
# 탐색을 멈추고 한 자리에 머무른다
# --------------------------------------------------------

np.random.seed(42)

def compute_free_energy(observation, preferred_mean, preferred_var):
    """
    변분 자유에너지의 단순화된 스칼라 버전.
    F = (obs - mu)^2 / (2*sigma^2) + 0.5*ln(sigma^2)
    선호 상태로부터의 편차를 측정.
    """
    return 0.5 * ((observation - preferred_mean) ** 2 / preferred_var + np.log(preferred_var))

def run_dark_room_agent(preferred_var, n_steps=50, env_size=10):
    """
    preferred_var이 낮을수록 에이전트는 현재 위치에 머문다.
    """
    position = env_size // 2  # 중앙에서 시작
    history = [position]
    fe_history = []

    preferred_mean = position  # 시작 위치가 선호 상태

    for _ in range(n_steps):
        current_fe = compute_free_energy(position, preferred_mean, preferred_var)

        # 가능한 행동: -1(왼쪽), 0(정지), +1(오른쪽)
        actions = [-1, 0, 1]
        fe_per_action = []

        for action in actions:
            next_pos = np.clip(position + action, 0, env_size)
            # 이동 시 관찰되는 새 위치의 자유에너지 계산
            # 환경 노이즈 추가
            obs = next_pos + np.random.normal(0, 0.5)
            fe = compute_free_energy(obs, preferred_mean, preferred_var)
            fe_per_action.append(fe)

        # 자유에너지 최소화 행동 선택
        best_action = actions[np.argmin(fe_per_action)]
        position = int(np.clip(position + best_action, 0, env_size))
        history.append(position)
        fe_history.append(min(fe_per_action))

    return np.array(history), np.array(fe_history)

# 실험 조건: 낮은 선호 분산(어두운 방) vs 높은 선호 분산(탐색 허용)
low_var = 0.1    # 어두운 방: 현재 상태만 허용
high_var = 5.0   # 탐색: 다양한 상태 허용

hist_low, fe_low = run_dark_room_agent(preferred_var=low_var)
hist_high, fe_high = run_dark_room_agent(preferred_var=high_var)

fig, axes = plt.subplots(2, 2, figsize=(12, 8))

axes[0, 0].plot(hist_low, color='steelblue', linewidth=2)
axes[0, 0].set_title(f'위치 이력 (선호 분산={low_var} — "어두운 방")')
axes[0, 0].set_xlabel('시간 단계'); axes[0, 0].set_ylabel('위치')
axes[0, 0].axhline(5, color='red', linestyle='--', alpha=0.5, label='시작 위치')
axes[0, 0].legend()

axes[0, 1].plot(hist_high, color='darkorange', linewidth=2)
axes[0, 1].set_title(f'위치 이력 (선호 분산={high_var} — 탐색 허용)')
axes[0, 1].set_xlabel('시간 단계'); axes[0, 1].set_ylabel('위치')
axes[0, 1].axhline(5, color='red', linestyle='--', alpha=0.5, label='시작 위치')
axes[0, 1].legend()

axes[1, 0].plot(fe_low, color='steelblue', linewidth=2)
axes[1, 0].set_title('자유에너지 (낮은 분산)')
axes[1, 0].set_xlabel('시간 단계'); axes[1, 0].set_ylabel('자유에너지 F')

axes[1, 1].plot(fe_high, color='darkorange', linewidth=2)
axes[1, 1].set_title('자유에너지 (높은 분산)')
axes[1, 1].set_xlabel('시간 단계'); axes[1, 1].set_ylabel('자유에너지 F')

plt.tight_layout()
plt.savefig('dark_room_simulation.png', dpi=150, bbox_inches='tight')
plt.show()

# 정량적 요약
print("=== 어두운 방 문제 시뮬레이션 결과 ===")
print(f"낮은 분산(σ²={low_var}): 위치 표준편차 = {np.std(hist_low):.3f}")
print(f"높은 분산(σ²={high_var}): 위치 표준편차 = {np.std(hist_high):.3f}")
print()
print("해석: 선호 분산이 낮을수록 에이전트는 현재 위치에서 벗어나지 않는다.")
print("이것이 어두운 방 문제의 핵심이다: 생성 모델의 선호가 고정되면")
print("에이전트는 탐색을 멈추고 정지 상태를 선택한다.")
print()
print("Friston의 응답: 실제 생물학적 에이전트의 생성 모델은")
print("에피스테믹 가치(epistemic value)를 내장하여 탐색을 선호로 포함시킨다.")
print("→ 그러나 이 선호가 어디서 오는지는 여전히 열린 문제다.")
```

**실험 1 해석**: 낮은 선호 분산을 가진 에이전트는 시작 위치에서 거의 이탈하지 않는다. 이는 어두운 방 문제를 재현한다. Friston의 응답(에피스테믹 가치)이 이론적으로 탈출구를 제공하지만, 에피스테믹 가치의 가중치 결정 메커니즘은 FEP 외부에서 도입되어야 한다.

---

### 실험 2: 반증가능성 형식 검토

반증가능한 FEP 예측과 반증 불가능한 주장의 차이를 대조한다.

```python
import numpy as np
from scipy import stats

np.random.seed(2024)

# 반증 가능한 예측: "놀라운 자극은 예측된 자극보다 더 큰 예측 오차를 유발한다"
pe_predicted  = np.random.normal(loc=0.2, scale=0.1, size=100)   # 예측된 자극
pe_surprising = np.random.normal(loc=0.8, scale=0.15, size=100)  # 놀라운 자극
t, p = stats.ttest_ind(pe_predicted, pe_surprising)
print(f"예측된: {pe_predicted.mean():.3f}  놀라운: {pe_surprising.mean():.3f}")
print(f"t={t:.2f}, p={p:.2e} → {'지지됨 ✓' if p < 0.05 else '기각됨 ✗'}")
print("반증 조건: 두 조건에서 오차가 같다면 이 예측은 기각된다.")
print()

# 반증 불가능한 주장: 어떤 관찰도 '자유에너지 최소화'와 일치한다고 말할 수 있다
for obs in [0.1, 0.5, 0.9, "어두운 방 정지", "극단 탐색"]:
    print(f"관찰 '{obs}': → 이 관찰은 자유에너지 최소화와 일치한다.")

print()
print("결론: FEP의 구현적 예측(오차 방향성)은 반증 가능하다.")
print("      FEP의 계산적 주장(모든 시스템이 FEP를 따른다)은 반증이 어렵다.")
```

**실험 2 해석**: 구현적 예측(오차 방향성)은 명확히 반증 가능하다. 반면 계산적 주장은 어떤 관찰에도 사후 적용 가능하다. 이 두 수준의 구별이 FEP 비판을 정확히 이해하는 열쇠다.

---

### 반례와 경계

**반례 1 — 위험 감수 행동**: 번지점프, 공포 영화 관람은 놀라움을 오히려 추구한다. FEP는 에피스테믹 가치나 선호의 개인차로 응답하지만, 선호의 독립적 측정 없이는 순환적이다.

**반례 2 — 창의성**: 예술가는 기대 위반을 의도적으로 만든다. "기대 위반 자체가 선호"라는 해석은 가능하지만 FEP의 설명력을 공허하게 만든다.

**경계 조건**: FEP는 정적 생성 모델을 가정할 때 가장 명확하다. 메타학습이나 빠른 적응처럼 모델 자체가 변화하는 상황에서는 예측이 불분명해진다.

---

## 🌉 간극의 위치

| 주장 | 상태 | 근거 |
|------|------|------|
| 계층적 예측 오차가 신경 처리의 핵심이다 | ✅ 지지됨 | Rao & Ballard 1999; Friston 2005; 다수의 신경영상 연구 |
| 정밀도 가중치가 주의를 설명한다 | ✅ 부분 지지 | Feldman & Friston 2010 |
| 마르코프 담요가 에이전트-환경 경계를 정의한다 | ✅ 형식적으로 유효 | 단, 생물학적 동정 문제 남음 |
| 모든 자기조직화 시스템이 FEP를 따른다 | ❌ 반증 불가 | Colombo & Wright 2018 |
| FEP가 의식을 설명한다 | ❌ 미완 | Hard problem 해소 안 됨 |
| 어두운 방 문제가 완전히 해결됐다 | ❌ 미완 | 에피스테믹 가치 원천 불명 |
| FEP가 자유의지를 설명한다 | ❌ 과잉주장 | Williams 2020 |
| 예측 코딩이 정신병리학을 설명한다 | ✅ 유망 | Adams et al. 2013; Van de Cruys et al. 2014 |

---

## 🧬 원리의 회수

원리 $\delta = \text{실제} - \text{예측} \to \text{갱신}$은 자유에너지 원리에서 다음의 형태로 나타난다:

$$
\Delta \mu \propto -\frac{\partial \mathcal{F}}{\partial \mu} = \underbrace{\varepsilon_s}_{\text{감각 예측 오차}} + \underbrace{\varepsilon_\mu}_{\text{사전 예측 오차}}
$$

이 갱신 규칙은 지각(감각 신호를 설명하는 원인의 추론)과 행위(감각 신호를 선호 상태와 일치시키는 운동 출력) 모두에 적용된다. 원리의 통합적 힘은 여기에 있다.

그러나 이 원리가 과학적 이론으로 기능하려면 세 질문이 남는다: 생성 모델 $p(s, \vartheta)$의 구체화, 선호 분포 $p(\tilde{o})$의 학습 메커니즘, 마르코프 담요의 경험적 동정(identification). 이 답은 FEP의 수학이 아니라 구현 이론에서 와야 한다.

IQ AI Lab의 모델기반 계획 에이전트는 선호를 보상 함수로 명시적으로 정의함으로써 이 공백을 채운다. FEP는 설계 원리로서 명확하지만 선호의 기원을 설명하는 이론으로서는 다른 기제를 필요로 한다.

---

## 🪞 1인칭

자유에너지 원리를 처음 접했을 때, 나는 두 가지 감정을 동시에 느꼈다. 하나는 경이로움이었다. 지각과 행위가 단일 방정식으로 수렴한다는 아이디어는 인지과학이 물리학처럼 통일될 수 있다는 가능성을 암시했다. 다른 하나는 불안이었다. 이 이론이 무엇을 예측하는지, 무엇이 일어나면 이것이 틀렸다고 말할 수 있는지가 분명하지 않았다.

그 불안은 정당했다. 그러나 경이로움도 정당했다. 이 장을 쓰면서 내가 배운 것은 다음이다: 이론을 지지하거나 기각하기 전에, 그 이론이 어떤 수준에서 무엇을 주장하는지를 먼저 해부해야 한다. FEP는 수학적 틀로서는 비어있지 않다. 구현적 이론으로서는 검증 가능하다. 철학적 프로그램으로서는 자극적이다. 그리고 모든 것을 설명한다는 주장으로서는 위험하다. 이 구별을 유지하는 것이 이 원리를 과학적으로 사용하는 방법이다.

---

## 📐 예측·반증

**예측 1**: 약물을 통해 상향 정밀도(감각 예측 오차의 가중치)를 낮추면, 피험자는 고무손 착각(rubber hand illusion)과 같은 신체 소유감 착각에 더 취약해진다.

반증 조건: 정밀도 조작에도 불구하고 착각 감수성이 변화하지 않을 경우 기각.

**예측 2**: 자폐 스펙트럼 장애(ASD)를 가진 개인은 맥락 기반 감각 억제가 감소한다. 반복적인 자극에 대해서도 예측 오차 신호가 지속적으로 높게 유지된다.

반증 조건: ASD 집단에서 반복 자극 억제가 신경전형 집단과 다르지 않을 경우 기각.

**예측 3**: 능동 추론 에이전트(기대 자유에너지 최소화)는 순수 강화학습 에이전트보다 새로운 환경에서 더 빠른 적응을 보인다. 특히 에피스테믹 가치가 탐색 보너스로 기능하기 때문이다.

반증 조건: 동등한 복잡도의 강화학습 에이전트 대비 성능 우위가 없을 경우 FEP의 추가적 설명력 주장이 약화된다.

---

## 🤔 열린 질문

자유에너지 원리의 한계를 탐색하다 보면 더 근본적인 질문들이 모습을 드러낸다.

**선호의 기원**: 선호 분포 $p(\tilde{o})$는 어디서 오는가? 진화인가, 발달인가, 학습인가? 이 질문에 답하지 않으면 FEP는 설명을 미루고 있을 뿐이다.

**마르코프 담요의 중첩**: 신경 집단·뇌·신체·사회적 개인은 각각 마르코프 담요를 형성하는가? 담요가 중첩될 때 어느 수준이 다른 수준을 지배하는가?

**현상성의 간극**: 예측 오차의 최소화가 왜 경험을 수반하는가? 이것은 순수한 어두운 정보처리 시스템과 의식 있는 시스템을 구별하는 무엇이 있는가? 이 질문은 다음 장으로 이어진다.

→ 다음 장: 예측처리가 설명하는 의식 내용 — FEP가 현상적 경험의 **내용**을 설명하는 데 어디까지 성공하는지를 검토한다.

---

> 🧩 **Principle** — 자유에너지 최소화는 지각·행위·학습을 통합하는 수학적 원리이며, 구현적 수준에서 예측 코딩으로 실현될 때 반증 가능하고 경험적으로 지지되는 이론이 된다.
>
> 🌉 **Boundary** — FEP의 과학적 한계는 계산적 수준에서의 동어반복 구조와 구현적 수준에서의 반증가능성 사이의 간극에 놓여 있다. 어두운 방 문제와 선호의 기원 문제는 이론의 내부에서 완전히 해소되지 않는다.
>
> 🪞 **Experience** — 이 원리를 이해한다는 것은 그것이 말하는 것과 말하지 않는 것 모두를 정직하게 대면하는 것이다. 과잉 주장이 아니라 정확한 주장만이 과학적 진전을 낳는다.

---

## 📝 연습문제

**기초.** **문제 1**: $\mathcal{F} \geq -\ln p(s)$가 항등식임을 KL 발산의 비음성으로부터 유도하라.

<details><summary>해설</summary>

$\mathcal{F} = D_{\mathrm{KL}}[q(\vartheta|\mu) \| p(\vartheta|s)] - \ln p(s)$이다. KL 발산은 언제나 $\geq 0$이므로, $\mathcal{F} \geq -\ln p(s)$가 성립한다. 이 부등식은 $q = p(\vartheta|s)$일 때 등호가 성립한다. 즉, 자유에너지는 정확한 사후 분포를 사용할 때 로그 증거와 같아진다. 이것은 수학적 항등식이며, 어떤 경험적 가정도 없다.

</details>

**문제 2**: 어두운 방 문제를 한 문단으로 서술하고, Friston의 응답이 어떤 가정을 추가하는지 명시하라.

<details><summary>해설</summary>

어두운 방 문제: FEP에 따르면 에이전트는 자유에너지를 최소화해야 한다. 놀라움이 없는 환경(어두운 방)에 머무르면 자유에너지가 최소화되지만, 생명체는 실제로 이렇게 행동하지 않는다. Friston의 응답은 기대 자유에너지 $\mathcal{G}$를 도입하여 탐색 행동을 에피스테믹 가치로 설명한다. 이 응답이 추가하는 가정: (1) 에이전트가 미래를 시뮬레이션하는 생성 모델을 가진다, (2) 에피스테믹 가치가 생성 모델에 내장된다. 이 가정들이 독립적으로 검증되어야 응답이 순환적이지 않다.

</details>

---

**심화.** **문제 3**: 마르코프 담요의 형식적 정의를 쓰고, 뇌와 신체의 경계가 이 정의를 충족하는지 논하라.

<details><summary>해설</summary>

마르코프 담요 $\mathcal{B}$는 내부 상태 $\mu$와 외부 상태 $\eta$를 조건부 독립으로 만드는 상태의 집합이다: $p(\mu, \eta | \mathcal{B}) = p(\mu|\mathcal{B})p(\eta|\mathcal{B})$. 뇌-신체 경계는 피부, 감각 수용체, 운동 출력으로 이루어진다. 이 경계가 마르코프 담요를 형성하는지는 논쟁 중이다. 정확히는, 뇌의 내부 상태가 신체적 담요 상태(감각 입력과 운동 출력)를 통해서만 환경과 상호작용한다는 가정이 필요하다. 이 가정은 생물학적으로 근사적으로 성립하지만, 신경-호르몬 상호작용이나 면역 시스템을 고려하면 경계가 흐려진다.

</details>

**문제 4**: 능동 추론과 강화학습을 비교하라. 기대 자유에너지 $\mathcal{G}$와 Q-함수가 어떤 관계에 있는지 분석하라.

<details><summary>해설</summary>

강화학습의 Q-함수 $Q(s, a)$는 상태-행동 쌍의 기대 누적 보상을 나타낸다. 능동 추론의 기대 자유에너지 $\mathcal{G}(\pi)$는 정책의 기대 자유에너지로, 에피스테믹 가치(불확실성 감소)와 프래그매틱 가치(선호 상태 달성)를 포함한다. 프래그매틱 가치가 보상에 해당하고, 에피스테믹 가치가 탐색 보너스(exploration bonus)에 해당한다. 따라서 $-\mathcal{G}(\pi) \approx Q(s, a) + \text{탐색 보너스}$의 구조를 가진다. 차이점: 강화학습은 보상 함수를 외부에서 주어지는 것으로 취급하지만, 능동 추론은 선호를 생성 모델 내부에 내장하려 한다.

</details>

---

**논문 비평.** **문제 5**: Colombo & Wright(2018) "Explanatory Pluralism in Computational Cognitive Science"를 읽고, 저자들의 핵심 비판이 FEP의 어느 수준을 겨냥하는지 분석하라. 저자들의 비판이 타당한 부분과 과도한 부분을 각각 구분하라.

<details><summary>해설</summary>

Colombo & Wright의 핵심 비판은 두 층위에서 작동한다. (1) 형이상학적 수준: FEP가 자기조직화의 정의로 사용된다면, 그것은 경험적 이론이 아니라 형이상학적 프레임워크다. 이 비판은 타당하다. FEP를 모든 자기조직화 시스템에 적용할 경우, 반증 가능성이 소진된다. (2) 구현적 수준에 대한 적용: 저자들이 구현적 예측 코딩까지 동어반복으로 기각하는 경우, 이것은 과도하다. 예측 오차 신호의 방향성, 정밀도 가중치의 효과 등은 명확히 반증 가능하다. 균형 잡힌 평가: FEP는 계산적 수준에서 철학적 프레임워크로, 구현적 수준에서 경험적 이론으로 이중 역할을 한다. 비판은 이 두 역할을 혼동할 때 과도해지고, 구별할 때 정확해진다.

</details>

---

<div align="center">

[◀ 이전: 능동 추론과 행위주체성](./03-agency.md) · [📚 README](../README.md) · [다음: 예측처리가 설명하는 의식 내용 ▶](../ch5-predictive-consciousness/01-predictive-content.md)

</div>

