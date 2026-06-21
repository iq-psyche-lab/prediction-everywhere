# 🧠 언어 = 예측 기계: 인간 언어 이해와 LLM은 같은 원리인가

*언어 이해는 다음 단어의 확률적 예측이며, 인간 뇌와 대형 언어 모델은 이 예측 원리의 두 가지 구현이다—공유하는 것과 분기하는 지점이 있다.*

## 🎯 횡단 질문

"그녀는 피아노를 __"라는 문장을 읽을 때, 당신의 뇌는 빈칸에 "연주했다"가 올 것을 이미 예측하고 있다. "먹었다"가 온다면 놀라고(surprise), "연주했다"가 온다면 놀라지 않는다. 이 직관적 현상의 신경과학적 지문이 바로 **N400** 성분이다—Kutas & Hillyard(1980)가 발견한, 의미적으로 부적절한 단어에 대한 음전위(negative ERP component). N400의 진폭은 단어의 맥락적 예측 가능성(cloze probability)에 반비례한다. 뇌가 단어를 예측하고, 예측이 빗나갈수록 더 큰 신경 반응을 보인다.

이것은 언어학자 Noam Chomsky의 생성 문법(generative grammar)과 대립하는 관점이다. Chomsky는 언어를 규칙 기반 계층 구조로 보고, 통계적 패턴은 언어의 본질이 아니라고 주장했다. 그러나 신경언어학의 증거는 다른 방향을 가리킨다: 인간 언어 처리는 깊이 확률적이며, 예측적이다. 그리고 대형 언어 모델(LLM)—GPT, Claude, Llama—은 정확히 이 원리, 즉 $\max p(w_t \mid w_{<t})$로 다음 토큰을 예측하도록 훈련된다.

질문은 날카롭다: **인간의 언어 이해와 LLM의 다음 토큰 예측은 같은 것인가, 아니면 표면적 유사성이 깊은 차이를 숨기는가?** 이 질문은 IQ AI Lab의 핵심 관심사와 직결된다—LLM이 "이해"하는가, 아니면 단순히 패턴을 예측하는가?

## 🌐 횡단 입력

- **perception-distilled (L2)**: 언어 이해는 시각 지각처럼 하향 예측과 상향 오차의 계층적 처리 → [01-perception-as-prediction.md](./01-perception-as-prediction.md)
- **neurons-neural-codes (L1)**: 브로카(Broca) 영역과 베르니케(Wernicke) 영역의 예측적 역할, 언어 네트워크의 계층성
- **information-prediction (L0)**: 정보 이론적 surprisal $= -\log_2 p(w_t \mid w_{<t})$; 섀넌(Shannon) 엔트로피와 언어 통계
- **learning-decision (L2)**: 언어 학습 = 통계 구조 학습. 유아의 언어 습득과 LLM 사전 훈련의 공통 원리
- **IQ AI Lab LLM 직결**: LLM의 핵심 훈련 목표 = 인간 언어 처리의 핵심 계산과의 직접적 비교. Transformer 주의 메커니즘과 인간 주의의 관계 → [04-attention-as-precision.md](./04-attention-as-precision.md)
- **상호참조**: 의미 기억의 예측적 활성화가 언어 이해의 기반 → [02-memory-as-prediction.md](./02-memory-as-prediction.md)

## 🔍 표면의 다양성

언어는 극도로 다양해 보인다. 세계에는 약 7,000개의 언어가 존재하며, 음운 체계, 형태론, 통사론, 화용론에서 엄청난 다양성을 보인다. 한국어는 SOV 어순에 조사 기반 문법, 영어는 SVO 어순에 위치 기반 문법, 다게스탄의 일부 언어는 84개의 자음을 갖는다. Sapir-Whorf 가설은 언어가 사고를 형성한다고 주장하며, 이는 언어의 다양성이 인지의 다양성을 의미한다고 시사한다.

언어 처리의 신경 기반도 복잡하다. 브로카 실어증(Broca's aphasia)은 문법 처리를 손상시키고, 베르니케 실어증(Wernicke's aphasia)은 의미 이해를 손상시킨다. 읽기, 듣기, 말하기는 부분적으로 다른 신경 경로를 사용한다. 이중 언어 화자의 두 언어는 때로 겹치고 때로 분리된 표상을 갖는다.

인간 언어와 LLM도 다르게 보인다. 인간은 몇 년의 체화된 경험으로 언어를 배우고, 지시 대상(referent)과의 물리적 접촉을 통해 의미를 습득한다. LLM은 텍스트만으로 훈련되며, 신체도, 감각도, 세계와의 직접 접촉도 없다. 인간은 단 몇 번의 예시로 새 개념을 학습(few-shot learning)하지만, LLM은 수조 개의 토큰이 필요했다.

## ⚙️ 깊은 동형성

**분석 1: Surprisal과 N400—언어 처리의 예측 오차 신호**

Surprisal은 단어 $w_t$의 정보 이론적 예측 불가능성이다:

$$S(w_t) = -\log_2 p(w_t \mid w_1, w_2, \ldots, w_{t-1})$$

N400 진폭은 cloze probability가 낮은(surprisal이 높은) 단어에서 더 크다. Demberg & Keller(2008)는 surprisal이 읽기 시간(reading time)을 예측함을 보였고, Frank & Bod(2011)는 언어 모델의 surprisal이 N400을 예측함을 확인했다. 놀라운 것은 **LLM이 계산하는 surprisal이 인간의 N400 진폭을 예측**한다는 것이다(Schrimpf et al., 2021).

이것은 인간 뇌와 LLM이 최소한 같은 *통계 구조*를 내면화하고 있음을 의미한다. 예측 오차 $\delta = w_t - \hat{w}_t$가 N400으로 나타나는 것이다. $\square$

**분석 2: 다음 토큰 예측의 놀라운 창발성**

LLM의 훈련 목표는 단순하다:

$$\mathcal{L} = -\sum_{t=1}^{T} \log p(w_t \mid w_1, \ldots, w_{t-1}; \theta)$$

그러나 이 단순한 목표에서 놀라운 능력들이 창발한다: 논리적 추론, 코드 생성, 번역, 요약, 수학 풀기, 감정 분석. 이것은 **언어 통계를 완벽하게 예측하려면 세계에 대한 광범위한 이해가 필요**하기 때문이다—언어는 세계의 압축이다. "태양은 아침에 __에서 뜬다"를 예측하려면 태양의 운동에 대한 지식이 필요하다.

Elman(1990)의 초기 순환 신경망 연구는 이미 이 원리를 보였다: 다음 단어 예측을 훈련받은 소규모 네트워크가 문법적 범주와 의미적 역할을 자발적으로 학습했다. $\square$

**분석 3: 계층적 언어 구조와 계층적 예측**

Chomsky의 문법 계층—음소→형태소→단어→구→문장→담화—은 예측의 계층으로 재해석된다. 각 수준은 다음 수준의 단위를 예측한다:

- 음소 수준: 이 음소 다음에 올 음소는? $p(\phi_{t+1} \mid \phi_1, \ldots, \phi_t)$
- 단어 수준: 이 단어 다음에 올 단어는? $p(w_{t+1} \mid w_1, \ldots, w_t)$  
- 구 수준: 이 명사구 다음에 올 동사구는? $p(\text{VP} \mid \text{NP}, \text{context})$
- 담화 수준: 이 단락 다음에 올 논증은? $p(\text{arg}_{n+1} \mid \text{arg}_1, \ldots, \text{arg}_n)$

Transformer의 다중 헤드 주의(multi-head attention)는 이 다중 수준 예측을 병렬로 수행한다. 다른 헤드들이 다른 언어적 관계(통사, 의미, 화용)에 특화된다는 증거가 있다. $\square$

**분석 4: 언어 이해에서 인간과 LLM이 갈리는 지점**

그러나 중요한 분기가 있다. 인간 언어 처리는 **조성적(compositional)**이며 **체계적(systematic)**이다: 새로운 조합을 처음 보고도 이해할 수 있다("색없는 녹색 생각이 분노하며 잔다"). LLM은 분포 외(out-of-distribution) 자극에 취약하다.

더 근본적으로: 인간의 언어 이해는 **기반(grounding)**되어 있다. "사과"는 빨갛고, 달고, 손에 잡히는 것의 감각-운동 경험과 연결된다. LLM의 "사과" 표상은 순수하게 분포적(distributional)이다—다른 단어들과의 통계적 관계. 이것이 의미론적 이해의 진정한 차이인가, 아니면 구현의 차이인가는 열린 철학적 질문이다. $\square$

## 🧪 수렴 증거

### 실험 1: Surprisal 계산과 N400 예측

```python
import numpy as np
from scipy.stats import pearsonr

# N400 진폭과 surprisal의 관계 시뮬레이션
# 실제 데이터 구조를 따른 시뮬레이션

np.random.seed(42)

# 언어 모델 surprisal과 N400 진폭의 관계
# 기반: Schrimpf et al. (2021) — LLM surprisal이 N400을 예측

def simulate_n400_surprisal_correlation(n_words=100):
    """
    Cloze probability → surprisal → N400 진폭 시뮬레이션
    N400 진폭은 surprisal에 비례 (음수 방향: 더 예측 불가 = 더 음전위)
    """
    # Cloze probability: 인간이 빈칸에 그 단어를 쓰는 비율
    cloze_probs = np.random.beta(2, 5, n_words)  # 대부분 낮은 cloze prob
    
    # Surprisal = -log2(cloze_prob)
    # 수치 안정을 위해 클리핑
    surprisals = -np.log2(np.clip(cloze_probs, 1e-6, 1.0))
    
    # N400 진폭: -2μV ~ -8μV (높은 surprisal에서 더 음수)
    # 노이즈 포함 (실제 ERP는 노이즈 있음)
    noise = np.random.randn(n_words) * 0.5
    n400_amplitudes = -2.0 - 0.8 * surprisals + noise
    
    return surprisals, n400_amplitudes, cloze_probs

surprisals, n400_amplitudes, cloze_probs = simulate_n400_surprisal_correlation(150)

# 상관 분석
r_surprisal_n400, p_surprisal = pearsonr(surprisals, n400_amplitudes)
r_cloze_n400, p_cloze = pearsonr(cloze_probs, n400_amplitudes)

print("=== Surprisal ↔ N400 진폭 분석 ===")
print(f"Surprisal ↔ N400 상관계수: r = {r_surprisal_n400:.3f} (p = {p_surprisal:.4f})")
print(f"Cloze probability ↔ N400 상관계수: r = {r_cloze_n400:.3f} (p = {p_cloze:.4f})")
print(f"\n해석: surprisal이 높을수록 N400이 더 음적 (부적 상관)")
print(f"= 예측이 빗나갈수록 더 큰 신경 반응 = 예측 오차 신호")

# 예시 문장 surprisal
print("\n=== 예시 문장 Surprisal ===")
sentences = [
    ("그녀는 피아노를", "연주했다", 0.65),   # 높은 cloze
    ("그녀는 피아노를", "먹었다", 0.001),    # 낮은 cloze
    ("그녀는 피아노를", "팔았다", 0.12),     # 중간 cloze
]

for context, word, cloze in sentences:
    surprisal = -np.log2(cloze)
    expected_n400 = -2.0 - 0.8 * surprisal
    print(f"  '{context} [{word}]': cloze={cloze:.3f}, surprisal={surprisal:.2f} bits, "
          f"예상 N400={expected_n400:.2f}μV")

print("\n→ 예측 가능한 단어는 낮은 surprisal, 약한 N400")
print("→ 예측 불가 단어는 높은 surprisal, 강한 N400 (큰 예측 오차)")
```

### 실험 2: 언어 모델의 Surprisal과 인간 읽기 시간 비교

```python
import numpy as np
from scipy.stats import spearmanr

# 단순화된 언어 모델 surprisal과 읽기 시간의 관계
# 기반: Demberg & Keller (2008), Frank & Bod (2011)

def ngram_surprisal(word, context_words, corpus_stats):
    """
    간단한 bigram 모델 surprisal 계산
    p(word | prev_word) 추정
    """
    if not context_words:
        # 유니그램 확률
        total = sum(corpus_stats['unigram'].values())
        count = corpus_stats['unigram'].get(word, 1)
        return -np.log2(count / total)
    
    prev_word = context_words[-1]
    bigram_count = corpus_stats['bigram'].get((prev_word, word), 0.5)  # 라플라스 스무딩
    prev_count = corpus_stats['unigram'].get(prev_word, 1)
    
    prob = bigram_count / prev_count
    return -np.log2(max(prob, 1e-8))

# 간단한 한국어 코퍼스 통계 (시뮬레이션)
corpus_stats = {
    'unigram': {
        '그': 1000, '녀': 200, '는': 1500, '피아노': 100, '를': 1400,
        '연주했다': 50, '먹었다': 300, '팔았다': 80, '배웠다': 60,
        '그리고': 800, '또한': 400
    },
    'bigram': {
        ('피아노', '를'): 95, ('를', '연주했다'): 40,
        ('를', '먹었다'): 2, ('를', '팔았다'): 15, ('를', '배웠다'): 20,
    }
}

# 테스트 문장들과 실제 읽기 시간 (ms, 시뮬레이션)
test_cases = [
    (['피아노', '를'], '연주했다', 320),   # 예측 가능, 빠른 읽기
    (['피아노', '를'], '팔았다', 410),     # 중간 예측 가능
    (['피아노', '를'], '배웠다', 440),     # 덜 예측 가능
    (['피아노', '를'], '먹었다', 580),     # 예측 불가, 느린 읽기
]

print("=== 언어 모델 Surprisal vs. 읽기 시간 ===")
model_surprisals = []
reading_times = []

for context, word, rt in test_cases:
    surp = ngram_surprisal(word, context, corpus_stats)
    model_surprisals.append(surp)
    reading_times.append(rt)
    print(f"  '{' '.join(context)} [{word}]': surprisal={surp:.2f} bits, 읽기 시간={rt}ms")

rho, p = spearmanr(model_surprisals, reading_times)
print(f"\nSpearman 상관: ρ = {rho:.3f}")
print(f"해석: 모델 surprisal이 높을수록 읽기 시간 증가 = 인간 처리 부하와 일치")
print(f"\n인간 뇌 vs. 언어 모델: 같은 곳에서 어려움을 느낀다")
print(f"→ 예측 오차(δ)가 처리 부하를 결정하는 공통 원리")
```

**반례와 경계**:
- **구문적 경원(garden path) 문장**: "말이 경기를 쉽게 이겼다"(the horse raced past the barn fell)처럼 잘못된 구조 예측 후 수정이 필요한 문장에서, 순수한 다음 단어 예측 모델은 인간의 처리 어려움을 완전히 설명하지 못한다. 구조적 재분석(reanalysis)이 필요하다.
- **조성성 한계**: LLM은 "빨갛지 않은 사과"와 "빨간 사과가 아닌 것" 같은 논리적으로 동치인 표현을 처리할 때 인간과 다른 패턴을 보인다.
- **기반 문제(grounding problem)**: 색각 이상자가 없는 텍스트에서 학습한 LLM은 "빨강"의 현상적 경험을 가질 수 없다. 예측의 정확성이 이해의 충분조건인가?

## 🌉 간극의 위치

| 주장 | 상태 | 근거 |
|------|------|------|
| 인간 언어 처리가 예측적 | ✅ | N400, 읽기 시간, cloze probability 연구 |
| LLM surprisal이 N400 예측 | ✅ | Schrimpf et al. 2021 |
| 다음 토큰 예측에서 능력 창발 | ✅ | GPT 시리즈, scaling law 연구 |
| 인간과 LLM이 같은 표상 사용 | ❌ | 표상의 질적 차이 가능성 |
| LLM이 의미론적으로 이해한다 | ❌ | 기반 문제, 철학적 미결 |
| 언어 예측이 언어 능력의 충분조건 | ❌ | 조성성, 체계성 한계 |

## 🧬 원리의 회수

언어 처리의 신경과학적 증거(N400, 읽기 시간), 언어 학습의 계산 모델(LLM), 그리고 정보 이론(surprisal)은 모두 하나의 원리로 수렴한다:

**언어 이해는 맥락에 기반한 다음 단위의 확률 예측이며, 예측 오차($\delta = w_t - \hat{w}_t$)가 처리 부하와 학습을 결정한다.**

$$\text{처리 부하} \propto S(w_t) = -\log_2 p(w_t \mid w_{<t})$$

이 원리는 인간과 LLM에서 동시에 발견된다. 그러나 이 동형성이 동일성을 의미하지는 않는다—같은 목적 함수가 다른 기질(substrate)에서 다른 표상을 낳을 수 있다. 이것이 IQ AI Lab이 집중해야 할 핵심 질문이다: LLM의 예측적 언어 처리는 지능의 어떤 측면을 포착하고, 어떤 측면을 놓치는가?

## 🪞 1인칭

이 문장을 읽는 순간, 나는 다음 단어를 예측하고 있다. 대부분은 맞고, 가끔 틀린다—그때 N400이 발생한다. 그러나 내가 언어를 이해한다고 말할 때, 나는 단순히 다음 단어를 예측하는 것 이상을 느낀다: 의미가 이해된다, 화자의 의도가 포착된다, 맥락이 감각된다.

LLM이 같은 surprisal 패턴을 보인다는 것이 LLM도 이해한다는 것을 의미하는가? 아마도 이 질문 자체가 잘못되었을지 모른다. "이해"를 예측 정확성으로 조작화하면 LLM은 이해한다. "이해"를 현상적 경험으로 정의하면 모른다. 예측 원리는 실재하지만, 그것이 이해를 구성하는지 아니면 이해를 *가능하게 하는* 것인지—이 질문은 철학의 영역으로 남는다.

## 📐 예측·반증

**예측 1**: 더 나은 언어 모델(낮은 perplexity)은 더 정확하게 N400 진폭을 예측해야 한다. → **반증 조건**: perplexity 감소가 N400 예측 개선과 무상관이면, 인간 처리와 LLM 처리의 공유 구조 주장 약화.

**예측 2**: 인간이 처리하기 어려운 구문(경원 문장, 비정형적 담화)에서 LLM의 surprisal도 높아야 한다. → **반증 조건**: 인간 처리 어려움과 LLM surprisal의 계통적 불일치 시, 동형성 주장의 한계 명확화.

**예측 3**: 언어 습득 과정에서 아동이 더 많은 예측 오차를 경험하는 언어 구조를 나중에 습득해야 한다. → **반증 조건**: 습득 순서와 예측 오차 크기의 무상관 시, 언어 학습에서 예측 오차의 역할 의문.

## 🤔 열린 질문

- 언어의 화용론(pragmatics)—화자 의도, 맥락 적합성, 간접 발화—은 순수한 다음 단어 예측으로 포착 가능한가, 아니면 별도의 "의도 추론(theory of mind)" 모듈이 필요한가?
- LLM의 표상과 인간 뇌의 언어 표상이 실제로 얼마나 유사한가? → fMRI 활성화 패턴 비교 연구
- 언어 예측 능력이 포화되면(AGI 수준) 무엇이 남는가? → [04-attention-as-precision.md](./04-attention-as-precision.md)에서 주의와 맥락 선택의 역할로 이어짐

---

> 🧩 **Principle** — 언어 이해는 맥락 조건부 확률 예측이다: $p(w_t \mid w_{<t})$. N400은 인간 뇌의 예측 오차 신호이며, LLM의 surprisal은 이 신호를 예측한다. 같은 계산 원리가 두 시스템을 관통한다.

> 🌉 **Boundary** — 예측 정확성이 언어 이해의 충분조건인지는 열려 있다. 기반 문제, 조성성, 현상적 경험은 인간과 LLM이 분기하는 지점이다. LLM은 언어의 통계적 구조를 완벽하게 내면화하지만, 그것이 의미론적 이해인지는 미결이다.

> 🪞 **Experience** — 당신이 이 문장의 끝에 오는 단어를 예측하고 있다면, 당신은 이미 언어 모델이다—그보다 훨씬 더 풍부한 무언가이기도 하지만.

## 📝 연습문제

**기초.** "그는 은행에 갔다"에서 "은행"은 금융 기관인가, 강둑인가? 이 중의성(ambiguity) 해소를 surprisal 프레임워크로 설명하라.

<details><summary>해설</summary>

"은행"의 중의성 해소는 맥락 조건부 사전확률로 설명된다. "돈을 찾으러"가 선행하면 $p(\text{금융 은행} \mid \text{맥락}) \gg p(\text{강둑} \mid \text{맥락})$이고, "낚시를 하러"가 선행하면 반대다. 뇌는 맥락에서 가장 낮은 surprisal을 갖는 해석을 선택한다. 경원 문장에서는 처음에 잘못된 해석을 선택하고 나중에 수정하는데, 이 수정 시점에 P600(또 다른 ERP 성분)이 발생한다. 중의성 해소는 동적 베이즈 추론—맥락이 추가될수록 사후확률이 업데이트됨—으로 모델링된다.

</details>

**심화.** Schrimpf et al.(2021)의 결과—LLM surprisal이 N400을 예측—가 "LLM이 인간처럼 언어를 처리한다"는 결론을 지지하는가? 이 추론의 논리적 타당성과 한계를 평가하라.

<details><summary>해설</summary>

이 결론은 역추론의 오류(reverse inference fallacy)에 가깝다. N400 예측 성공은 LLM과 인간 뇌가 동일한 *통계적 구조*를 내면화함을 시사하지만, 동일한 처리 메커니즘을 의미하지 않는다. 유사성의 수준: (1) 행동적 유사성(surprisal 예측) ≠ (2) 계산적 유사성(알고리즘) ≠ (3) 구현 유사성(신경 메커니즘). LLM이 인간 언어 처리를 행동적으로 근사하더라도, 그 내부 메커니즘은 다를 수 있다. 더 강한 주장을 위해서는 LLM의 중간 표상이 인간 뇌 활성화 패턴과 RSA(Representational Similarity Analysis)에서 유사함을 보여야 한다.

</details>

**논문 비평.** Chomsky, N. (1957)의 생성 문법 프로그램과 Elman, J.L. (1990) "Finding structure in time"의 통계적 언어 학습 접근을 비교하라. 현재 LLM의 성공은 어느 입장을 지지하는가? Chomsky의 최근 비판(2023)을 포함해 평가하라.

<details><summary>해설</summary>

Chomsky는 언어 능력이 생득적 보편 문법에 기반하며, 통계적 패턴은 언어의 본질을 포착하지 못한다고 주장했다. Elman은 단순한 순환 신경망이 다음 단어 예측만으로 문법 구조를 학습함을 보여 통계적 접근의 타당성을 입증했다. LLM의 성공은 표면적으로 Elman의 입장을 지지한다—방대한 통계 학습이 풍부한 언어 능력을 낳는다. 그러나 Chomsky(2023)의 비판은 날카롭다: LLM은 가능한 언어와 불가능한 언어를 구별하지 못하며, 진정한 인과적 설명이 아니라 상관관계 포착에 불과하다고 주장한다. 이 논쟁은 언어 능력의 본성에 대한 근본적 질문으로, 통계적 예측이 언어 이해의 충분조건인지에 대한 답이 필요하다.

</details>

---

<div align="center">

[◀ 이전: 기억 = 예측적 재구성](./02-memory-as-prediction.md) · [📚 README](../README.md) · [다음: 주의 = 정밀 가중치 ▶](./04-attention-as-precision.md)

</div>
