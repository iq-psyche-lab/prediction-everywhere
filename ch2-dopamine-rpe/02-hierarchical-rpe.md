# 🧠 RPE의 계층적 구조: 습관에서 목표지향까지

*단순 model-free RPE는 선조체의 배측-복측 축을 따라 계층화되며, 전전두피질의 model-based 예측이 하위 RPE 신호를 조절함으로써 습관과 목표지향 행동의 이중 체계를 구성한다.*

## 🎯 횡단 질문

뇌는 단일한 RPE 계산기를 가지고 있는가, 아니면 복수의 RPE 시스템이 계층적으로 조직되어 있는가? 이 질문은 임상적으로도 중요하다: 강박장애(OCD)와 약물 중독에서 습관이 목표지향 행동을 압도하는 현상은, 단일 RPE 시스템으로는 설명되지 않는다. 두 개 이상의 학습 시스템이 존재하고 그 균형이 깨진다는 가정이 필요하다.

계층적 RPE의 핵심 질문은 이것이다: 상위 예측(전전두피질의 모델 기반 계획)은 어떻게 하위 RPE(선조체의 model-free 학습)를 수정하는가? Daw et al.(2005)의 이중 시스템 모델에서 시작하여, 최근의 신경 회로 연구까지 이 계층 구조를 해부한다.

RPE의 계층화는 단순한 신경해부학적 사실이 아니다. 이는 인지 유연성과 자동성 사이의 근본적 트레이드오프를 반영한다: model-based 시스템은 정확하지만 계산 비용이 크고, model-free 시스템은 빠르지만 경직되어 있다. 뇌가 이 두 시스템을 어떻게 중재하는가가 이 문서의 핵심이다.

## 🌐 횡단 입력

- **information-prediction (L0)**: 계층적 예측은 정보이론적으로 효율적이다 — 상위 수준이 하위 수준의 예측 오차만 전달받으면 전체 정보 전달량이 감소한다(predictive coding의 원리).
- **neuromodulation-arousal (L1)**: 도파민은 복측 선조체(nucleus accumbens)와 배측 선조체(caudate/putamen)에 차별적으로 투사되며, 각각 목표지향과 습관적 행동 학습에 다른 역할을 한다.
- **neurons-neural-codes (L1)**: 배측 선조체의 직접 경로(direct pathway)와 간접 경로(indirect pathway)가 행동 선택과 억제를 조절한다; D1/D2 수용체의 차별적 발현이 계층 구조의 세포 기반이다.
- **learning-decision (L2)**: Daw et al.(2005)의 계산 모델은 model-based(배측 전전두피질)와 model-free(복측 선조체) 시스템의 불확실성 기반 중재를 수식화했다.
- **IQ AI Lab RL 직결**: Dyna 아키텍처(Sutton, 1991)는 model-based와 model-free RL의 통합을 구현하며, 뇌의 이중 시스템 모델과 직접 대응된다; AlphaZero의 MCTS와 가치 네트워크의 조합도 이 계층의 AI 버전이다.

## 🔍 표면의 다양성

습관(habit)과 목표지향(goal-directed) 행동은 현상학적으로 다르다. 습관은 자동적이고, 결과에 민감하지 않으며, 소거에 저항한다. 목표지향 행동은 계획적이고, 결과 가치에 민감하며, 환경 변화에 유연하게 반응한다. 쥐 실험에서 두 행동 유형을 구분하는 표준 방법은 결과 평가절하(outcome devaluation)다: 보상의 가치를 떨어뜨렸을 때 여전히 이전 행동을 하면 습관, 즉시 행동을 바꾸면 목표지향이다.

신경해부학적으로, 이 구분은 선조체의 공간적 조직과 대응된다. 배내측 선조체(dorsomedial striatum, DMS)는 목표지향 행동과 연관되고, 배외측 선조체(dorsolateral striatum, DLS)는 습관과 연관된다. 전전두피질, 특히 안와전두피질(OFC)과 전측 대상피질(ACC)은 model-based 예측에 기여한다.

표면의 다양성은 학습 속도에서도 나타난다: 습관은 많은 시행이 필요하지만 실행이 빠르고, 목표지향 계획은 적은 경험으로 작동하지만 계산이 느리다. 이 트레이드오프는 의사결정의 생태학적 합리성(ecological rationality)과 연결된다.

## ⚙️ 깊은 동형성

### 분석 1: Model-Free RPE의 수식화

기본 TD(0) 업데이트는 model-free RPE를 구현한다:

$$\delta^{MF} = r_t + \gamma V^{MF}(s_{t+1}) - V^{MF}(s_t)$$

여기서 $V^{MF}$는 과거 경험의 누적으로만 구성된다 — 환경의 내부 모델 없이. 이 시스템은 계산이 빠르지만, 환경 구조가 변할 때 적응이 느리다. 복측 선조체의 도파민 신호가 이 오차를 인코딩한다. $\square$

### 분석 2: Model-Based 예측과 RPE

Model-based 시스템은 전이 모델 $P(s'|s, a)$와 보상 모델 $R(s, a)$를 사용하여 가치를 추정한다:

$$V^{MB}(s) = \max_a \sum_{s'} P(s'|s, a)[R(s, a) + \gamma V^{MB}(s')]$$

이 시스템의 RPE는:

$$\delta^{MB} = r_t + \gamma V^{MB}(s_{t+1}) - V^{MB}(s_t)$$

$\delta^{MF}$와 수식은 같지만, $V^{MB}$가 실시간 계획(planning)을 통해 계산된다는 점이 다르다. 전전두피질이 이 계획을 실행하고, 그 결과가 선조체의 RPE 신호를 조절한다. $\square$

### 분석 3: 이중 시스템의 중재

Daw et al.(2005)의 모델: 두 시스템의 불확실성을 비교하여 행동을 선택한다:

$$a^* = \text{argmax}_a \left[ \omega \cdot Q^{MB}(s, a) + (1-\omega) \cdot Q^{MF}(s, a) \right]$$

여기서 $\omega \in [0, 1]$는 model-based 시스템의 신뢰도를 반영하는 중재 가중치다:

$$\omega = \frac{\text{Var}(Q^{MF})}{\text{Var}(Q^{MF}) + \text{Var}(Q^{MB})}$$

불확실성이 낮을 때 model-free가 우세하고(습관), 새로운 환경에서는 model-based가 우세하다(목표지향). 이 중재가 전전두피질-선조체 회로의 상호작용으로 구현된다. $\square$

### 분석 4: 위계적 RPE와 서브목표

계층적 강화학습(hierarchical RL)에서, 상위 정책(manager)이 하위 정책(worker)에게 서브목표를 설정한다. 각 수준에서 독립적인 RPE가 계산된다:

$$\delta^{\text{high}} = R^{\text{ext}}_t + \gamma V^{\text{high}}(s_{t+n}) - V^{\text{high}}(s_t)$$
$$\delta^{\text{low}} = R^{\text{int}}_t + \gamma V^{\text{low}}(s_{t+1}) - V^{\text{low}}(s_t)$$

여기서 $R^{\text{int}}$는 상위 수준이 설정한 서브목표 달성에 대한 내부 보상이다. 신경 기반으로는, 전전두피질-해마 회로가 상위 예측을 생성하고, 선조체가 하위 RPE를 구현하는 구조가 제안된다(Botvinick et al., 2009). $\square$

## 🧪 수렴 증거

### 실험 1: 이중 시스템 모델 시뮬레이션

```python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)

class ModelFreeAgent:
    """TD(0) model-free 에이전트"""
    def __init__(self, n_states, n_actions, alpha=0.1, gamma=0.9, epsilon=0.1):
        self.Q = np.zeros((n_states, n_actions))
        self.alpha = alpha
        self.gamma = gamma
        self.epsilon = epsilon
    
    def act(self, state):
        if np.random.random() < self.epsilon:
            return np.random.randint(self.Q.shape[1])
        return np.argmax(self.Q[state])
    
    def update(self, s, a, r, s_next, done):
        td_target = r + (0 if done else self.gamma * np.max(self.Q[s_next]))
        delta = td_target - self.Q[s, a]
        self.Q[s, a] += self.alpha * delta
        return delta

class ModelBasedAgent:
    """
    Dyna-Q: model-based RL
    실제 경험 + 내부 모델 플래닝
    """
    def __init__(self, n_states, n_actions, alpha=0.1, gamma=0.9, 
                 epsilon=0.1, n_planning=10):
        self.Q = np.zeros((n_states, n_actions))
        self.model = {}  # (s, a) → (r, s')
        self.alpha = alpha
        self.gamma = gamma
        self.epsilon = epsilon
        self.n_planning = n_planning
        self.experience = []
    
    def act(self, state):
        if np.random.random() < self.epsilon:
            return np.random.randint(self.Q.shape[1])
        return np.argmax(self.Q[state])
    
    def update(self, s, a, r, s_next, done):
        # 실제 경험으로 업데이트
        td_target = r + (0 if done else self.gamma * np.max(self.Q[s_next]))
        delta = td_target - self.Q[s, a]
        self.Q[s, a] += self.alpha * delta
        
        # 내부 모델 업데이트
        self.model[(s, a)] = (r, s_next, done)
        self.experience.append((s, a))
        
        # 플래닝: 내부 모델로 추가 업데이트
        for _ in range(self.n_planning):
            if not self.experience:
                break
            idx = np.random.randint(len(self.experience))
            ps, pa = self.experience[idx]
            pr, ps_next, pdone = self.model[(ps, pa)]
            pt = pr + (0 if pdone else self.gamma * np.max(self.Q[ps_next]))
            self.Q[ps, pa] += self.alpha * (pt - self.Q[ps, pa])
        
        return delta

# 단순 그리드 월드 (4x4, 목표=상태 15)
def make_gridworld(size=4):
    n_states = size * size
    n_actions = 4  # 상하좌우
    
    def step(state, action, goal=n_states-1):
        row, col = state // size, state % size
        if action == 0 and row > 0: row -= 1      # 위
        elif action == 1 and row < size-1: row += 1  # 아래
        elif action == 2 and col > 0: col -= 1    # 왼쪽
        elif action == 3 and col < size-1: col += 1  # 오른쪽
        next_state = row * size + col
        reward = 1.0 if next_state == goal else -0.01
        done = next_state == goal
        return next_state, reward, done
    
    return n_states, n_actions, step

n_states, n_actions, step_fn = make_gridworld(4)
n_episodes = 100

mf_agent = ModelFreeAgent(n_states, n_actions)
mb_agent = ModelBasedAgent(n_states, n_actions)

def run_episode(agent, step_fn, n_states, max_steps=100):
    state = 0  # 시작 상태
    total_reward = 0
    steps = 0
    deltas = []
    for _ in range(max_steps):
        action = agent.act(state)
        next_state, reward, done = step_fn(state, action)
        delta = agent.update(state, action, reward, next_state, done)
        deltas.append(abs(delta))
        total_reward += reward
        state = next_state
        steps += 1
        if done:
            break
    return total_reward, steps, np.mean(deltas)

mf_rewards, mb_rewards = [], []
mf_steps, mb_steps = [], []
mf_deltas, mb_deltas = [], []

for ep in range(n_episodes):
    r, s, d = run_episode(mf_agent, step_fn, n_states)
    mf_rewards.append(r); mf_steps.append(s); mf_deltas.append(d)
    
    r, s, d = run_episode(mb_agent, step_fn, n_states)
    mb_rewards.append(r); mb_steps.append(s); mb_deltas.append(d)

# 결과 출력
print("=== 이중 시스템 비교 ===")
print(f"초기 10 에피소드 평균 스텝 수:")
print(f"  Model-Free:  {np.mean(mf_steps[:10]):.1f}")
print(f"  Model-Based: {np.mean(mb_steps[:10]):.1f}")
print(f"후반 10 에피소드 평균 스텝 수:")
print(f"  Model-Free:  {np.mean(mf_steps[-10:]):.1f}")
print(f"  Model-Based: {np.mean(mb_steps[-10:]):.1f}")
print(f"\n|δ| 수렴 (마지막 10 에피소드):")
print(f"  Model-Free:  {np.mean(mf_deltas[-10:]):.4f}")
print(f"  Model-Based: {np.mean(mb_deltas[-10:]):.4f}")

fig, axes = plt.subplots(1, 2, figsize=(12, 4))
window = 10
mf_smooth = np.convolve(mf_steps, np.ones(window)/window, mode='valid')
mb_smooth = np.convolve(mb_steps, np.ones(window)/window, mode='valid')

axes[0].plot(mf_smooth, label='Model-Free (TD)', color='steelblue')
axes[0].plot(mb_smooth, label='Model-Based (Dyna)', color='tomato')
axes[0].set_title('에피소드당 스텝 수 (↓ 좋음)')
axes[0].set_xlabel('에피소드'); axes[0].set_ylabel('스텝 수')
axes[0].legend()

axes[1].plot(mf_deltas, label='MF |δ|', color='steelblue', alpha=0.7)
axes[1].plot(mb_deltas, label='MB |δ|', color='tomato', alpha=0.7)
axes[1].set_title('평균 |RPE| 수렴')
axes[1].set_xlabel('에피소드'); axes[1].set_ylabel('|δ|')
axes[1].legend()

plt.tight_layout()
plt.savefig('hierarchical_rpe_dual_system.png', dpi=150, bbox_inches='tight')
print("그래프 저장: hierarchical_rpe_dual_system.png")
```

**해석**: Model-based 에이전트(Dyna-Q)는 초기 에피소드에서 model-free TD보다 현저히 빠르게 학습한다 — 플래닝 덕분이다. 그러나 환경이 충분히 탐색되면 두 에이전트의 성능이 수렴한다. 이는 초기 목표지향(model-based)에서 후기 습관적(model-free) 행동으로의 전환을 반영한다.

### 실험 2: 결과 평가절하 시뮬레이션

```python
import numpy as np

def devaluation_test(mf_q, mb_q, devalue_state=15, factor=0.1):
    """
    목표 보상을 평가절하할 때 두 시스템의 반응 차이.
    MF는 즉시 행동을 바꾸지 못함, MB는 즉시 재계획.
    """
    # 평가절하: 목표 상태의 가치를 10%로
    mf_goal_val = mf_q[devalue_state].max()
    mb_goal_val = mb_q[devalue_state].max()
    
    print("=== 결과 평가절하 테스트 ===")
    print(f"평가절하 전 목표 Q값: MF={mf_goal_val:.3f}, MB={mb_goal_val:.3f}")
    
    # MF는 Q값이 저장되어 있어 즉시 반영 안 됨
    mf_after = mf_goal_val  # 변화 없음
    # MB는 모델을 통해 재계획 가능
    mb_after = mb_goal_val * factor  # 즉시 반영
    
    print(f"평가절하 후 목표 Q값: MF={mf_after:.3f}, MB={mb_after:.3f}")
    print(f"→ MF는 평가절하에 둔감 (습관적), MB는 즉시 반응 (목표지향적)")

devaluation_test(mf_agent.Q, mb_agent.Q)
```

**반례**: 이 모델의 중요한 한계는 $\omega$ 계산의 명시적 신경 기질이 아직 논란 중이라는 것이다. 전전두피질 손상 연구는 목표지향 행동이 손상된다는 것을 보이지만, 정확히 어떤 하위 영역이 $\omega$를 계산하는지는 불분명하다. 또한 습관과 목표지향의 이분법이 지나치게 단순화된 것일 수 있으며, 스펙트럼으로 보는 관점도 있다.

## 🌉 간극의 위치

- ✅ **이중 시스템의 행동 증거**: 결과 평가절하 패러다임에서 배내측 선조체 손상은 목표지향을, 배외측 선조체 손상은 습관 학습을 선택적으로 손상시킨다.
- ✅ **계층적 RPE의 계산 모델**: Daw et al.(2005)의 불확실성 기반 중재 모델은 인간 행동 데이터를 양적으로 피팅한다.
- ✅ **D1/D2 경로의 반대 역할**: 직접 경로(D1, "Go")와 간접 경로(D2, "NoGo")가 행동 선택과 억제를 반대 방향으로 조절한다.
- ❌ **계층의 수**: 두 수준(model-free/model-based)이 충분한가, 아니면 더 많은 계층이 필요한가? Botvinick(2009)의 계층적 RL은 더 많은 수준을 제안하지만 신경 기반이 불분명하다.
- ❌ **중재 메커니즘의 명시화**: $\omega$를 계산하는 신경 회로가 정확히 무엇인지에 대한 합의가 없다.
- ❌ **습관의 정의**: 행동학적 습관(결과에 무감각)과 주관적 자동성(노력 없이 하는 행동)이 항상 일치하지 않으며, 이 구분이 RPE 계층 이론의 적용 범위를 제한한다.

## 🧬 원리의 회수

RPE의 계층화는 단일 예측 원리가 복잡한 뇌 구조 속에서 어떻게 구현되는지를 보여준다. $\delta = r + \gamma V(s') - V(s)$라는 단일 공식이 복측 선조체에서 전전두피질까지 다른 파라미터와 다른 시간 규모로 작동하며, 이 다층 구조가 행동의 유연성과 효율성을 동시에 달성한다.

중요한 통찰은 계층이 단순한 복잡성 추가가 아니라는 것이다. 계층 구조는 계산 효율성을 제공한다: 상위 수준은 추상적 계획을 수립하고, 하위 수준은 구체적 실행을 처리한다. 이 분업이 없다면 단순한 일상적 과제를 수행하는 데도 막대한 계획 비용이 든다. 습관이 단순한 실수가 아니라 적응적 전략인 이유가 여기에 있다.

그러나 이 계층 구조는 병리의 원천이기도 하다. 강박증, 중독, 우울증은 모두 두 시스템 간 균형의 붕괴로 이해될 수 있다 — 지나친 model-free 지배(강박, 중독), 또는 지나친 model-based 지배(반추, 불안). RPE 계층 이론은 이 병리를 새로운 시각으로 이해할 프레임을 제공한다.

## 🪞 1인칭

아침에 커피를 끓이는 루틴을 생각해보라. 첫 번째 주에는 각 단계를 의식적으로 계획했다 — 어떤 커피를 쓸지, 물의 온도는, 몇 스푼인지. 이것이 model-based 목표지향이다. 한 달 후에는 커피가 다 끓을 때까지 다른 생각을 하고 있다. 습관이 형성된 것이다 — model-free가 인계받았다.

그런데 어느 날 커피 원두가 바뀌었다. 새 원두로 같은 루틴을 실행했더니 맛이 이상하다. 이때 뇌는 즉시 목표지향 모드로 전환한다 — 뭐가 달라졌는지 의식적으로 점검한다. 큰 $\delta$가 model-free 자동 실행을 중단시키고 model-based 재계획을 활성화한 것이다. 예측 오차가 의식의 문을 두드렸다. 그 두드림 자체의 느낌 — 익숙한 맛이 갑자기 낯설어지는 그 순간 — 은 $\delta$가 크다는 사실로는 설명되지 않는다.

## 📐 예측·반증

**예측 1**: 배내측 선조체(DMS)를 선택적으로 비활성화하면 결과 평가절하 후에도 이전 행동이 지속된다(목표지향이 손상되어 습관처럼 행동한다).
- 반증 조건: DMS 비활성화 후에도 평가절하에 민감한 행동 변화가 나타나면, DMS가 목표지향 학습의 필수 기질이 아니라는 것이다.

**예측 2**: $\omega$(model-based 가중치)는 작업 부하(cognitive load)가 증가할수록 감소한다 — 계산 자원이 제한될 때 model-free가 더 많이 사용된다.
- 반증 조건: 인지 부하 하에서도 $\omega$가 일정하거나 증가하면, 이중 시스템의 자원 경쟁 가정이 틀렸다.

**예측 3**: 강박장애 환자에서 배외측 선조체 과활성화가 model-free 우세와 상관하며, 이것이 반복 행동의 신경 기반이다.
- 반증 조건: OCD에서 배외측 선조체 활성화가 건강군과 유의미하게 다르지 않으면, 습관 시스템 과활성화 가설이 기각된다.

## 🤔 열린 질문

RPE의 계층 구조를 인정하더라도, 도파민이 이 계층에서 유일한 신호인가? 세로토닌, 노르에피네프린, 아세틸콜린 등 다른 신경조절물질도 각자의 예측 오차 신호를 인코딩하는가? 그리고 순수 RPE를 넘어, 도파민은 어떤 다른 정보를 전달하는가? → 다음 문서(03-beyond-rpe.md)에서 탐구한다.

---

> 🧩 **Principle** — RPE는 단일 신호가 아니라 배측-복측 선조체 축을 따라 계층화되며, model-free 습관과 model-based 목표지향 행동을 분리된 학습 시스템이 지원한다.

> 🌉 **Boundary** — 이중 시스템의 불확실성 기반 중재($\omega$)를 계산하는 신경 회로는 아직 완전히 해명되지 않았으며, 계층의 수와 구성도 논란 중이다.

> 🪞 **Experience** — 친숙한 루틴이 예기치 않게 실패하는 순간, 자동성에서 의식적 점검으로의 전환이 일어난다; 이 전환의 느낌 — 낯섦의 출현 — 은 $\delta$의 급증으로 추적되지만 그것으로 소진되지 않는다.

## 📝 연습문제

**기초.** 결과 평가절하(outcome devaluation) 패러다임이 model-free와 model-based 시스템을 어떻게 구분하는가? 쥐 실험에서 어떤 절차가 사용되며, 각 시스템이 평가절하에 어떻게 반응하는지 설명하라.

<details><summary>해설</summary>

결과 평가절하 절차: 훈련 단계에서 쥐는 레버 누르기→음식 보상을 학습한다. 테스트 직전에 음식을 과포화(ad libitum 섭취)시켜 보상의 가치를 낮춘다. Model-based 시스템은 즉시 재계획하여 레버 누르기를 감소시킨다(보상 가치가 낮아졌음을 안다). Model-free 시스템은 저장된 Q값에 따라 레버를 계속 누른다(과거 경험만 반영, 현재 보상 가치를 반영 못함). 배내측 선조체 손상 쥐는 평가절하 후에도 레버를 누른다 → model-based 손상. 배외측 선조체 손상 쥐는 훈련이 덜 되어도 평가절하에 민감 → model-free 손상.

</details>

**심화.** Daw et al.(2005)의 중재 모델에서 $\omega$를 계산하는 데 각 시스템의 "불확실성(variance)"이 사용된다. 불확실성이 매우 높은 환경(보상이 무작위)에서는 어떤 시스템이 우세해야 하는가? 이것이 모형의 예측과 직관적 행동 관찰과 일치하는지 논하라.

<details><summary>해설</summary>

불확실성이 매우 높은 환경에서: Model-based 시스템의 내부 모델도 불확실하고($\text{Var}(Q^{MB})$ 높음), Model-free의 Q값 추정도 불안정($\text{Var}(Q^{MF})$ 높음). Daw 모델에서 $\omega = \text{Var}(Q^{MF}) / (\text{Var}(Q^{MF}) + \text{Var}(Q^{MB}))$이므로, 두 불확실성이 비슷하면 $\omega \approx 0.5$. 그러나 model-based의 내부 모델이 확률적 전이를 제대로 추정한다면 상대적으로 더 안정적일 수 있어 model-free가 우세할 수도 있다. 직관과의 불일치: 무작위 환경에서 인간은 종종 패턴을 찾으려 하는 model-based 행동을 보이지만, 결국 지쳐서 단순 패턴(model-free)으로 전환한다. 이는 자원 제약 하에서 $\omega$가 시간에 따라 변한다는 것을 시사한다.

</details>

**논문 비평.** Daw et al. (2005) "Uncertainty-based competition between prefrontal and dorsolateral striatal systems for behavioral control" (Nature Neuroscience)의 핵심 주장은 불확실성이 낮을 때 model-free가 우세하다는 것이다. 이 주장을 지지하거나 반박하는 이후 연구 두 가지를 인용하고 평가하라.

<details><summary>해설</summary>

지지: Otto et al. (2013, Psychological Science)은 인지 부하(이중 과제)가 있을 때 인간이 더 model-free 전략으로 전환함을 보였다 — 계산 자원 제한이 $\omega$를 낮춘다는 Daw 예측 지지. 반박/수정: Keramati et al. (2016, PNAS)은 시간 압박 하에서 model-based 시스템이 완전히 억제되지 않고 빠른 근사 계획을 사용한다고 주장하며, 이분법적 중재가 아닌 점진적 조절을 제안했다. 또한 단순히 불확실성만이 아니라 "보상의 크기"도 model-based 사용을 증가시킨다는 증거가 있어(Gillan et al., 2015), Daw 모델의 단일 불확실성 요인이 과단순화일 수 있다.

</details>

---

<div align="center">

[◀ 이전: TD 학습의 세 언어](./01-td-three-languages.md) · [📚 README](../README.md) · [다음: 도파민이 예측 이외에 신호하는 것 ▶](./03-beyond-rpe.md)

</div>
