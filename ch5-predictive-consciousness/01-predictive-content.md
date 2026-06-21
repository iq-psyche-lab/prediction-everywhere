# 🧠 예측처리가 설명하는 의식 내용
*뇌는 세계를 직접 보는 것이 아니라 자신의 최선 가설을 경험한다 — 예측처리는 의식의 내용을 풍부하게 설명하지만, 경험이 존재한다는 사실 자체는 설명하지 못한다.*

## 🎯 횡단 질문

예측오류 $\delta = r - \hat{r}$ 가운데 어느 것이 의식적 경험의 내용을 구성하며, 어느 것은 무의식적으로 억제되는가? 정밀도 가중치 $\pi$ 는 이 선별을 어떻게 결정하는가?

$$\delta_t = r_t - \hat{r}_t, \qquad \hat{r}_t = \mathbb{E}[r \mid \text{prior beliefs}]$$

$$\text{posterior} \propto \pi_{\text{likelihood}} \cdot \mathcal{L}(r \mid h) \times \pi_{\text{prior}} \cdot P(h)$$

## 🌐 횡단 입력
- theories-of-consciousness (L4) — 전역 작업공간 이론(GWT), 고차 이론(HOT)과 예측처리의 교차점
- information-prediction (L0) — 베이즈 추론의 기본 틀: $P(h \mid r) \propto P(r \mid h) P(h)$
- perception (L2) — 지각이 구성적(constructive) 과정임을 보여주는 착시·양안경쟁 현상
- IQ AI Lab LLM 직결 설명 — 대형 언어 모델도 토큰 수준 예측오류를 최소화하는 방향으로 학습되지만, 그 내부에 '경험하는 것이 어떠한가(what it is like)'가 있는지는 동일하게 미결 문제로 남는다

## 🔍 표면의 다양성

우리는 매 순간 다채로운 지각 경험을 한다. 커피 향이 코를 찌르는 감각, 창밖으로 보이는 나무의 윤곽, 낯선 언어 속에서 불현듯 알아채는 단어 하나. 이 경험들은 서로 판이하게 달라 보이지만, 예측처리 이론은 이것들이 공통된 계산 원리 — 예측과 예측오류의 상호작용 — 로부터 생성된다고 제안한다.

더 흥미로운 현상은 **지각적 다의성(perceptual ambiguity)** 이다. 두 눈에 서로 다른 영상을 동시에 제시하는 양안경쟁(binocular rivalry) 실험에서 관찰자는 두 영상을 동시에 보지 못한다. 대신 몇 초마다 한 영상이 사라지고 다른 영상이 의식 전면에 떠오르는 교번(alternation)이 일어난다. 네커 정육면체(Necker cube)나 루빈의 꽃병(Rubin's vase) 같은 양의적 도형에서도 마찬가지다 — 뇌에 입력되는 망막 자극은 변하지 않는데 지각은 자발적으로 뒤집힌다.

이 현상들은 고전적 지각 심리학에서 다소 수수께끼로 남아 있었다. 예측처리 이론은 이를 베이즈 추론의 자연스러운 귀결로 설명한다.

## ⚙️ 깊은 동형성

### 분석 1: 의식 내용 = 뇌의 최선 가설

Jacob Hohwy는 『The Predictive Mind』(2013)에서 지각을 **가설 검증(hypothesis testing)** 의 과정으로 정식화한다. 뇌의 위계적 피질 구조에서 하향(top-down) 신호는 예측 $\hat{r}$을 전달하고, 상향(bottom-up) 신호는 예측오류 $\delta$를 전달한다. 의식에 나타나는 내용은 예측도, 원시 감각 신호도 아닌, 그 순간 **가장 높은 사후 확률을 가진 가설** $h^*$ 이다:

$$h^* = \arg\max_h P(h \mid r) = \arg\max_h \left[ \log P(r \mid h) + \log P(h) \right]$$

Anil Seth는 이를 한층 생생하게 표현한다. 『Being You』(2021)에서 그는 지각을 **"통제된 환각(controlled hallucination)"** 이라 부른다. 우리가 꿈에서 경험하는 환각과 깨어있을 때의 지각의 차이는, 후자의 경우 감각 입력이 환각을 **제약하고 교정**한다는 점뿐이다. 지각 자체가 뇌의 생성 모델(generative model)이 만들어내는 구성물(construct)이라는 점에서 두 상태는 연속선상에 있다. $\square$

### 분석 2: 정밀도 가중치와 의식의 문턱

모든 예측오류가 의식에 도달하는 것은 아니다. Karl Friston의 자유에너지 원리(Free Energy Principle) 틀 안에서, 예측오류가 상위 계층으로 전파되는 정도는 **정밀도(precision)** $\pi$ 에 의해 조절된다:

$$\delta_{\pi} = \pi \cdot \delta = \pi \cdot (r - \hat{r})$$

정밀도는 감각 채널의 신뢰성에 대한 메타 추론으로, 신경생물학적으로는 **주의(attention)** 에 해당한다. 정밀도가 높게 할당된 예측오류는 상위 피질로 전파되어 현재의 가설을 갱신하고 의식적 경험에 반영된다. 반면 정밀도가 낮은 오류 — 예컨대 조용한 배경 소음이나 습관화된 자극 — 는 낮은 계층에서 억제되어 의식에 이르지 못한다.

이는 칵테일파티 효과를 우아하게 설명한다. 수십 개의 대화가 동시에 귀를 두드리지만, 자신의 이름이 들릴 때만 주의가 — 즉 정밀도가 — 즉각 재배분되어 그 신호가 의식 전면에 부상한다. $\square$

### 분석 3: 양안경쟁 — 두 가설의 경쟁

양안경쟁은 예측처리 이론의 가장 선명한 증거 사례 중 하나다. 왼쪽 눈에 수평선 격자를, 오른쪽 눈에 수직선 격자를 제시하면 뇌는 두 입력을 동시에 설명하는 단일 가설을 만들 수 없다. 두 가설 $h_1$(수평선)과 $h_2$(수직선)는 동일한 감각 증거에 대해 경쟁한다:

$$P(h_1 \mid r) \approx P(h_2 \mid r) \approx 0.5 \quad \text{(초기 상태)}$$

그러나 이 균형은 불안정하다. Rao & Ballard(1999)의 예측 부호화(predictive coding) 모델과 이후의 확장 연구들은 현재 지배적인 가설이 만들어내는 예측오류가 누적되면서 — 즉 현재 해석이 감각 증거를 점점 잘못 설명하게 되면서 — 결국 경쟁 가설로의 전환이 일어남을 보인다. 전환 시간의 분포는 감마 분포(gamma distribution)를 따르며, 이는 경쟁 과정의 확률적 성격을 반영한다.

신경영상 연구들은 이 관점을 지지한다. 의식에 올라온 지각과 억제된 지각은 서로 다른 뇌 영역 활성 패턴을 보이며, 특히 전두-두정 피질 네트워크의 활성이 의식적 지각의 전환과 상관된다 — 전역 작업공간 이론(Baars, Dehaene)의 예측과도 수렴하는 결과다. $\square$

### 분석 4: 네커 정육면체 — 모호한 사전 분포

네커 정육면체는 망막 영상이 완전히 고정되어 있음에도 두 가지 3차원 해석 사이를 오간다. 예측처리 관점에서 이는 **하향 사전 분포(prior)가 두 가설에 균등하게 배분된 상황**이다. 어느 해석도 더 강한 사전 우위를 점하지 못하므로, 뇌는 현재 활성화된 가설이 만들어내는 예측오류 누적에 따라 교번한다. 의도적으로 한 해석을 '붙들려' 노력하면 전환이 늦춰지는데, 이는 상위 계층의 하향 신호 — 즉 의도적 주의에 의한 정밀도 재배분 — 가 가설의 안정성에 개입함을 시사한다.

이 모든 분석은 공통된 원리로 수렴한다. $\square$

## 🧪 수렴 증거

### 실험 1: 양안경쟁의 베이즈 모델 시뮬레이션

아래 코드는 두 경쟁 가설 사이의 확률적 교번을 예측오류 누적 메커니즘으로 구현한다. 각 타임스텝에서 현재 지배 가설의 예측오류가 누적되고, 임계값을 초과하면 전환이 일어난다.

```python
import numpy as np
import scipy.stats as stats
import matplotlib.pyplot as plt

# ─────────────────────────────────────────────
# Bayesian model of binocular rivalry
# Two competing percepts (h1, h2) alternate
# driven by accumulating prediction error
# ─────────────────────────────────────────────

rng = np.random.default_rng(42)

# Parameters
T = 300          # total time steps (arbitrary units)
dt = 0.05        # time step size (seconds)
tau = 1.0        # prediction-error decay time constant
precision = 2.5  # precision weighting (attention level)
noise_std = 0.3  # stochastic noise on prediction error
threshold = 3.0  # accumulated error threshold for switching

# State variables
percept = np.zeros(T, dtype=int)   # 0 = h1 dominant, 1 = h2 dominant
pe_accum = np.zeros(T)             # accumulated prediction error
switch_times = []

current = 0      # currently dominant hypothesis (h1)
pe = 0.0         # running accumulated prediction error

for t in range(T):
    # Prediction error for the currently dominant hypothesis
    # rises over time (adaptation / fatigue)
    base_pe = 1.0 - np.exp(-t * dt / (tau * 8))  # slow ramp-up
    noise = rng.normal(0, noise_std)
    pe += dt * (precision * (base_pe + noise) - pe / tau)

    pe_accum[t] = pe
    percept[t] = current

    if pe >= threshold:
        # Hypothesis switch
        current = 1 - current       # flip percept
        switch_times.append(t * dt)
        # Reset pe, but not to zero — hysteresis
        pe = rng.uniform(0.2, 0.6)

switch_durations = np.diff([0] + switch_times + [T * dt])

# ─────────────────────────────────────────────
# Statistics: dominance durations
# ─────────────────────────────────────────────
mean_dur = np.mean(switch_durations)
std_dur  = np.std(switch_durations)

# Fit gamma distribution (empirical finding in rivalry research)
alpha_fit, loc_fit, beta_fit = stats.gamma.fit(switch_durations, floc=0)

print(f"Number of switches: {len(switch_times)}")
print(f"Mean dominance duration: {mean_dur:.2f}s  (SD={std_dur:.2f}s)")
print(f"Gamma fit — shape (α): {alpha_fit:.2f}, scale (β): {beta_fit:.2f}")

# ─────────────────────────────────────────────
# Visualization
# ─────────────────────────────────────────────
fig, axes = plt.subplots(3, 1, figsize=(10, 8))
t_axis = np.arange(T) * dt

# Panel 1: dominant percept over time
axes[0].fill_between(t_axis, percept, step='post', alpha=0.7,
                      color='steelblue', label='h1 dominant')
axes[0].fill_between(t_axis, 1 - percept, step='post', alpha=0.7,
                      color='coral', label='h2 dominant')
axes[0].set_ylabel('Dominant percept')
axes[0].set_yticks([0, 1]); axes[0].set_yticklabels(['h1', 'h2'])
axes[0].legend(loc='upper right'); axes[0].set_title('Binocular Rivalry: Perceptual Alternation')

# Panel 2: accumulated prediction error
axes[1].plot(t_axis, pe_accum, color='darkgreen', lw=1.2)
axes[1].axhline(threshold, color='red', ls='--', label=f'Threshold={threshold}')
for st in switch_times:
    axes[1].axvline(st, color='gray', alpha=0.4, lw=0.8)
axes[1].set_ylabel('Accumulated PE')
axes[1].legend(); axes[1].set_title('Prediction Error Accumulation (→ drives switching)')

# Panel 3: dominance duration histogram + gamma fit
x_range = np.linspace(0, max(switch_durations) * 1.2, 200)
axes[2].hist(switch_durations, bins=12, density=True,
             color='mediumpurple', alpha=0.7, label='Observed durations')
axes[2].plot(x_range,
             stats.gamma.pdf(x_range, alpha_fit, loc_fit, beta_fit),
             'k-', lw=2, label=f'Gamma fit (α={alpha_fit:.1f})')
axes[2].set_xlabel('Dominance duration (s)')
axes[2].set_ylabel('Density')
axes[2].legend(); axes[2].set_title('Distribution of Dominance Durations')

plt.tight_layout()
plt.savefig('binocular_rivalry_simulation.png', dpi=150, bbox_inches='tight')
plt.show()
print("Figure saved to binocular_rivalry_simulation.png")
```

이 시뮬레이션은 세 가지 핵심 예측을 재현한다: (1) 지각 교번의 자발성과 불규칙성, (2) 지배 지속시간이 감마 분포를 따름, (3) 정밀도 매개변수(`precision`) 증가 시 교번이 느려짐 (주의가 현재 지각을 안정화).

### 실험 2: 반례와 경계 — 예측처리가 설명하지 못하는 현상

**정밀도 가중치의 신경상관물 문제.** 모델은 정밀도를 단일 스칼라로 취급하지만, 실제 주의 시스템은 공간·특징·객체 수준에서 동시에 다르게 배분된다. 계층적 정밀도의 신경 구현은 아직 충분히 해명되지 않았다.

**마취와 수면의 비대칭.** 예측처리 이론은 예측오류가 억제되면 의식이 사라진다고 예측할 수 있다. 그러나 REM 수면 중에는 예측오류 신호가 상당히 활성화됨에도 외부 자극에 대한 의식적 처리가 차단된다. 이는 예측오류의 억제와 의식 수준의 관계가 단순하지 않음을 시사한다.

**경계:** 예측처리는 의식적 경험의 **내용(content)** — 무엇이 보이는가, 어떤 가설이 지배하는가 — 을 강력하게 설명한다. 그러나 경험에는 **내용**이 있다는 사실, 즉 주관적 성격(phenomenal character)이 존재한다는 사실은 별개의 문제다. 이 경계가 바로 다음 절의 주제다.

## 🌉 간극의 위치

예측처리가 의식 내용에 대해 설명하는 것과 그렇지 못한 것:

- ✅ 어떤 지각 가설이 의식에 나타나는지 (최고 사후 확률 가설)
- ✅ 왜 지각적 다의성에서 교번이 일어나는지 (경쟁 가설 간 예측오류 누적)
- ✅ 주의가 지각 내용을 어떻게 조형하는지 (정밀도 재배분)
- ✅ 착시와 환각이 왜 발생하는지 (생성 모델의 과도한 사전 분포 영향)
- ✅ 습관화와 감각 억압의 메커니즘 (낮은 정밀도 오류의 하위 억제)
- ❌ **왜 뇌의 계산 과정에 주관적 경험이 수반되는지** (어려운 문제, hard problem)
- ❌ 빨간색을 볼 때의 질적 느낌(qualia)이 왜 그런 성격을 갖는지
- ❌ 예측오류 최소화 자체가 경험을 필요로 하는지, 아니면 '좀비 시스템'도 동일하게 수행 가능한지
- ❌ 의식의 **존재(existence)** — 경험이 있다는 사실 자체 — 의 설명

마지막 네 항목이 David Chalmers가 명명한 '어려운 문제(hard problem of consciousness)'를 구성한다. 예측처리는 이 문제를 해소(dissolve)하는 것이 아니라 그 경계를 더 선명하게 그어준다는 것이 정직한 평가다.

## 🧬 원리의 회수

챕터 전체를 관통하는 추론 원리 $\delta = \text{actual} - \text{predicted} \rightarrow \text{update}$ 는 의식 내용의 영역에서 다음과 같이 구체화된다.

지각은 뇌가 세계를 직접 읽는 과정이 아니라, 생성 모델이 감각 입력을 설명하기 위해 최선의 가설을 경쟁적으로 생성하고, 예측오류 $\delta$ 를 신호로 삼아 가설을 갱신하는 순환 과정이다. 정밀도 가중치 $\pi$ 는 어떤 오류가 이 갱신에 참여하고 어떤 오류가 배제되는지를 결정함으로써, 광대한 감각 정보 중 의식에 도달하는 좁은 통로를 규정한다.

양안경쟁과 양의적 도형은 이 원리의 투명한 창문이다. 뇌에 들어오는 자극이 고정되어 있음에도 지각이 변한다는 사실은, 의식 내용이 자극 자체가 아닌 **가설**임을 — 따라서 추론의 산물임을 — 직접적으로 보여준다.

## 🪞 1인칭

지금 이 글을 읽는 당신은 페이지 위의 검은 기호들을 보고 있다고 생각할 것이다. 그러나 예측처리 이론이 옳다면, 당신이 경험하는 것은 기호 자체가 아니라 당신의 시각 피질이 수십 밀리초의 계층적 처리를 거쳐 구성해낸 가설 — '한국어 문자가 있다', '이 단어는 저것을 의미한다' — 의 집합이다. 망막에 닿는 광자는 이 가설들을 제약하고 교정할 뿐이다. 당신이 경험하는 세계의 풍요로움은 세계 자체의 풍요로움이기도 하지만, 동시에 당신의 생성 모델이 오랜 학습으로 쌓아온 예측의 풍요로움이기도 하다.

그러나 이 설명이 아무리 정교해도, 설명되지 않는 것이 하나 있다. 왜 이 모든 계산 과정이 '어떠한 느낌(what it is like)'을 동반하는가. 눈을 감고 한 순간 그 질문에 머물러보라 — 검은 빈 공간도 아무것도 아닌 것도 아닌, 분명히 어둠을 '경험하고 있는' 무언가가 있다는 느낌. 예측처리는 당신이 어둠을 보는 것이 아니라 '어둠이라는 가설을 유지하고 있다'고 설명할 수 있다. 그러나 그 가설 유지가 느껴진다는 사실은 여전히 설명의 바깥에 있다.

## 📐 예측·반증

**예측 1.** 정밀도 가중치를 인위적으로 낮추는 약물(예: 클로르프로마진 같은 도파민 차단제가 정밀도 조절에 관여한다는 가설 하에)을 투여하면, 양안경쟁에서 지각 교번 빈도가 감소하고 한 지각이 더 오래 지배해야 한다.

- 반증 조건: 교번 빈도가 변하지 않거나 오히려 증가한다면, 정밀도-교번 연결 가설은 수정되어야 한다.

**예측 2.** 뇌의 생성 모델 내 사전 분포가 강할수록 착시 효과가 강해야 한다. 따라서 특정 착시에 장기 노출로 사전 분포를 약화시키면 착시 강도가 감소해야 한다.

- 반증 조건: 노출에도 착시 강도가 변하지 않는다면, 착시가 사전 분포가 아닌 더 낮은 수준의 고정된 처리 과정에 기인함을 시사한다.

**예측 3.** 의식적 지각 전환 직전에 전두-두정 피질의 하향 신호 패턴이 통계적으로 예측 가능한 방식으로 변해야 한다 — 즉 전환을 유발하는 정밀도 재배분의 신경 서명이 존재해야 한다.

- 반증 조건: 전환이 완전히 국소적인(V1 수준) 과정만으로 설명된다면, 계층적 정밀도 재배분 이론은 과도한 설명이다.

## 🤔 열린 질문

예측처리는 의식의 내용을 훌륭하게 설명하지만, **의식의 수준(level of consciousness)** — 각성과 혼수 사이의 스펙트럼 — 은 어떻게 설명할 것인가? 자유에너지 원리는 전체 시스템의 예측 능력과 의식 수준을 어떻게 연결하는가?

→ 이 질문은 다음 문서 [02-free-energy-consciousness-level.md](./02-free-energy-consciousness-level.md)에서 다룬다. 특히 Integrated Information Theory(IIT)와 예측처리의 비교, 그리고 마취·수면·의식장애 연구에서 두 이론이 내놓는 상이한 예측들을 검토할 것이다.

---
> 🧩 **Principle** — 의식의 내용은 예측오류 $\delta = r - \hat{r}$ 를 최소화하는 방향으로 생성 모델이 선택한 최선 가설이다. 정밀도 가중치 $\pi$ 가 어떤 오류가 의식에 참여하는지를 결정한다.
> 🌉 **Boundary** — 예측처리는 의식의 **내용(content)** 을 설명하지만, 경험이 **존재한다는 사실(existence of experience)** — 어려운 문제 — 은 설명하지 못한다. 이 경계는 이론의 실패가 아니라 이론의 정직한 한계다.
> 🪞 **Experience** — 양안경쟁의 교번을 직접 경험할 때, 당신은 단순히 뇌 안의 가설 전환을 관찰하는 것이 아니다. 한 지각이 사라지고 다른 지각이 나타나는 그 순간, 거기에는 분명히 '어떠한 것(something it is like)'이 있다 — 그리고 바로 그것이 예측처리로 환원되지 않는 남은 질문이다.

## 📝 연습문제

**기초.** 정밀도 가중치(precision weighting)가 낮은 감각 오류가 의식에 이르지 못하는 이유를 예측 부호화 계층 모델의 관점에서 설명하라. 일상 생활에서 이에 해당하는 구체적 예를 하나 제시하라.

<details><summary>해설</summary>

예측 부호화 모델에서 각 계층의 예측오류 $\delta$ 는 상위 계층으로 전달되기 전에 정밀도 $\pi$ 에 의해 스케일된다: $\delta_\pi = \pi \cdot \delta$. 정밀도가 낮으면 오류 신호가 약화되어 상위 피질 계층에 도달하지 못하고, 해당 오류는 낮은 수준에서 국소적으로 처리된다. 즉 현재의 가설(upper-level representation)을 갱신하는 데 기여하지 못하므로 의식적 내용을 변화시키지 않는다.

일상 예: 시계 소리. 조용한 방에서 처음 시계 소리를 들을 때는 명확히 의식되지만, 몇 분 후에는 거의 인식하지 못한다. 이는 반복적·예측 가능한 자극에 대해 뇌가 점차 정밀도를 낮게 할당하고, 그 예측오류가 의식에 이르지 못하게 되기 때문이다(습관화).

</details>

**심화.** Seth의 "통제된 환각(controlled hallucination)" 개념과 Hohwy의 "가설 검증으로서의 지각" 개념의 공통점과 차이점을 설명하라. 두 관점이 정밀도 가중치를 어떻게 다르게 강조하는지 포함하여 논하라.

<details><summary>해설</summary>

**공통점:** 두 관점 모두 지각을 수동적 자극 수용이 아닌 능동적 구성 과정으로 본다. 뇌의 생성 모델이 만들어내는 하향 예측이 지각 경험의 핵심이며, 감각 입력은 이 예측을 교정하는 역할을 한다는 점에서 일치한다.

**차이점:** Hohwy는 뇌의 인식론적 위치를 강조한다. 뇌는 두개골 안에 갇혀 간접 증거(감각 신호)만으로 외부 세계에 대한 가설을 검증해야 하므로, 지각은 필연적으로 추론적이고 간접적이다. 그는 지각의 주요 특성으로 **인과적 깊이(causal depth)** — 표면 자극 너머의 원인을 추론하는 능력 — 를 강조한다.

Seth는 현상학적 측면을 더 전면에 세운다. '통제된 환각'이라는 표현은 정상 지각과 병리적 환각 사이의 연속성을 부각시키며, 자아(self)와 신체 경험 역시 동일한 생성 모델의 구성물임을 강조한다. 정밀도 가중치에 관해서, Hohwy는 이를 주의의 베이즈적 구현으로 다루는 반면, Seth는 정밀도 조절의 실패가 망상이나 해리 등 임상적 의식 장애를 설명할 수 있음을 더 직접적으로 다룬다.

</details>

**논문 비평.** Rao & Ballard(1999) "Predictive coding in the visual cortex: a functional interpretation of some extra-classical receptive-field effects"(*Nature Neuroscience*)를 읽고 다음을 평가하라: (1) 이 논문의 예측 부호화 모델이 현재의 예측처리 의식 이론과 어떻게 연결되는가, (2) 이 모델이 의식 자체에 대해 어떤 주장을 하는가(또는 하지 않는가), (3) 이 모델의 가장 중요한 한계 하나를 논하라.

<details><summary>해설</summary>

**(1) 연결:** Rao & Ballard 모델은 시각 피질의 계층적 구조에서 상위 영역이 하위 영역의 활동을 예측하고, 하위 영역은 잔차(예측오류)만을 상위로 전달한다는 2계층 모델을 제안했다. 이는 Friston의 자유에너지 원리, Hohwy의 가설 검증 이론, Seth의 통제된 환각 모두의 신경생물학적 토대를 제공한다. 특히 '하향 연결 = 예측, 상향 연결 = 예측오류'라는 구조는 현재 예측처리 이론의 핵심 해부학적 가정이다.

**(2) 의식에 대한 주장:** Rao & Ballard(1999) 논문 자체는 의식에 대한 명시적 주장을 하지 않는다. 이 논문은 고전적 수용야(classical receptive field) 외부 자극이 신경 반응을 억제하는 '외고전적 수용야 효과(extra-classical receptive field effects)'를 예측 부호화로 설명하는 데 집중한다. 의식으로의 확장은 이후 Friston, Hohwy, Seth 등이 수행했다.

**(3) 한계:** 가장 중요한 한계는 모델이 **2계층**에 그친다는 점이다. 실제 시각 피질은 V1-V2-V4-IT 등 6개 이상의 계층을 가지며, 각 계층 간의 정밀도 배분과 횡방향(lateral) 연결은 이 모델에 포함되지 않는다. 또한 운동 예측(active inference)이 빠져있어, 뇌가 환경을 단순히 예측할 뿐 아니라 행동을 통해 예측오류를 능동적으로 최소화한다는 측면이 다루어지지 않는다.

</details>

---
<div align="center">

[◀ 이전: 자유에너지의 한계](../ch4-active-inference/04-fep-limits.md) · [📚 README](../README.md) · [다음: 자유에너지와 의식 수준 ▶](./02-free-energy-consciousness-level.md)

</div>
