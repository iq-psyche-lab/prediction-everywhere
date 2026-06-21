# 🧠 RPE에서 자유에너지로: 보상 예측이 놀라움 최소화의 특수 사례인 이유

*보상 예측 오차(RPE)는 자유에너지(놀라움) 최소화의 특수 사례이며, 보상을 선호 결과의 로그 확률로 해석하면 TD 학습이 변분 자유에너지의 경사하강으로 환원된다 — 이 다리는 Chapter 2(도파민)를 Chapter 4(자유에너지 원리)로 연결한다.*

## 🎯 횡단 질문

Friston의 자유에너지 원리(FEP)는 뇌의 모든 작동을 "놀라움(surprise, 또는 surprisal)의 최소화"로 기술한다. 강화학습의 TD 오차는 보상 예측 오차를 최소화한다. 이 두 이론은 근본적으로 다른 것인가, 아니면 하나가 다른 하나의 특수 사례인가?

이 질문에 답하려면 먼저 자유에너지와 놀라움의 관계를 명확히 해야 한다. 정보이론적으로, 놀라움(surprisal)은 $-\log P(o)$로 정의된다 — 관찰 $o$가 모델에 의해 얼마나 예상치 못한 것인가. 변분 자유에너지(variational free energy) $F$는 이 놀라움의 상한으로, 직접 계산할 수 없는 놀라움 대신 최소화할 수 있는 대리(proxy) 목표다.

보상의 관점에서: Friston et al.(2009)은 보상을 "선호 결과의 로그 확률"로 재해석한다. 즉, $r(s) = \log P(s | \text{선호})$. 이 재해석을 받아들이면 TD 오차 $\delta = r + \gamma V(s') - V(s)$는 자유에너지 경사하강의 한 단계가 된다. RPE는 미래 놀라움을 줄이기 위해 현재 믿음을 수정하는 과정의 신경적 구현이다.

## 🌐 횡단 입력

- **information-prediction (L0)**: 변분 자유에너지 $F = D_{KL}[Q(\theta) \| P(\theta|o)] - \log P(o)$는 모델 복잡도와 예측 정확도의 트레이드오프를 명시화하며, 놀라움의 최소화와 정보 획득을 통합한다.
- **neuromodulation-arousal (L1)**: 자유에너지 관점에서 도파민은 예상 자유에너지(expected free energy)의 경사를 인코딩하며, 탐색(미래 놀라움 감소)과 착취(현재 보상 최대화)를 단일 프레임워크 안에서 균형 잡는다.
- **neurons-neural-codes (L1)**: 예측 코딩(predictive coding) 회로에서 오차 뉴런(error units)은 RPE와 일반 예측 오차를 모두 인코딩한다; 계층적 피질 조직이 변분 추론의 신경 구현이다.
- **learning-decision (L2)**: 능동 추론(active inference, Friston et al.)은 인식(perception)과 행동을 동일한 자유에너지 최소화로 통합한다; 행동은 예측을 세계에 강요하는 방식(proprioceptive prediction fulfillment)으로 이해된다.
- **IQ AI Lab RL/FEP 직결**: 딥마인드와 여러 그룹이 FEP 기반 에이전트를 구현 시도했다; 탐색-착취 딜레마를 "예상 자유에너지 최소화"로 해결하는 알고리즘이 최대 엔트로피 RL과 연결된다.

## 🔍 표면의 다양성

강화학습과 자유에너지 원리는 서로 다른 언어를 사용한다. RL은 보상, 가치 함수, 벨만 방정식, 정책을 말한다. FEP는 놀라움, 변분 자유에너지, 사후 확률, 믿음 갱신을 말한다. RL의 에이전트는 보상을 최대화하고, FEP의 에이전트는 자유에너지를 최소화한다 — 이 두 목표가 어떻게 동치일 수 있는가?

표면적 차이는 더 깊다. RL은 환경을 외부에서 주어진 것으로 다루고, 에이전트는 최적 행동을 학습한다. FEP는 에이전트가 생성 모델(generative model)을 가지며, 이 모델이 세계와 에이전트 자신을 시뮬레이션한다고 가정한다. RL에서 보상은 스칼라 신호로 주어지지만, FEP에서 "보상"은 모델에 의해 정의된 선호(prior preference)다.

이 차이들이 근본적인가, 아니면 수학적 변환으로 극복될 수 있는가? 이것이 이 문서에서 해결하려는 핵심 긴장이다.

## ⚙️ 깊은 동형성

### 분석 1: 놀라움과 보상의 동치

정보이론에서 놀라움(surprisal): $\mathcal{S}(o) = -\log P(o)$

Friston(2010)의 핵심 제안: 생물학적 에이전트는 놀라움을 최소화함으로써 생존한다 — 예상치 못한 상태에 있는 것은 위험하므로, 생존 가능한 상태에 머무르려면 자신의 상태가 선호 상태(prior preference)와 일치해야 한다:

$$P(s | \text{선호}) \propto e^{r(s)}$$

따라서 보상 $r(s) = \log P(s | \text{선호})$. 이를 대입하면 보상은 선호 상태에 있을 로그 확률이 된다. 놀라움 최소화 = 선호 상태의 확률 최대화 = 보상 최대화. $\square$

### 분석 2: TD 오차와 변분 자유에너지

변분 자유에너지:
$$F = \underbrace{D_{KL}[Q(\theta) \| P(\theta)]}_{\text{복잡도}} - \underbrace{\mathbb{E}_Q[\log P(o|\theta)]}_{\text{정확도}}$$

이를 시간 차분으로 전개하면 TD 오차와의 연결이 드러난다. 상태 $s$에서의 가치 함수를 자유에너지의 음의 기대값으로 정의하면:

$$V(s) = -\mathbb{E}\left[\sum_{t=0}^{\infty} \gamma^t \mathcal{S}(o_t) \bigg| s_0 = s\right] = \mathbb{E}\left[\sum_{t=0}^{\infty} \gamma^t \log P(o_t|\text{선호}) \bigg| s_0 = s\right]$$

그러면 벨만 방정식 $V(s) = r(s) + \gamma V(s')$가 자유에너지 최소화의 귀납적 형태가 되며, TD 오차 $\delta = r + \gamma V(s') - V(s)$는 자유에너지 경사의 단일 시간 단계 근사다. $\square$

### 분석 3: 예상 자유에너지와 탐색-착취

능동 추론에서, 에이전트는 현재 자유에너지뿐 아니라 미래 예상 자유에너지(expected free energy, EFE) $\mathcal{G}$를 최소화한다:

$$\mathcal{G}(\pi) = \underbrace{-\mathbb{E}_{Q(o|\pi)}[\log P(o|\text{선호})]}_{\text{착취: 선호 결과 달성}} + \underbrace{D_{KL}[Q(\theta|\pi) \| Q(\theta)]}_{\text{탐색: 믿음 갱신}}$$

첫 번째 항은 보상 최대화(착취), 두 번째 항은 불확실성 감소(탐색)다. 이 단일 목표가 탐색-착취 트레이드오프를 내생적으로 해결한다:

$$\mathcal{G}(\pi) = -\text{보상} + \text{불확실성}$$

표준 RL에서 탐색은 외부에서 부과되는 별도 메커니즘($\epsilon$-탐욕, UCB 등)이지만, FEP에서는 단일 최적화 목표의 내재적 구성 요소다. $\square$

### 분석 4: 계층적 통합과 정밀 가중치

자유에너지 원리에서 예측 오차의 영향력은 정밀도(precision, 역분산 $\Pi = 1/\sigma^2$)에 의해 가중된다:

$$\delta_{\text{정밀 가중}} = \Pi \cdot \delta_{\text{raw}}$$

이 정밀도가 주의(attention), 각성(arousal), 도파민과 연결된다: Friston et al.(2012)은 도파민 신호가 정밀도 가중치를 인코딩한다고 제안한다. 높은 도파민 = 높은 정밀도 = 예측 오차에 더 강하게 반응 = 더 많이 학습.

$$\text{DA}_{\text{tonic}} \propto \Pi \quad \Rightarrow \quad \alpha_{\text{effective}} = \Pi \cdot \alpha_{\text{기본}}$$

이 해석에서 도파민은 "오차 신호" 자체가 아니라 "오차 신호에 얼마나 주목할 것인가"를 조절한다. 이는 03-beyond-rpe.md의 wanting/salience 역할과 자유에너지 프레임에서 통합된다. $\square$

## 🧪 수렴 증거

### 실험 1: RPE와 자유에너지 최소화의 수학적 동치 시뮬레이션

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.special import softmax

np.random.seed(42)

# ─── 보상 = log P(선호 결과) 해석 ─────────────────────────────
def reward_as_log_prior(states, preferred_state, temperature=1.0):
    """
    보상 = 선호 상태의 로그 사전 확률
    P(s|선호) ∝ exp(reward(s))
    """
    n_states = len(states)
    # 선호 상태에 가까울수록 높은 보상
    rewards = np.array([-abs(s - preferred_state) / temperature for s in states])
    # 로그 확률로 정규화
    log_prior = rewards - np.log(np.sum(np.exp(rewards)))
    return log_prior

# ─── 자유에너지 최소화 = TD 학습 등치 시연 ──────────────────────
class FEPAgent:
    """
    자유에너지 관점의 에이전트.
    보상 = log P(선호), 값함수 = 기대 누적 놀라움의 음수
    """
    def __init__(self, n_states, preferred_state, alpha=0.1, gamma=0.9):
        self.V = np.zeros(n_states)
        self.preferred_state = preferred_state
        self.alpha = alpha
        self.gamma = gamma
        # 보상 = 선호 상태의 로그 사전 확률
        states = list(range(n_states))
        log_priors = reward_as_log_prior(states, preferred_state)
        self.reward_fn = log_priors  # r(s) = log P(s|선호)
    
    def compute_surprise(self, state):
        """놀라움 = -log P(관찰 | 선호)"""
        return -self.reward_fn[state]
    
    def td_update(self, s, s_next, done=False):
        r = self.reward_fn[s]  # 보상 = 로그 사전 확률
        v_next = 0 if done else self.V[s_next]
        # TD 오차 = 자유에너지 경사의 근사
        delta = r + self.gamma * v_next - self.V[s]
        self.V[s] += self.alpha * delta
        return delta, self.compute_surprise(s)

class StandardRLAgent:
    """표준 RL 에이전트: 외부 보상 최대화"""
    def __init__(self, n_states, preferred_state, alpha=0.1, gamma=0.9):
        self.V = np.zeros(n_states)
        self.alpha = alpha
        self.gamma = gamma
        # 표준 보상: 선호 상태 = 1, 나머지 = 0
        self.reward_fn = np.zeros(n_states)
        self.reward_fn[preferred_state] = 1.0
    
    def td_update(self, s, s_next, done=False):
        r = self.reward_fn[s]
        v_next = 0 if done else self.V[s_next]
        delta = r + self.gamma * v_next - self.V[s]
        self.V[s] += self.alpha * delta
        return delta

# 시뮬레이션
n_states = 10
preferred = 7
n_episodes = 300

fep_agent = FEPAgent(n_states, preferred)
rl_agent = StandardRLAgent(n_states, preferred)

def random_walk_episode(agent, n_states, preferred, is_fep=True):
    state = np.random.randint(n_states)
    total_delta = 0
    for _ in range(20):
        next_state = min(max(state + np.random.choice([-1, 0, 1]), 0), n_states - 1)
        done = (next_state == preferred)
        if is_fep:
            delta, surprise = agent.td_update(state, next_state, done)
        else:
            delta = agent.td_update(state, next_state, done)
            surprise = None
        total_delta += abs(delta)
        state = next_state
        if done:
            break
    return total_delta / 20

fep_deltas = [random_walk_episode(fep_agent, n_states, preferred, is_fep=True) 
              for _ in range(n_episodes)]
rl_deltas = [random_walk_episode(rl_agent, n_states, preferred, is_fep=False) 
             for _ in range(n_episodes)]

print("=== RPE vs 자유에너지 최소화 비교 ===")
print(f"FEP 에이전트 보상 함수: {fep_agent.reward_fn.round(3)}")
print(f"표준 RL 보상 함수:      {rl_agent.reward_fn}")
print(f"\n수렴 후 가치 함수 (마지막 50 에피소드 평균 |δ|):")
print(f"  FEP:     {np.mean(fep_deltas[-50:]):.4f}")
print(f"  표준 RL: {np.mean(rl_deltas[-50:]):.4f}")
print(f"\n선호 상태({preferred})의 가치:")
print(f"  FEP V({preferred}):     {fep_agent.V[preferred]:.4f}")
print(f"  RL  V({preferred}):     {rl_agent.V[preferred]:.4f}")

# 자유에너지와 TD 동치 확인
print("\n=== 수학적 동치 확인 ===")
print(f"FEP: r(s) = log P(s|선호) = {fep_agent.reward_fn[preferred]:.4f} (선호 상태)")
print(f"FEP: -r(s) = 놀라움 = {-fep_agent.reward_fn[preferred]:.4f}")
print(f"TD 업데이트: δ = r + γV(s') - V(s) — 동일한 오차 신호")
print("→ FEP의 '자유에너지 최소화'와 RL의 'TD 학습'은 동일한 업데이트 규칙")

fig, axes = plt.subplots(1, 2, figsize=(12, 4))
window = 20
fep_smooth = np.convolve(fep_deltas, np.ones(window)/window, mode='valid')
rl_smooth = np.convolve(rl_deltas, np.ones(window)/window, mode='valid')

axes[0].plot(fep_smooth, label='FEP (log-prior 보상)', color='purple')
axes[0].plot(rl_smooth, label='표준 RL', color='steelblue', linestyle='--')
axes[0].set_title('|δ| 수렴 비교')
axes[0].set_xlabel('에피소드'); axes[0].set_ylabel('평균 |δ|')
axes[0].legend()

states = list(range(n_states))
axes[1].bar(states, fep_agent.V, alpha=0.7, label='FEP 가치', color='purple')
axes[1].bar(states, rl_agent.V, alpha=0.5, label='표준 RL 가치', color='steelblue')
axes[1].axvline(preferred, color='red', linestyle=':', label=f'선호 상태={preferred}')
axes[1].set_title('수렴된 가치 함수')
axes[1].set_xlabel('상태'); axes[1].set_ylabel('V(s)')
axes[1].legend()

plt.tight_layout()
plt.savefig('rpe_to_free_energy.png', dpi=150, bbox_inches='tight')
print("그래프 저장: rpe_to_free_energy.png")
```

### 실험 2: 예상 자유에너지의 탐색-착취 분해

```python
import numpy as np

def expected_free_energy(Q_states, P_preferred, Q_theta, uncertainty):
    """
    예상 자유에너지 G(π) = -보상항 + 탐색항
    - 보상항: E_Q[log P(o|선호)] = 기대 보상
    - 탐색항: KL[Q(θ|π) || Q(θ)] = 믿음 갱신 (정보 이득)
    """
    # 보상항 (착취): 선호 결과 달성
    reward_term = np.sum(Q_states * np.log(P_preferred + 1e-10))
    
    # 탐색항 (탐색): KL 발산 = 불확실성 감소 기대량
    exploration_term = np.sum(Q_theta * np.log((Q_theta + 1e-10) / (uncertainty + 1e-10)))
    
    EFE = -reward_term + exploration_term
    return EFE, reward_term, exploration_term

# 세 가지 정책 시나리오
n_states = 4
scenarios = {
    "고착취-저탐색": {
        "Q_states": np.array([0.05, 0.1, 0.15, 0.7]),  # 선호 상태 확실
        "Q_theta": np.array([0.9, 0.05, 0.03, 0.02]),  # 믿음 확실
        "uncertainty": np.array([0.25, 0.25, 0.25, 0.25]),
    },
    "저착취-고탐색": {
        "Q_states": np.array([0.25, 0.25, 0.25, 0.25]),  # 상태 불확실
        "Q_theta": np.array([0.25, 0.25, 0.25, 0.25]),   # 믿음 불확실
        "uncertainty": np.array([0.25, 0.25, 0.25, 0.25]),
    },
    "균형": {
        "Q_states": np.array([0.1, 0.2, 0.3, 0.4]),
        "Q_theta": np.array([0.4, 0.3, 0.2, 0.1]),
        "uncertainty": np.array([0.25, 0.25, 0.25, 0.25]),
    }
}

P_preferred = np.array([0.05, 0.1, 0.15, 0.7])  # 선호: 상태 3

print("=== 예상 자유에너지 분해 ===")
print(f"{'시나리오':<20} {'EFE':>8} {'보상항':>8} {'탐색항':>8}")
print("-" * 48)
for name, params in scenarios.items():
    EFE, reward, explore = expected_free_energy(
        params["Q_states"], P_preferred, params["Q_theta"], params["uncertainty"]
    )
    print(f"{name:<20} {EFE:>8.3f} {-reward:>8.3f} {explore:>8.3f}")

print("\n→ EFE가 가장 낮은 정책이 선택됨")
print("→ 탐색항이 RL의 외부 bonus 없이 내재적으로 탐색을 유도")
```

**반례와 경계**: FEP-RL 동치의 핵심 가정은 보상이 "선호의 로그 확률"로 해석될 수 있다는 것이다. 그러나 생물학적 보상(음식, 물, 성적 자극)이 항상 이 형식으로 표현될 수 있는지는 논란이다. 또한 FEP는 에이전트가 생성 모델을 가진다고 가정하지만, 표준 model-free RL은 명시적 모델 없이 작동한다. 이 가정의 차이가 수학적 동치를 제한한다.

## 🌉 간극의 위치

- ✅ **수학적 동치의 핵심**: 보상 = log P(선호)로 재해석하면 TD 벨만 방정식이 자유에너지 최소화의 특수 사례가 된다; 이 동치는 분석적으로 증명 가능하다.
- ✅ **탐색의 내생화**: 예상 자유에너지(EFE)는 탐색-착취 트레이드오프를 외부 heuristic 없이 단일 목표로 통합한다.
- ✅ **정밀도-도파민 대응**: 도파민을 정밀도 가중치로 해석하면 RPE(위상성), wanting(유인 현저성), vigor(긴장성)가 단일 프레임워크 안에 통합된다.
- ❌ **생성 모델의 신경 기반**: FEP는 뇌가 명시적 생성 모델을 가진다고 가정하지만, 이 모델의 해부학적 기반이 충분히 특정되지 않았다.
- ❌ **반증 가능성**: FEP는 원칙적으로 어떤 적응적 행동도 설명할 수 있어 반증하기 어렵다는 비판이 있다(Colombo & Series, 2012).
- ❌ **보상 = log-prior의 제한**: 외생적 보상(먹이, 전기자극)이 항상 선호의 로그 확률로 해석될 수 있는지 불분명하다.
- ❌ **현상학의 간극**: 자유에너지 최소화가 놀라움의 최소화라 해도, "놀라움이 느껴진다"는 사실은 $F = D_{KL} - \log P(o)$로 환원되지 않는다. 수식은 구조를 설명하지만 질을 설명하지 않는다.

## 🧬 원리의 회수

RPE에서 자유에너지로의 이행은 "예측 원리"가 단순한 오차 최소화를 넘어 훨씬 더 넓은 인식론적 원리임을 보인다. 도파민 RPE는 국소적 오차 신호이고, 계층적 RPE는 다층 추론이며, FEP는 이 모두를 하나의 변분 추론 프레임워크 안에 통합한다.

이 통합의 핵심 기여는 세 가지다. 첫째, 보상을 선호의 로그 확률로 재해석함으로써 "보상 최대화"와 "놀라움 최소화"가 동일한 계산 목표임을 보인다. 둘째, 탐색이 더 이상 외부에서 부과된 heuristic이 아니라 자유에너지 목표의 내재적 구성 요소임을 밝힌다. 셋째, 도파민을 정밀도 신호로 해석함으로써 Chapter 2 전체에서 논의한 도파민의 다중 역할 — RPE, wanting, vigor, uncertainty — 을 단일 원리 아래 통합한다.

그러나 이 통합은 완성이 아니라 다음 장으로의 다리다. 자유에너지 원리는 지각, 기억, 언어까지 확장된다 — 같은 변분 추론이 피질의 모든 수준에서 작동한다는 주장. Chapter 3과 4에서 이 확장을 검토한다.

## 🪞 1인칭

지금 이 문서를 읽으면서 당신은 예상치 못한 문장을 만날 때마다 작은 불일치를 경험한다. 그 불일치가 주의를 잡아당기고, 재읽기를 유도하며, 이해가 되면 작은 만족감을 준다. 자유에너지 원리의 언어로: 텍스트의 의미에 대한 예측이 실패하면 놀라움이 증가하고, 뇌는 이 놀라움을 줄이기 위해 믿음을 갱신한다. 만족감은 자유에너지가 감소했다는 신호다.

그런데 이 설명은 뭔가 빠뜨린다. 이해의 만족감이 단순히 $F$가 감소했다는 사실로 환원되지 않는다. "아, 그렇구나!"의 느낌 — 통찰의 현상학 — 은 변분 추론의 수렴으로는 포착되지 않는다. 자유에너지 원리는 이 느낌이 언제, 왜 발생하는지의 구조를 설명하지만, 느낌 자체가 무엇인지를 설명하지 않는다. 이것이 "Explain it, don't explain it away"라는 이 레포의 핵심 긴장이다. 수식이 아무리 정확해도, 놀라움이 느껴진다는 사실 그 자체는 수식 바깥에 있다.

## 📐 예측·반증

**예측 1**: 최대 엔트로피 강화학습(MaxEnt RL)은 정책을 $\pi(a|s) \propto \exp(Q(s,a)/\alpha)$로 표현하며, 이는 FEP의 예상 자유에너지 최소화와 수학적으로 동치다. 따라서 MaxEnt RL 에이전트의 탐색 패턴은 능동 추론 에이전트와 동일해야 한다.
- 반증 조건: 동일한 환경에서 두 에이전트의 탐색 전략이 체계적으로 다르면 동치 주장이 깨진다.

**예측 2**: 도파민을 정밀도 신호로 해석하면, 도파민 수준이 높을 때 예측 오차에 대한 반응성이 증가하고, 낮을 때 감소해야 한다. 약리학적으로 도파민을 증가시키면 가치 학습의 학습률이 높아진다.
- 반증 조건: 도파민 증가가 학습률과 상관없거나 반대 방향으로 움직이면, 정밀도-도파민 가설이 기각된다.

**예측 3**: FEP 기반 에이전트는 표준 RL 에이전트보다 새로운 환경(distribution shift)에서 적응이 빠르다 — 내재적 탐색(epistemic value)이 믿음 갱신을 가속하기 때문이다.
- 반증 조건: 동일한 계산 예산에서 FEP 에이전트가 표준 RL 에이전트보다 새 환경 적응이 빠르지 않으면, 내재적 탐색의 실용적 이점이 없다.

## 🤔 열린 질문

자유에너지 원리가 보상 예측의 일반화라면, 지각은 어떻게 같은 원리로 설명되는가? 외부 세계를 "보는" 것도 놀라움을 최소화하는 과정인가, 그리고 착각(illusion)과 환각(hallucination)은 자유에너지 최소화의 실패인가 성공인가? 지각이 예측 검증이라는 주장 → 다음 문서(ch3-perception-language-memory/01-perception-as-prediction.md)에서 탐구한다.

---

> 🧩 **Principle** — 보상을 선호 결과의 로그 확률 $r(s) = \log P(s|\text{선호})$로 해석하면, TD 학습($\delta = r + \gamma V(s') - V(s)$)은 변분 자유에너지 최소화의 특수 사례가 되어 RPE와 FEP를 단일 프레임워크 안에 통합한다.

> 🌉 **Boundary** — 이 동치는 보상이 선호의 로그 확률로 표현될 수 있고 에이전트가 생성 모델을 가진다는 가정에 의존한다; 외생적 보상과 model-free RL에서 이 가정은 약화된다.

> 🪞 **Experience** — "아, 그렇구나!"의 이해 만족감은 자유에너지 감소의 신호로 추적되지만, 통찰 자체의 느낌 — 개념이 맞아떨어지는 그 순간의 질감 — 은 $F$의 수렴으로 소진되지 않는다.

## 📝 연습문제

**기초.** "보상 = 선호 결과의 로그 확률"이라는 FEP의 보상 재해석을 수식으로 표현하고, 이것이 TD 벨만 방정식과 어떻게 연결되는지 세 단계로 설명하라.

<details><summary>해설</summary>

1단계 — 보상 재정의: $P(s|\text{선호}) \propto e^{r(s)}$이므로 $r(s) = \log P(s|\text{선호}) + \text{상수}$. 상수를 0으로 정규화하면 $r(s) = \log P(s|\text{선호})$.

2단계 — 놀라움과의 연결: 놀라움 $\mathcal{S}(s) = -\log P(s|\text{선호}) = -r(s)$. 따라서 보상 최대화 = 놀라움 최소화.

3단계 — 벨만 방정식으로: 가치 함수 $V(s) = \mathbb{E}[\sum_t \gamma^t r(s_t) | s_0 = s] = -\mathbb{E}[\sum_t \gamma^t \mathcal{S}(s_t) | s_0 = s]$ (기대 누적 놀라움의 음수). 이를 귀납적으로 쓰면 $V(s) = r(s) + \gamma V(s')$, 즉 표준 벨만 방정식. TD 오차 $\delta = r + \gamma V(s') - V(s)$는 이 방정식의 불일치(residual)다.

</details>

**심화.** 예상 자유에너지(EFE) $\mathcal{G}(\pi) = -\text{보상항} + \text{탐색항}$에서 두 항을 수식으로 쓰고, 이것이 표준 RL의 탐색-착취 딜레마와 어떻게 다른지 설명하라. 특히 $\epsilon$-탐욕 전략과 비교하라.

<details><summary>해설</summary>

EFE 수식:
$$\mathcal{G}(\pi) = \underbrace{-\mathbb{E}_{Q(o|\pi)}[\log P(o|\text{선호})]}_{\text{착취}} + \underbrace{D_{KL}[Q(\theta|\pi) \| Q(\theta)]}_{\text{탐색(정보 이득)}}$$

보상항: 정책 $\pi$ 하에서 기대되는 관찰의 선호도. 탐색항: 정책이 믿음을 얼마나 갱신하는가(KL 발산).

표준 $\epsilon$-탐욕과의 차이: (1) $\epsilon$-탐욕은 탐색 확률이 시간에 따라 외부적으로 감소($\epsilon$ 스케줄); EFE는 믿음이 충분히 수렴하면 탐색항이 자동으로 감소. (2) $\epsilon$-탐욕은 무작위 탐색; EFE는 정보 이득이 가장 큰 행동을 선택(epistemic foraging). (3) $\epsilon$-탐욕은 탐색과 착취를 확률적으로 분리; EFE는 매 의사결정에서 두 항을 통합 최적화. 중요한 차이: EFE의 탐색은 불확실성 감소에 목적이 있어 "지능적 탐색"인 반면, $\epsilon$-탐욕은 무작위 탐색이다.

</details>

**논문 비평.** Friston et al. (2009) "Reinforcement learning or active inference?" (PLOS ONE)은 TD 학습이 자유에너지 최소화의 특수 사례라고 주장한다. 이 주장에 대한 가장 강력한 반론 두 가지를 제시하고, 각각이 얼마나 치명적인지 평가하라.

<details><summary>해설</summary>

반론 1 (반증 불가능성): FEP는 어떤 행동도 "자유에너지 최소화로 볼 수 있다"는 사후적 해석이 가능하여 반증이 어렵다(Colombo & Series, 2012). 치명성 평가: 상당히 타당. FEP를 falsifiable prediction으로 만들려면 "이 조건에서 FEP 에이전트는 RL 에이전트와 다른 행동을 해야 한다"는 구체적 예측이 필요하다. Friston et al.의 논문은 이런 구별 예측이 충분히 명시되지 않았다. 그러나 능동 추론의 구체적 구현에서 반증 가능한 예측이 가능하므로, 일반 이론의 반증 어려움이 전체를 무효화하지는 않는다.

반론 2 (생성 모델 가정의 비현실성): FEP는 에이전트가 환경의 완전한 생성 모델을 가진다고 가정하지만, 실제 뇌(또는 RL 에이전트)는 부분적이고 근사적인 모델만 가진다. Model-free RL은 명시적 모델 없이 작동하므로 동치 주장이 약화된다. 치명성 평가: 실용적으로 중요하다. FEP-RL 동치는 완전한 생성 모델을 가정할 때 성립하지만, 근사 모델에서는 수학적 동치가 보장되지 않는다. 그러나 근사 FEP(amortized variational inference)가 model-free RL과 연결될 수 있어, 이 반론도 완전히 치명적이지는 않다.

</details>

---

<div align="center">

[◀ 이전: 도파민이 예측 이외에 신호하는 것](./03-beyond-rpe.md) · [📚 README](../README.md) · [다음: 지각 = 예측 검증 ▶](../ch3-perception-language-memory/01-perception-as-prediction.md)

</div>
