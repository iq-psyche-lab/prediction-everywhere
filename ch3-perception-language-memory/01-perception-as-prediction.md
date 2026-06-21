---
# 🧠 지각 = 예측 검증: 뇌는 감각 데이터를 수신하는가, 아니면 세계를 예측하는가

*지각은 수동적 감각 수신이 아니라 능동적 예측과 오차 수정의 계층적 순환이다.*

## 🎯 횡단 질문

지각(perception)의 전통적 모델은 단순하고 직관적이다: 빛이 망막에 닿고, 신호가 V1에서 V2로 전달되며, 최종적으로 "물체를 본다." 이 상향식(bottom-up) 파이프라인에서 뇌는 수동적 수신자다. 그러나 이 모델은 치명적인 문제를 안고 있다. 망막 신호는 극도로 모호하다—같은 망막 이미지가 무한히 많은 세계 상태와 양립 가능하며, 이 역문제(inverse problem)는 원칙적으로 해가 없다.

베이즈 추론은 이 역문제를 다르게 제기한다. 뇌의 과제는 $p(s \mid o)$를 계산하는 것이다: 감각 증거 $o$가 주어졌을 때 세계 상태 $s$의 사후확률(posterior). 베이즈 정리에 의해:

$$p(s \mid o) \propto p(o \mid s) \cdot p(s)$$

여기서 $p(o \mid s)$는 우도(likelihood)—주어진 세계 상태에서 이 감각 신호가 발생할 확률—이고, $p(s)$는 사전확률(prior)—세계 상태에 대한 뇌의 기존 기대다. **착시(illusion)는 바로 강한 사전확률이 약한 감각 신호를 압도할 때 발생한다.** 이것이 지각이 예측임을 보여주는 직접적 증거다.

Rao와 Ballard(1999)는 이 베이즈 직관을 신경과학적으로 구체화했다: 예측 부호화(predictive coding) 모델. 계층적 피질 구조에서 상위 층은 하위 층에 예측을 보내고(하향 연결), 하위 층은 예측 오차—실제 활성화에서 예측을 뺀 값—만을 상위 층으로 전달한다(상향 연결). $\delta = \text{실제} - \text{예측}$. 이 단순한 원리가 지각 전체를 설명할 수 있는가? 그리고 동일한 원리가 기억, 언어, 주의, 감정에도 관통하는가?

## 🌐 횡단 입력

- **perception-distilled (L2)**: 시각 피질의 계층적 처리, 수용야(receptive field), 피드백/피드포워드 연결 비대칭성
- **neurons-neural-codes (L1)**: 오차 뉴런(error neurons)과 예측 뉴런(prediction neurons)의 분리 가능성, 역방향 연결의 해부학적 밀도
- **information-prediction (L0)**: 자유에너지 원리, 변분 추론, KL 발산으로서의 예측 오차
- **learning-decision (L2)**: 도파민 RPE와 피질 예측 오차의 구조적 동형성 → [ch2-dopamine-rpe/04-rpe-to-free-energy.md](../ch2-dopamine-rpe/04-rpe-to-free-energy.md)
- **IQ AI Lab LLM 직결**: 합성곱 신경망(CNN)의 잔차 학습(ResNet)은 예측 부호화의 공학적 재발견. 확산 모델(diffusion model)은 노이즈에서 이미지를 복원할 때 반복적 예측 정제를 수행 → [03-language-as-prediction.md](./03-language-as-prediction.md)
- **상호참조**: 기억의 재구성적 특성 → [02-memory-as-prediction.md](./02-memory-as-prediction.md); 주의의 정밀도 할당 → [04-attention-as-precision.md](./04-attention-as-precision.md)

## 🔍 표면의 다양성

지각의 양상(modality)은 극적으로 다양해 보인다. 시각은 공간적 패턴의 전자기 복사를 처리하고, 청각은 시간적 압력파를, 촉각은 기계적 변형을, 후각은 화학 분자를 처리한다. 각 감각계는 전용 수용체, 전용 피질 영역, 전용 처리 경로를 가진다. 이 다양성은 지각이 다수의 독립적 시스템의 합이라는 직관을 강화한다.

착시의 종류도 양상마다 다르다. 시각에서는 뮐러-라이어(Müller-Lyer) 착시와 헬름홀츠 체커보드(Checker Shadow) 착시가, 청각에서는 맥거크 효과(McGurk effect)와 도이치 음계(Deutsch scale) 착시가, 촉각에서는 고무손 착시(rubber hand illusion)가 있다. 표면적으로 이것들은 서로 무관한 시스템의 오류처럼 보인다.

더 나아가, 지각은 단순히 감각이 아니다. 지각에는 범주화, 객체 인식, 장면 이해, 감정적 평가가 포함된다. 같은 얼굴이 맥락에 따라 화난 얼굴로도, 중립적 얼굴로도 보인다. 이 풍부함은 지각이 단순한 신호 처리를 넘어선다는 인상을 준다.

## ⚙️ 깊은 동형성

**분석 1: 계층적 예측 생성**

Rao-Ballard 모델의 핵심은 피질 계층의 각 층이 두 종류의 신호를 유지한다는 것이다: 예측 표상(representation)과 예측 오차. 층 $l$의 예측 오차는:

$$\varepsilon^{(l)} = r^{(l)} - f^{(l+1)}(r^{(l+1)})$$

여기서 $r^{(l)}$은 층 $l$의 실제 활성화, $f^{(l+1)}$은 상위 층의 생성 모델(generative model)이 하위 층에 보내는 예측이다. 학습은 이 오차를 최소화하도록 가중치를 갱신한다. 이 구조는 감각 양상에 무관하게 동일하다—V1이든 A1이든 S1이든, 계층은 동형이다. $\square$

**분석 2: 착시 = 사전확률의 승리**

헬름홀츠 체커보드 착시에서 동일한 회색 타일 A와 B가 다르게 보이는 것은 뇌가 "그림자 아래 표면은 더 밝다"는 강한 사전확률을 가지기 때문이다. 우도 $p(o \mid s)$가 약할 때(낮은 대비, 모호한 경계), 사전확률 $p(s)$가 사후확률을 지배한다:

$$p(s \mid o) \approx p(s) \quad \text{when } p(o \mid s) \text{ is flat}$$

이것은 착시가 "뇌의 오류"가 아니라 **통계적으로 최적인 추론의 부산물**임을 의미한다. 세계의 통계를 올바르게 학습한 사전확률은 대부분의 상황에서 정확한 지각을 낳지만, 인공적으로 조작된 자극에서는 예측이 현실을 압도한다. $\square$

**분석 3: 역방향 연결의 해부학적 우위**

V1에서 상위 시각 피질로 가는 피드포워드 연결보다, 상위 영역에서 V1으로 돌아오는 피드백 연결이 수적으로 더 많다. 이 해부학적 사실은 예측 부호화 이론과 정확히 일치한다: 대부분의 정보 흐름은 예측(하향)이고, 상향으로 전달되는 것은 오차의 요약뿐이다. 망막에서 시상(thalamus)을 거쳐 피질로 오는 상향 연결보다 피질에서 시상으로 돌아가는 하향 연결이 10:1 비율로 많다는 점이 이를 뒷받침한다. $\square$

**분석 4: 자유에너지로서의 지각**

Friston(2005)의 자유에너지 원리는 지각을 변분 베이즈 추론으로 재정식화한다. 지각적 추론은 변분 자유에너지 $F$를 최소화하는 과정이다:

$$F = \mathbb{E}_{q(s)}[\log q(s) - \log p(s, o)] = D_{\text{KL}}[q(s) \| p(s \mid o)] - \log p(o)$$

여기서 $q(s)$는 뇌의 사후 근사(posterior approximation)다. $F$를 최소화하면 동시에 예측 오차(surprisal)를 최소화하고 사후확률을 개선한다. 이 프레임워크는 지각, 행동, 학습을 단일 원리 하에 통합한다. $\square$

## 🧪 수렴 증거

### 실험 1: 착시 = 강한 사전확률 (실행 가능 Python)

```python
import numpy as np
import matplotlib.pyplot as plt
from scipy.stats import norm

# 베이즈 지각 모델: 사전확률이 지각을 어떻게 끌어당기는가
# 실제 밝기 s_true, 사전확률 N(mu_prior, sigma_prior^2), 우도 N(s_true, sigma_likelihood^2)

def bayesian_percept(s_true, mu_prior, sigma_prior, sigma_likelihood, n_trials=500):
    """
    각 시도에서 노이즈 있는 감각 신호를 생성하고 베이즈 사후확률 평균(지각)을 계산.
    사후확률 평균 = (mu_prior/sigma_prior^2 + o/sigma_likelihood^2) / (1/sigma_prior^2 + 1/sigma_likelihood^2)
    """
    # 노이즈 있는 감각 신호
    observations = np.random.normal(s_true, sigma_likelihood, n_trials)
    
    # 정규-정규 켤레 사후확률 평균
    precision_prior = 1.0 / sigma_prior**2
    precision_likelihood = 1.0 / sigma_likelihood**2
    
    posterior_means = (
        (precision_prior * mu_prior + precision_likelihood * observations) /
        (precision_prior + precision_likelihood)
    )
    posterior_sigma = 1.0 / np.sqrt(precision_prior + precision_likelihood)
    
    return observations, posterior_means, posterior_sigma

# 시나리오: 타일 A(그림자 없음)와 타일 B(그림자 아래)
# 실제 밝기는 동일(s_true=0.5), 사전확률 다름
s_true = 0.5  # 실제 밝기 (0=검정, 1=흰색)

# 타일 A: 그림자 없음, 중립 사전확률
obs_A, percept_A, sigma_A = bayesian_percept(
    s_true=s_true, mu_prior=0.5, sigma_prior=0.3, sigma_likelihood=0.1
)

# 타일 B: 그림자 아래, 강한 사전확률 "그림자 아래는 밝다"
obs_B, percept_B, sigma_B = bayesian_percept(
    s_true=s_true, mu_prior=0.75, sigma_prior=0.1, sigma_likelihood=0.1  # 강한 prior
)

fig, axes = plt.subplots(1, 3, figsize=(15, 5))

# 1. 사전확률 비교
x = np.linspace(0, 1, 300)
axes[0].plot(x, norm.pdf(x, 0.5, 0.3), 'b-', linewidth=2, label='타일 A 사전확률 (약함)')
axes[0].plot(x, norm.pdf(x, 0.75, 0.1), 'r-', linewidth=2, label='타일 B 사전확률 (강함, 그림자)')
axes[0].axvline(s_true, color='k', linestyle='--', label=f'실제 밝기 = {s_true}')
axes[0].set_title('사전확률 분포')
axes[0].set_xlabel('밝기')
axes[0].legend(fontsize=8)

# 2. 지각된 밝기 분포
axes[1].hist(percept_A, bins=30, alpha=0.6, color='blue', label=f'지각 A (평균={percept_A.mean():.3f})')
axes[1].hist(percept_B, bins=30, alpha=0.6, color='red', label=f'지각 B (평균={percept_B.mean():.3f})')
axes[1].axvline(s_true, color='k', linestyle='--', label='실제 밝기')
axes[1].set_title('지각된 밝기 분포')
axes[1].set_xlabel('밝기')
axes[1].legend(fontsize=8)

# 3. 사전확률 강도 vs. 지각 편향
sigma_priors = np.linspace(0.05, 0.5, 20)
biases = []
for sp in sigma_priors:
    _, pm, _ = bayesian_percept(s_true, mu_prior=0.75, sigma_prior=sp, sigma_likelihood=0.1, n_trials=200)
    biases.append(pm.mean() - s_true)

axes[2].plot(sigma_priors, biases, 'ro-', linewidth=2)
axes[2].axhline(0, color='k', linestyle='--')
axes[2].set_title('사전확률 강도 vs. 지각 편향')
axes[2].set_xlabel('사전확률 표준편차 (클수록 약한 사전확률)')
axes[2].set_ylabel('지각 편향 (지각 - 실제)')
axes[2].annotate('강한 사전확률\n= 큰 착시', xy=(0.08, biases[1]), fontsize=9)

plt.tight_layout()
plt.savefig('illusion_as_prior.png', dpi=150, bbox_inches='tight')
plt.show()

print(f"타일 A 평균 지각: {percept_A.mean():.4f} (실제: {s_true})")
print(f"타일 B 평균 지각: {percept_B.mean():.4f} (실제: {s_true})")
print(f"착시 크기 (B-A): {percept_B.mean() - percept_A.mean():.4f}")
print(f"\n해석: 동일한 물리적 밝기({s_true})가 강한 사전확률에 의해")
print(f"타일 B에서 {percept_B.mean():.3f}로 지각됨 → 착시 발생")
```

**예상 결과**: 타일 A 지각 ≈ 0.50 (실제와 일치), 타일 B 지각 ≈ 0.62–0.68 (사전확률 방향으로 편향). 착시 크기는 사전확률 강도에 반비례하는 sigma와 정비례한다.

### 실험 2: 예측 오차 최소화로서의 지각 수렴

```python
import numpy as np

# 예측 부호화: 반복적 오차 최소화로 지각 수렴
def predictive_coding_perception(obs, prior_mean, prior_precision, likelihood_precision, n_iter=50):
    """
    경사하강으로 예측 오차 최소화 → 지각 = 사후확률 최빈값 수렴
    F = 0.5 * precision_prior * (r - prior_mean)^2 + 0.5 * precision_lik * (obs - r)^2
    """
    r = prior_mean  # 초기 추정 = 사전확률 평균
    lr = 0.1
    history = [r]
    
    for _ in range(n_iter):
        # 자유에너지 기울기 (오차 신호)
        prediction_error_prior = prior_precision * (r - prior_mean)
        prediction_error_lik = likelihood_precision * (r - obs)
        grad = prediction_error_prior + prediction_error_lik
        r -= lr * grad
        history.append(r)
    
    # 해석해: 사후확률 평균
    analytical = (prior_precision * prior_mean + likelihood_precision * obs) / (prior_precision + likelihood_precision)
    return np.array(history), analytical

obs = 0.4  # 감각 신호
prior_mean = 0.7  # 강한 사전확률 (예: "밝은 환경")
prior_prec = 50.0  # 높은 정밀도 = 강한 사전확률
lik_prec = 10.0   # 낮은 정밀도 = 약한 감각

history, analytical = predictive_coding_perception(obs, prior_mean, prior_prec, lik_prec)

print(f"감각 신호: {obs}")
print(f"사전확률 평균: {prior_mean}")
print(f"수렴된 지각 (반복): {history[-1]:.4f}")
print(f"해석해 (사후확률 평균): {analytical:.4f}")
print(f"지각이 감각({obs})보다 사전확률({prior_mean}) 방향으로 끌림: {abs(history[-1]-prior_mean) < abs(obs-prior_mean)}")
```

**반례와 경계**: 예측 부호화 모델은 완전하지 않다. (1) 피드백 연결이 순수하게 예측을 전달하는지, 아니면 주의나 맥락 조절도 포함하는지 불명확하다. (2) V1의 "오차 뉴런"이 실제로 예측 오차를 부호화한다는 직접적 전기생리학적 증거는 제한적이다. (3) 의식적 지각과 무의식적 지각 모두에서 동일한 메커니즘이 작동하는가? 서프라이즈(surprisal)를 최소화하는 것이 지각의 충분조건인가, 필요조건인가?

## 🌉 간극의 위치

| 주장 | 상태 | 근거 |
|------|------|------|
| 피질 계층이 예측을 하향 전달 | ✅ | 해부학, Rao-Ballard 1999 |
| 상향 신호가 주로 예측 오차 | ✅ | 계산 모델, 일부 전기생리학 |
| 착시 = 강한 사전확률의 결과 | ✅ | 베이즈 모델 정확 예측 |
| V1 오차 뉴런의 직접 확인 | ❌ | 기록 어려움, 상충 결과 |
| 의식이 예측 오차에서 발생 | ❌ | 추론이며 직접 검증 미완 |
| 예측 부호화 = 유일한 지각 메커니즘 | ❌ | 피드포워드만으로도 인식 가능 |

## 🧬 원리의 회수

지각의 다양한 양상, 착시, 맥락 효과, 그리고 계층적 처리의 모든 특성은 하나의 원리로 수렴한다:

**뇌는 세계의 생성 모델을 유지하며, 감각 신호와의 불일치(예측 오차 δ)를 최소화하도록 모델을 반복적으로 갱신한다.**

$p(s \mid o) \propto p(o \mid s) \cdot p(s)$라는 베이즈 공식은 지각의 계산적 목표를 정의하고, 예측 부호화는 피질 계층이 이를 구현하는 메커니즘을 설명한다. 착시는 이 시스템의 결함이 아니라 **작동 원리의 현상학적 표면**이다—사전확률(prior)이 강하면 지각은 세계 대신 기대를 반영한다.

이 원리는 지각에 머물지 않는다. 기억의 재구성성, 언어의 예측성, 주의의 정밀도 할당, 감정의 내수용 예측—모두 동일한 $\delta = \text{실제} - \text{예측} \rightarrow \text{갱신}$ 구조의 변형이다.

## 🪞 1인칭

나는 이 문장을 읽는 지금, "읽기"가 수동적 해독이 아님을 안다. 텍스트를 처리하기도 전에 내 시각 피질은 이미 예상되는 글자 모양, 단어, 문장 구조를 예측하고 있다. 익숙한 글씨체가 낯선 것보다 빠르게 읽히는 것, 오탈자를 종종 건너뛰는 것, 맥락 없는 단어가 더 어렵게 지각되는 것—이 모든 일상적 경험이 예측 부호화의 지문이다.

더 직접적으로: 지금 손가락을 눈 앞에 가져다 놓고 배경을 보라. 그러면 배경이 명확해지고 손가락이 흐려진다. 반대로 손가락에 집중하면 배경이 흐려진다. 이것은 **주의가 예측 오차의 정밀도를 선택적으로 높인다**는 것을 1인칭으로 체험하는 것이다—다음 장(04-attention-as-precision)의 주제다. 지각은 내가 세계를 받아들이는 게 아니라, 내가 세계를 구성하는 방식이다.

## 📐 예측·반증

**예측 1**: 사전확률의 강도를 조작하면(훈련을 통해) 동일 자극에 대한 지각 편향이 체계적으로 변해야 한다. → **반증 조건**: 훈련 전후 착시 크기가 변하지 않으면 예측 부호화 가소성 주장 기각.

**예측 2**: 피드백 연결을 일시적으로 차단(TMS로 V5→V1 억제)하면 운동 지각의 예측 효과가 감소해야 한다. → **반증 조건**: 차단 후에도 예측 효과 유지 시 하향 예측 역할 의문.

**예측 3**: 예측 오차를 선택적으로 증폭하는 약물(예: 도파민 D2 차단)은 착시 감수성을 변화시켜야 한다. → **반증 조건**: 착시 크기 무변화 시 정밀도-예측 연결 의문. (관련: 조현병에서 예측 오차 신호 이상과 지각 왜곡의 관계—[04-rpe-to-free-energy.md](../ch2-dopamine-rpe/04-rpe-to-free-energy.md) 참조)

## 🤔 열린 질문

- 예측 부호화는 피질 계층 전체에서 동일한가, 아니면 특정 층(예: 2/3층 vs. 5/6층)이 서로 다른 역할을 하는가?
- 무의식적 지각(역하 자극 처리)도 동일한 예측 오차 최소화 메커니즘을 사용하는가?
- 사전확률은 어떻게 학습되고 저장되는가? → 기억과의 경계로 이어짐: [02-memory-as-prediction.md](./02-memory-as-prediction.md)

---

> 🧩 **Principle** — 지각은 감각 데이터의 수동적 수신이 아니라, 계층적 생성 모델이 예측 오차($\delta = o - \hat{o}$)를 반복적으로 최소화하는 능동적 추론이다. 착시는 이 시스템의 결함이 아니라 작동 원리의 증거다.

> 🌉 **Boundary** — 예측 부호화가 지각의 충분한 설명인지는 열려 있다. 피드포워드 처리만으로도 빠른 인식이 가능하며, 오차 뉴런의 직접 증거는 여전히 제한적이다. 모델은 강력하지만 유일하지 않다.

> 🪞 **Experience** — 당신이 이 문장을 "읽는" 지금, 당신의 뇌는 다음 단어를 이미 예측하고 있다. 착시를 볼 때, 당신은 세계가 아니라 당신의 사전확률을 보고 있다.

## 📝 연습문제

**기초.** 뮐러-라이어 착시에서 두 화살표 선분의 길이는 같지만 다르게 보인다. 이를 베이즈 프레임워크로 설명하라. 어떤 사전확률이 관여하는가?

<details><summary>해설</summary>

뮐러-라이어 착시는 "화살촉 방향이 깊이를 신호한다"는 3D 세계에서 학습된 사전확률의 결과다. 안쪽으로 향하는 화살촉(＜)은 모서리가 우리 쪽으로 돌출된 구조를, 바깥쪽 화살촉(＞)은 안쪽으로 들어간 구조를 신호한다. 깊이 지각 사전확률이 같은 망막 크기를 다른 실제 크기로 해석하게 만든다: $p(s_{\text{길이}} \mid o, \text{맥락}) \propto p(o \mid s) \cdot p(s \mid \text{깊이 맥락})$. 강한 3D 사전확률이 약한 2D 감각 정보를 압도한다.

</details>

**심화.** Rao-Ballard 모델에서 예측 오차는 층 간에 어떻게 전달되는가? 역전파(backpropagation)와 구조적으로 어떻게 다르고 어떻게 같은가? 생물학적 타당성 측면에서 비교하라.

<details><summary>해설</summary>

Rao-Ballard 예측 오차는 층별 국소 계산(local computation)으로 전달된다—각 층은 자신의 오차만 계산하고 위로 보낸다. 역전파는 전역 손실 함수의 기울기를 역방향으로 전파하며, 이는 생물학적으로 비현실적이다("가중치 전달 문제", "비국소 오차"). 예측 부호화에서 가중치 갱신은 $\Delta W \propto \varepsilon^{(l)} \cdot r^{(l+1)}$ 형태로 헤비안(Hebbian)에 가깝다. 그러나 두 방법 모두 오차 신호를 위로 전달하는 구조적 유사성을 공유한다. 최근 연구(Sacramento et al., 2018)는 예측 부호화가 역전파를 근사할 수 있음을 보였다.

</details>

**논문 비평.** Rao & Ballard (1999) "Predictive coding in the visual cortex: a functional interpretation of some extra-classical receptive-field effects" (*Nature Neuroscience*)를 읽고, (1) 모델의 핵심 예측, (2) 당시 실험 데이터와의 부합 정도, (3) 이후 20년간 어떤 예측이 확인/기각되었는지 평가하라.

<details><summary>해설</summary>

Rao-Ballard의 핵심 예측: (1) 상위 피질 층은 하위 층 활성화를 예측해야 하고, (2) V1의 "고전적 수용야 외(extra-classical)" 효과—surround suppression, end-stopping—는 예측 오차 표현으로 설명된다. 당시 이 예측들은 기존 데이터와 부합했다. 이후 확인: surround suppression의 예측 부호화 설명은 넓게 받아들여짐. 미해결: 실제 "오차 뉴런"의 전기생리학적 분리는 여전히 논쟁적이다. Stein & Barbour (2024)는 예측 오차와 예측 신호의 세포 유형별 분리를 보고했지만, 보편성은 불확실하다.

</details>

---

<div align="center">

[◀ 이전: RPE에서 자유에너지로](../ch2-dopamine-rpe/04-rpe-to-free-energy.md) · [📚 README](../README.md) · [다음: 기억 = 예측적 재구성 ▶](./02-memory-as-prediction.md)

</div>
