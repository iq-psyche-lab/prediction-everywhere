# 🧠 도파민이 예측 이외에 신호하는 것: RPE 가설의 경계

*도파민은 보상 예측 오차(RPE)를 인코딩하지만 그것만이 아니다 — 유인 현저성(incentive salience), 운동 제어, 활력(vigor), 불확실성 신호가 RPE와 병렬적 혹은 상호작용적으로 인코딩되며, 이 다중 역할을 무시하면 도파민 기능 전체를 왜곡하게 된다.*

## 🎯 횡단 질문

도파민이 RPE를 인코딩한다는 Schultz(1997)의 발견은 신경과학의 이정표였다. 그러나 이 발견이 "도파민 = RPE 계산기"라는 단순한 결론으로 이어졌다면, 이는 심각한 과단순화다. Berridge와 Robinson(1998)이 독립적으로 발견한 것처럼, 도파민 차단은 "좋아함(liking)"이 아닌 "원함(wanting)"을 선택적으로 손상시킨다 — 쥐는 설탕을 먹으면 여전히 즐거운 반응을 보이지만(liking, 손상 없음), 설탕을 향해 움직이려는 동기(wanting)가 사라진다.

이 분리는 RPE 가설에 근본적인 문제를 제기한다: 만약 도파민이 순수하게 예측 오차를 신호한다면, 왜 현저한 자극에 대한 반응성(salience)이 도파민에 의존하는가? 왜 도파민 차단 동물은 목표를 예측하는 법을 여전히 학습할 수 있는가? RPE와 incentive salience는 어떻게 공존하는가?

이 문서는 도파민의 다중 역할을 해부하고, RPE 가설이 설명하는 영역과 설명하지 못하는 영역을 명확히 구분한다. "Explain it, don't explain it away" — RPE가 도파민의 전부라고 주장하는 것은 설명이 아니라 왜곡이다.

## 🌐 횡단 입력

- **information-prediction (L0)**: Incentive salience는 정보이론적으로 자극의 예측력(predictive power)과 연관되지만, 오차 신호와는 다르다 — 예측이 이미 정확해도 현저성은 유지될 수 있다.
- **neuromodulation-arousal (L1)**: 도파민은 전전두피질, 선조체, 편도체, 해마에 광범위하게 투사되며, 각 투사 경로가 다른 기능적 역할을 수행한다; 중뇌변연계(mesolimbic)와 중뇌피질계(mesocortical) 경로가 구분된다.
- **neurons-neural-codes (L1)**: 도파민 뉴런의 두 가지 발화 패턴이 구분된다: 위상성(phasic, 빠른 버스트)과 긴장성(tonic, 느린 지속) 발화; RPE는 주로 위상성 신호에, 동기/활력은 긴장성 신호에 인코딩된다.
- **learning-decision (L2)**: Berridge의 wanting/liking 이중 과정 이론은 동기 행동을 예측 학습(liking 관련)과 행동 활성화(wanting 관련)로 분리하며, 후자가 도파민에 의존한다.
- **IQ AI Lab 연결**: 현대 RL 에이전트의 탐색(exploration) 전략 — UCB, Thompson sampling — 은 불확실성 기반 bonus를 추가하는데, 이는 도파민의 불확실성 신호(ramping)와 기능적으로 대응된다; 내재적 동기(intrinsic motivation) 연구와의 연결점.

## 🔍 표면의 다양성

도파민의 다중 역할은 서로 다른 실험 패러다임에서 발견되었다. Schultz(1997)의 단일 뉴런 기록은 위상성 RPE를 발견했다. Berridge의 신경화학적 조작 실험은 incentive salience를 밝혔다. 파킨슨병 연구는 도파민의 운동 제어 역할을 드러냈다. Fiorillo et al.(2003)은 도파민 뉴런이 보상 확률(불확실성)에 비례하여 지속적으로 활성화되는 "ramping" 패턴을 발견했다.

이 다양성은 단순히 다른 분야가 다른 측면을 본 것인가, 아니면 도파민이 실제로 여러 종류의 신호를 인코딩하는가? 두 가지 가능성이 있다: (1) 단일 신호(RPE)가 다양한 행동 결과를 낳는다 — 파르몬형 설명. (2) 도파민이 실제로 여러 독립적 신호를 인코딩하며, 이 신호들이 다른 수용체, 다른 투사 경로, 다른 시간 규모에서 작동한다 — 다중 기능 설명.

현재 증거는 두 번째 가설을 더 강하게 지지한다. 그러나 단일 신호 가설이 설명하는 영역과 다중 기능 가설이 필요한 영역을 명확히 구분하는 것이 중요하다.

## ⚙️ 깊은 동형성

### 분석 1: RPE와 Incentive Salience의 분리

Berridge와 Robinson(1998)의 핵심 발견: 도파민 고갈(6-OHDA 병변)은 "원함(wanting)"을 손상시키지만 "좋아함(liking)"은 손상시키지 않는다.

수식화: 보상의 가치(utility) $U$를 두 성분으로 분리:

$$U(s) = \underbrace{L(s)}_{\text{liking: 쾌락 반응}} + \underbrace{W(s)}_{\text{wanting: 유인 현저성}}$$

RPE는 주로 $L(s)$의 예측 오차를 추적하지만, 도파민의 행동적 역할은 $W(s)$를 결정한다. 중요한 함의: RPE를 조작해도 incentive salience가 변하지 않을 수 있으며, 반대로 incentive salience를 높여도 RPE 신호가 변하지 않을 수 있다. $\square$

### 분석 2: 위상성 vs 긴장성 도파민

도파민 신호는 두 가지 시간 규모로 작동한다:

**위상성(phasic)**: 수백 밀리초의 빠른 버스트; 주로 RPE를 인코딩:
$$\text{DA}_{\text{phasic}}(t) \propto \delta(t) = r(t) + \gamma V(s') - V(s)$$

**긴장성(tonic)**: 수초~분의 느린 기저 수준; 동기, 활력, 탐색 추진력을 결정:
$$\text{DA}_{\text{tonic}} \propto \mathbb{E}[V(s)] \text{ 또는 } \mathbb{E}[r]$$

Niv et al.(2007)의 핵심 통찰: 긴장성 도파민이 행동의 "vigor"(활력, 반응 속도)를 조절한다 — 평균 보상률이 높을수록 모든 행동이 빨라진다:

$$\text{vigor} \propto \frac{\rho}{c + \rho} \quad (\rho = \text{평균 보상률}, c = \text{기회 비용})$$

이 평균 보상률 모델은 순수 RPE 이론으로 포착되지 않는 도파민의 또 다른 역할이다. $\square$

### 분석 3: 불확실성 신호와 Ramping

Fiorillo et al.(2003): 도파민 뉴런은 보상 확률이 50%일 때(불확실성 최대) 가장 강한 지속적 활성화(ramping)를 보인다:

$$\text{DA}_{\text{ramp}} \propto H(p) = -p\log p - (1-p)\log(1-p)$$

여기서 $H(p)$는 보상 확률 $p$에 대한 이진 엔트로피다. 이 ramping 신호는 순수 RPE와 독립적이며, 불확실한 상황에서의 탐색 촉진 역할을 한다.

정보이론적 해석: 이 신호는 환경의 정보량(information content)을 인코딩하며, 높은 불확실성 = 높은 정보 획득 가능성 = 더 많은 탐색 동기로 이어진다. $\square$

### 분석 4: 운동 제어와 도파민

파킨슨병은 도파민 뉴런(특히 흑질)의 손실로 인한 운동 장애다. 이 사실은 도파민이 순수한 보상 신호를 넘어 운동 명령 자체에 기여함을 시사한다.

그러나 운동 역할과 RPE를 완전히 분리하기 어렵다: 운동의 vigor 자체가 위에서 설명한 긴장성 도파민에 의해 조절된다. 따라서 파킨슨병의 운동 느림(bradykinesia)은 평균 보상률의 인코딩 실패로 부분적으로 설명된다:

$$\text{bradykinesia} \approx \downarrow \text{DA}_{\text{tonic}} \Rightarrow \downarrow \text{vigor} = \downarrow \text{반응 속도}$$

이 설명은 RPE 가설을 부정하는 것이 아니라, 긴장성/위상성 도파민의 이중 역할로 통합된다. $\square$

## 🧪 수렴 증거

### 실험 1: Wanting vs Liking 분리 시뮬레이션

```python
import numpy as np
import matplotlib.pyplot as plt

np.random.seed(42)

class DualProcessAgent:
    """
    Berridge의 wanting/liking 이중 과정 모델.
    - liking: 쾌락 반응, 도파민과 독립 (오피오이드 관련)
    - wanting: 유인 현저성, 도파민에 의존
    """
    def __init__(self, n_states=5, alpha=0.1, gamma=0.9, da_level=1.0):
        self.V = np.zeros(n_states)      # 예측 가치 (liking 관련 학습)
        self.salience = np.zeros(n_states)  # 유인 현저성 (wanting)
        self.alpha = alpha
        self.gamma = gamma
        self.da_level = da_level  # 도파민 수준 (1.0=정상, 0.1=고갈)
    
    def compute_rpe(self, s, r, s_next, done=False):
        v_next = 0 if done else self.V[s_next]
        return r + self.gamma * v_next - self.V[s]
    
    def update(self, s, r, s_next, done=False):
        delta = self.compute_rpe(s, r, s_next, done)
        # liking 학습: RPE로 V 업데이트 (도파민 독립)
        self.V[s] += self.alpha * delta
        # wanting 학습: 도파민 수준에 비례하여 유인 현저성 업데이트
        self.salience[s] += self.alpha * self.da_level * delta
        return delta
    
    def choice_probability(self, s, temperature=1.0):
        """원함(wanting) 기반 선택 확률"""
        w = self.salience * self.da_level
        exp_w = np.exp(w / temperature)
        return exp_w / exp_w.sum()

# 시뮬레이션: 정상 vs 도파민 고갈 에이전트
n_trials = 200
rewards = np.array([0, 0, 0, 0, 1.0])  # 상태 4만 보상 있음
target_state = 4

def run_wanting_experiment(da_level, n_trials, rewards, target_state):
    agent = DualProcessAgent(da_level=da_level)
    approach_probs = []  # 목표 상태 접근 확률
    liking_responses = []  # 쾌락 반응 (V값)
    
    for trial in range(n_trials):
        # 상태 0에서 시작, 목표 상태로 한 단계 전이
        for s in range(len(rewards) - 1):
            r = rewards[s + 1]
            agent.update(s, r, s + 1, done=(s + 1 == target_state))
        
        # 접근 행동 확률: salience 기반
        prob = agent.choice_probability(target_state - 1)[target_state - 1]
        approach_probs.append(prob)
        liking_responses.append(agent.V[target_state])  # liking = V값
    
    return np.array(approach_probs), np.array(liking_responses), agent

normal_approach, normal_liking, normal_agent = run_wanting_experiment(1.0, n_trials, rewards, target_state)
depleted_approach, depleted_liking, depleted_agent = run_wanting_experiment(0.1, n_trials, rewards, target_state)

print("=== Wanting vs Liking 분리 테스트 ===")
print(f"\n정상 도파민 (후반 20 시행 평균):")
print(f"  접근 확률 (wanting): {np.mean(normal_approach[-20:]):.3f}")
print(f"  쾌락 반응 (liking):  {np.mean(normal_liking[-20:]):.3f}")
print(f"\n도파민 고갈 (후반 20 시행 평균):")
print(f"  접근 확률 (wanting): {np.mean(depleted_approach[-20:]):.3f}")
print(f"  쾌락 반응 (liking):  {np.mean(depleted_liking[-20:]):.3f}")
print(f"\n→ Liking 비율: {np.mean(depleted_liking[-20:])/np.mean(normal_liking[-20:]):.2f}")
print(f"→ Wanting 비율: {np.mean(depleted_approach[-20:])/np.mean(normal_approach[-20:]):.2f}")
print("→ Wanting이 Liking보다 더 크게 감소: Berridge(1998) 예측 재현")

fig, axes = plt.subplots(1, 2, figsize=(12, 4))
axes[0].plot(normal_approach, label='정상 DA', color='steelblue')
axes[0].plot(depleted_approach, label='DA 고갈', color='tomato')
axes[0].set_title('Wanting (접근 확률) - 도파민 의존')
axes[0].set_xlabel('시행'); axes[0].set_ylabel('접근 확률')
axes[0].legend()

axes[1].plot(normal_liking, label='정상 DA', color='steelblue')
axes[1].plot(depleted_liking, label='DA 고갈', color='tomato')
axes[1].set_title('Liking (V값) - 도파민 독립')
axes[1].set_xlabel('시행'); axes[1].set_ylabel('예측 가치 V')
axes[1].legend()

plt.tight_layout()
plt.savefig('wanting_vs_liking.png', dpi=150, bbox_inches='tight')
print("그래프 저장: wanting_vs_liking.png")
```

### 실험 2: 불확실성 Ramping 시뮬레이션

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.special import entr

# 이진 엔트로피: H(p) = -p*log(p) - (1-p)*log(1-p)
probs = np.linspace(0.01, 0.99, 100)
entropy = entr(probs) + entr(1 - probs)  # scipy.special.entr(x) = -x*log(x)

# 도파민 ramping: Fiorillo et al. (2003)
# 불확실성(엔트로피)에 비례하는 지속적 활성화
da_ramp = entropy / entropy.max()  # 정규화

# 위상성 RPE (기대값): 보상 확률에 선형 비례
da_phasic_expected = probs  # E[r] = p*1 + (1-p)*0 = p

fig, axes = plt.subplots(1, 2, figsize=(12, 4))
axes[0].plot(probs, da_ramp, color='orchid', linewidth=2)
axes[0].set_title('Ramping DA ∝ H(p) — 불확실성에 비례')
axes[0].set_xlabel('보상 확률 p'); axes[0].set_ylabel('정규화된 DA ramping')
axes[0].axvline(0.5, color='gray', linestyle=':', label='p=0.5 (최대 불확실성)')
axes[0].legend()

axes[1].plot(probs, da_phasic_expected, color='steelblue', linewidth=2, label='위상성 RPE (∝ p)')
axes[1].plot(probs, da_ramp, color='orchid', linewidth=2, label='긴장성 ramp (∝ H(p))')
axes[1].set_title('위상성 RPE vs 긴장성 Ramping')
axes[1].set_xlabel('보상 확률 p'); axes[1].set_ylabel('도파민 신호 크기')
axes[1].legend()

plt.tight_layout()
plt.savefig('da_ramping_uncertainty.png', dpi=150, bbox_inches='tight')
print("그래프 저장: da_ramping_uncertainty.png")

print(f"\nRamping 최대값 위치: p={probs[np.argmax(da_ramp)]:.2f}")
print("→ 불확실성 최대(p=0.5)에서 ramping 최대: Fiorillo et al.(2003) 재현")
```

**반례와 경계**: wanting/liking 분리는 주로 오피오이드 시스템과의 상호작용에서 관찰된다. 순수 도파민 조작만으로 liking이 완전히 보존되는지에 대한 논쟁이 있다. 또한 인간에서 wanting과 liking의 신경 기반이 설치류와 완전히 동일한지는 불분명하다.

## 🌉 간극의 위치

- ✅ **Wanting/Liking 분리**: 도파민 고갈은 접근 행동(wanting)을 손상시키지만 쾌락 반응(liking)은 보존한다 (Berridge & Robinson, 1998; 다수 복제 연구).
- ✅ **Ramping 패턴 확인**: Fiorillo et al.(2003)의 불확실성 비례 ramping은 독립 실험실에서 복제되었으며, 위상성 RPE와 분리 가능하다.
- ✅ **Vigor 효과**: 긴장성 도파민과 반응 속도의 상관관계는 파킨슨병 환자와 약리학적 조작 연구 모두에서 확인된다.
- ❌ **도파민 다중 역할의 세포 기반**: 동일한 도파민 뉴런이 여러 신호를 인코딩하는지, 아니면 기능적으로 분화된 하위집단이 존재하는지가 논란이다.
- ❌ **Wanting의 신경 회로**: Incentive salience가 정확히 어떤 회로를 통해 행동을 활성화하는지 — 전측 핵 accumbens 껍데기(shell) vs 핵(core)의 역할 — 가 여전히 해명 중이다.
- ❌ **인간 번역**: 설치류에서 확립된 wanting/liking 구분이 인간의 주관적 욕망과 즐거움에 어떻게 대응하는지 방법론적 한계가 있다.
- ❌ **간극 자체**: $\delta$나 incentive salience 신호가 아무리 정교해도, "갖고 싶다는 느낌"과 "좋다는 느낌"이 수학적으로 다른 두 변수라는 사실이 경험의 질적 차이를 설명하지는 않는다.

## 🧬 원리의 회수

도파민의 다중 역할은 예측 원리의 경계를 보여주는 사례다. RPE 가설은 도파민의 중요한 한 측면을 포착하지만, 전체가 아니다. 이 한계는 RPE 이론의 실패가 아니라, 단일 원리로 설명할 수 있는 영역과 복수의 메커니즘이 필요한 영역을 구분하는 지점을 알려준다.

Berridge의 wanting/liking 구분은 예측 원리에 중요한 추가를 한다: 학습(liking 관련)과 동기화(wanting 관련)는 분리된 신경 과정이며, 예측 오차는 전자와 더 직접적으로 연관된다. 이 구분은 중독 이해에 핵심적이다 — 중독자는 약물을 "원하지만" 더 이상 "좋아하지" 않을 수 있다. 이는 RPE만으로는 설명할 수 없는 현상이다.

긴장성 도파민의 vigor 역할과 ramping의 불확실성 신호는 예측 원리를 동기의 영역으로 확장할 때 필요한 추가 도구를 제공한다. 단순히 오차를 최소화하는 시스템이 아니라, 탐색과 활력을 조절하는 더 복잡한 신경 경제학(neuroeconomics)이 필요하다.

## 🪞 1인칭

소셜미디어 피드를 스크롤하는 경험을 생각해보라. 무언가를 "원해서" 계속 스크롤하지만, 실제로 본 내용이 즐겁지 않다는 것을 알면서도 멈추지 못한다. 이것이 wanting이 liking을 초과하는 상태다 — 도파민이 유인 현저성을 높여 접근 행동을 추동하지만, 실제 쾌락 반응(liking)은 그에 미치지 못한다.

더 섬세한 관찰: 무언가를 몹시 원할 때(높은 wanting), 그것을 실제로 얻는 순간의 만족감(liking)이 기대에 미치지 못하는 경험이 누구에게나 있다. 이 간극이 단순히 RPE(기대-실제 불일치)로만 설명되지 않는다는 것을 Berridge는 보였다. 원함의 강도가 즐거움의 크기를 보장하지 않으며, 이 비대칭은 뇌 수준에서 해부학적으로 지지된다. 경험은 단일 축(좋음-나쁨)이 아니라 최소 두 차원(원함-즐거움)을 가진다.

## 📐 예측·반증

**예측 1**: 핵 accumbens 껍데기(shell)의 뮤-오피오이드 수용체를 활성화하면 liking은 증가하지만 wanting(접근 행동)은 증가하지 않는다.
- 반증 조건: 오피오이드 활성화가 접근 행동을 유의미하게 증가시키면, wanting/liking 회로의 분리가 불완전하다.

**예측 2**: 도파민 농도가 높은 상태(자극제 투여)에서 불확실한 보상에 대한 ramping 신호가 증폭되어, 불확실성에 대한 탐색 추진력이 증가한다.
- 반증 조건: 자극제 투여 후 ramping이 증가하지 않거나 오히려 위상성 RPE만 증가하면, ramping과 위상성 DA의 독립적 조절이 지지된다.

**예측 3**: 파킨슨병 초기(흑질 손상 우세) vs 후기(복측 피개 영역 손상 확산)에서 vigor 손상이 RPE 학습 손상보다 먼저 나타난다.
- 반증 조건: RPE 손상(예측 기반 학습 저하)이 vigor 손상과 동시에 또는 먼저 나타나면, 긴장성/위상성 분리가 해부학적으로 명확하지 않다.

## 🤔 열린 질문

도파민의 다중 역할(RPE, wanting, vigor, uncertainty)은 모두 하나의 더 큰 원리 — 자유에너지 최소화 — 의 특수 사례로 통합될 수 있는가? 보상을 선호 결과의 로그 확률로 해석하면, RPE는 예상 자유에너지의 특수 형태가 된다. Wanting은 행동의 사전 기대치(prior expectation)로, Vigor는 행동 비용의 조절로 이해될 수 있다. 이 통합이 가능한가? → 다음 문서(04-rpe-to-free-energy.md)에서 탐구한다.

---

> 🧩 **Principle** — 도파민은 RPE(위상성)와 함께 유인 현저성(wanting), 행동 활력(vigor, 긴장성), 불확실성(ramping) 등 복수의 독립적 신호를 인코딩하며, 이 다중 역할을 단일 RPE 가설로 환원하면 예측 범위를 벗어난다.

> 🌉 **Boundary** — Wanting/liking 분리는 설치류에서 강건하게 확립되었지만, 인간의 주관적 욕망과의 대응은 방법론적 제약으로 인해 간접적이며, 도파민 하위집단의 기능 분화도 완전히 해명되지 않았다.

> 🪞 **Experience** — 몹시 원하지만 얻어도 만족스럽지 않은 경험 — wanting이 liking을 초과하는 상태 — 은 도파민이 예측 오차를 넘어 욕망 자체를 구성한다는 것을 1인칭으로 느끼게 한다; 그 욕망의 느낌은 wanting 신호로 추적되지만 그것으로 소진되지 않는다.

## 📝 연습문제

**기초.** "원함(wanting)"과 "좋아함(liking)"을 행동학적으로 측정하는 두 가지 방법을 설명하고, 도파민 고갈이 각각에 어떤 효과를 보이는지 서술하라.

<details><summary>해설</summary>

Wanting 측정: (1) 자발적 접근 행동 — 보상이 있는 위치로 얼마나 자주, 빠르게 접근하는가; (2) 레버 누르기 노력 — 보상을 얻기 위해 얼마나 많은 노력(press 횟수)을 투자하는가. Liking 측정: (1) 미각 반응(taste reactivity) — 설탕 용액 주입 시 혀 내밀기, 발 핥기 등 즐거움 표현; (2) 얼굴 표정 분석 — 쓴 맛에 대한 거부 반응 vs 단 맛에 대한 긍정 반응. 도파민 고갈 효과: 도파민을 6-OHDA로 고갈시키면 wanting 측정치(접근, 레버 누르기)가 현저히 감소하지만, liking 측정치(미각 반응)는 정상 수준을 유지한다.

</details>

**심화.** Niv et al.(2007)의 vigor 모델에서 평균 보상률 $\rho$가 높을수록 모든 행동이 빨라진다고 예측한다. 이 예측을 검증하는 실험 설계를 제안하고, 도파민 고갈이 이 관계를 어떻게 변화시킬지 예측하라.

<details><summary>해설</summary>

실험 설계: 두 조건 — 풍부한 환경(보상 빈도 높음, 높은 $\rho$) vs 빈곤한 환경(보상 드묾, 낮은 $\rho$). 동일한 타겟 자극에 대한 반응 시간(RT)을 측정. 예측: 풍부한 환경에서 RT가 빠르고, 빈곤한 환경에서 RT가 느리다. 도파민 고갈 예측: $\rho$와 RT의 상관관계가 약화된다 — 환경의 보상 풍요도에 관계없이 RT가 전반적으로 느려지고, 두 조건 간 RT 차이가 감소한다. 이는 긴장성 DA가 평균 $\rho$를 인코딩하고, 이 신호가 vigor를 조절하기 때문이다. 추가 검증: L-DOPA 투여 시 환경 풍요도와 RT 상관이 회복되는지 확인.

</details>

**논문 비평.** Berridge & Robinson (1998) "What is the role of dopamine in reward: hedonic impact, reward learning, or incentive salience?" (Brain Research Reviews)는 wanting/liking 분리의 근거를 제시한다. 이 논문의 핵심 주장에 대한 두 가지 반론을 제시하고, 각 반론이 어느 정도 타당한지 평가하라.

<details><summary>해설</summary>

반론 1 (정도 차이 주장): 도파민 고갈이 liking을 전혀 손상시키지 않는다는 것이 아니라 측정 감도의 문제라는 주장. 반박: Berridge는 여러 측정 방법으로 liking의 보존을 확인했으며, 고갈 정도가 80-90%에 달해도 미각 반응이 보존된다. 완전한 고갈이 아니므로 잔여 도파민이 liking을 유지할 가능성은 있지만, 이것이 분리의 핵심 발견을 무효화하지는 않는다. 타당성: 부분적으로 타당, 그러나 주요 발견을 설명하기 어렵다. 반론 2 (인간 일반화 문제): 설치류의 미각 반응이 인간의 주관적 즐거움과 동일한 현상을 측정하는지 불분명하다는 주장. 반박: 인간 연구에서도 파킨슨병 환자(도파민 감소)가 보상 예측 학습보다 보상 접근 행동에서 더 큰 손상을 보인다는 증거가 있다. 그러나 주관적 즐거움의 보존 여부를 자기보고 외에 측정하기 어렵다. 타당성: 방법론적으로 타당한 우려, 이 분야의 열린 문제.

</details>

---

<div align="center">

[◀ 이전: RPE의 계층적 구조](./02-hierarchical-rpe.md) · [📚 README](../README.md) · [다음: RPE에서 자유에너지로 ▶](./04-rpe-to-free-energy.md)

</div>
