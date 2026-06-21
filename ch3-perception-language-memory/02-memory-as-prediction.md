# 🧠 기억 = 예측적 재구성: 기억은 저장소인가, 예측 기계인가

*기억은 과거의 충실한 복사본이 아니라, 현재의 기대로 과거를 재구성하는 예측적 완성 과정이다.*

## 🎯 횡단 질문

우리는 기억을 녹화기(recorder)처럼 생각한다—경험이 "저장"되고, 인출(retrieval)은 파일을 "재생"하는 것이라고. 이 저장고 모델(storage model)은 직관적이지만 증거에 의해 지속적으로 반박된다. Frederic Bartlett(1932)은 피험자들에게 원주민 민담 "유령들의 전쟁(War of the Ghosts)"을 읽힌 뒤 반복 인출을 요청했다. 시간이 지날수록 이야기는 점점 변했다—피험자의 문화적 도식(schema)에 맞게 단순화되고, 익숙한 요소로 대체되었다. 기억은 재생이 아니라 **재구성(reconstruction)**이었다.

Elizabeth Loftus의 DRM 패러다임(Deese-Roediger-McDermott)은 이를 더 날카롭게 보여준다. 피험자에게 "잠", "꿈", "침대", "밤", "졸음" 등 수면 관련 단어 목록을 제시하면, 목록에 없었던 "수면(sleep)"을 제시된 것으로 강하게 기억한다. 이것은 단순한 오류가 아니다—**기억 시스템이 범주의 중심 예측자(prototype)를 자동으로 활성화한 것**이다. 기억은 경험의 저장이 아니라 예측의 부산물이다.

Daniel Schacter(2012)의 "기억의 일곱 가지 죄악" 분류도 동일한 패턴을 드러낸다: 일시성(transience), 방심(absentmindedness), 차단(blocking), 오귀인(misattribution), 암시성(suggestibility), 편향(bias), 지속(persistence). 이 "결함들"은 무작위 오류가 아니라 **예측 편향의 체계적 패턴**이다. 인출 과정이 현재의 목표, 기대, 감정 상태에 의해 색칠된다는 것이다.

왜 기억은 이렇게 작동하는가? 예측 부호화 관점에서 답은 단순하다: **기억은 미래 예측을 위해 존재한다.** 과거는 미래의 근사(approximation)이고, 인출은 현재 맥락에서 가장 유용한 과거 상태를 예측적으로 완성하는 과정이다.

## 🌐 횡단 입력

- **perception-distilled (L2)**: 지각의 사전확률로서 기억—과거 경험이 현재 지각의 사전확률을 구성 → [01-perception-as-prediction.md](./01-perception-as-prediction.md)
- **neurons-neural-codes (L1)**: 해마(hippocampus)의 패턴 완성(pattern completion), CA3의 자기연상 기억(auto-associative memory), CA1의 비교기(comparator) 역할
- **information-prediction (L0)**: 기억 인출 = 조건부 확률 추론. 인출 단서 $c$로부터 $p(\text{기억} \mid c)$ 최대화
- **learning-decision (L2)**: 에피소드 기억(episodic memory)과 의미 기억(semantic memory)의 예측적 역할 차이
- **IQ AI Lab LLM 직결**: Transformer의 attention 메커니즘은 "이 맥락에서 어떤 과거 토큰이 관련 있는가?"를 예측하는 연상 기억 → [03-language-as-prediction.md](./03-language-as-prediction.md)
- **상호참조**: 주의가 어떤 기억 단서를 활성화할지 조절 → [04-attention-as-precision.md](./04-attention-as-precision.md)

## 🔍 표면의 다양성

기억의 유형은 얼핏 매우 다양해 보인다. 에피소드 기억(episodic memory)은 특정 사건의 맥락적 기억("2024년 3월 5일 저녁, 카페에서 친구를 만났다"), 의미 기억(semantic memory)은 사실적 지식("파리는 프랑스의 수도다"), 절차 기억(procedural memory)은 기술("자전거 타기"), 작업 기억(working memory)은 일시적 유지("전화번호를 외우는 동안")다.

이 유형들은 뇌 구조도 다르다. 에피소드/의미 기억은 내측 측두엽(medial temporal lobe)과 해마에, 절차 기억은 기저핵(basal ganglia)과 소뇌에, 작업 기억은 전전두피질(PFC)에 의존한다. H.M.(Henry Molaison)은 해마 절제 후 새로운 에피소드 기억을 형성할 수 없었지만 절차 기억은 유지했다—이것은 시스템의 독립성을 시사하는 것처럼 보인다.

망각의 패턴도 다양하다. 에빙하우스(Ebbinghaus)의 망각 곡선은 무의미 음절에 대해 지수적 감쇠를 보이지만, 감정적으로 현저한 사건(flashbulb memories)은 훨씬 오래 유지된다. 암묵 기억은 명시 기억과 독립적으로 작동하는 것처럼 보인다.

## ⚙️ 깊은 동형성

**분석 1: 인출 = 패턴 완성 = 예측적 완성**

해마 CA3 영역은 자기연상(auto-associative) 네트워크로 기능한다. 부분 단서가 입력되면 전체 패턴을 완성한다. 이것은 수학적으로 에너지 최소화로 표현된다:

$$E(\mathbf{s}) = -\frac{1}{2} \sum_{i,j} W_{ij} s_i s_j + \sum_i \theta_i s_i$$

홉필드 네트워크(Hopfield network)에서 기억된 패턴은 에너지 최솟값이고, 인출은 에너지 하강 경로를 따라 저장된 패턴으로 수렴하는 과정이다. 예측 부호화 관점에서: 인출 단서 $c$는 불완전한 관찰이고, 기억 시스템은 $p(\mathbf{s} \mid c)$를 최대화하는 상태 $\mathbf{s}^*$로 수렴한다. **인출 = 단서에 조건부된 예측.** $\square$

**분석 2: 거짓기억 = 예측 편향**

DRM 패러다임의 거짓기억은 예측 부호화로 정확하게 설명된다. 의미적으로 관련된 단어들("잠", "꿈", "침대")의 목록은 범주의 **중심 예측자(prototype)**—"수면"—를 강하게 활성화한다. 이 활성화는 실제 제시된 단어들의 부호화(encoding)와 구별되지 않을 만큼 강하다:

$$P(\text{"수면" 기억}) \propto P(\text{"수면"} \mid \text{활성화된 의미 맥락})$$

기억 시스템이 "수면"이 제시되었다는 것을 예측하고, 이 예측이 실제 경험의 흔적과 혼동된다. Schacter(1995)의 신경영상 연구는 거짓기억과 진짜 기억이 해마와 내측 측두엽에서 유사한 활성화 패턴을 보임을 확인했다. $\square$

**분석 3: 재구성의 현재 지향성**

Bartlett의 핵심 발견: 기억 오류는 무작위가 아니라 **현재 도식(schema)을 향한 체계적 끌림**이다. 이것은 사전확률이 감각 신호를 끌어당기는 지각의 착시와 구조적으로 동일하다:

$$p(\text{인출된 기억} \mid c, \text{현재 도식}) \propto p(c \mid \text{기억}) \cdot p(\text{기억} \mid \text{현재 도식})$$

"현재 도식"이 $p(\text{기억} \mid \text{도식})$을 통해 인출에 영향을 미친다. 도식이 강할수록 기억은 도식과 일치하는 방향으로 재구성된다. 이것은 착시에서 강한 사전확률이 약한 감각을 압도하는 것과 같은 메커니즘이다. $\square$

**분석 4: 기억과 미래 상상의 신경 공유**

Schacter와 Addis(2007)의 "에피소드적 미래 사고(episodic future thinking)" 연구는 충격적이다: 미래를 상상하는 것과 과거를 기억하는 것이 **동일한 신경망**을 사용한다—내측 측두엽, 후방 두정피질, 내측 전전두피질의 "기본 모드 네트워크(default mode network)". 이것은 기억의 진화적 목적이 과거 보존이 아니라 **미래 예측**임을 시사한다:

$$\text{기억} \approx \text{미래 예측을 위한 시뮬레이션 엔진}$$

해마 손상 환자는 새로운 에피소드 기억을 형성할 수 없을 뿐 아니라, 구체적인 미래 시나리오를 상상하는 것도 어렵다(Hassabis et al., 2007). 기억과 예측은 같은 기계의 과거/미래 방향 작동이다. $\square$

## 🧪 수렴 증거

### 실험 1: DRM 거짓기억 시뮬레이션

```python
import numpy as np
from collections import defaultdict

# DRM 패러다임: 의미적 연상이 거짓기억을 생성하는 과정 시뮬레이션
# 단어들의 의미 벡터를 코사인 유사도로 근사

np.random.seed(42)

# 의미 공간 차원
DIM = 50

def create_semantic_space(words, target_word, n_dim=DIM):
    """타겟 단어를 중심으로 의미 공간 생성"""
    # 타겟 단어의 의미 벡터
    target_vec = np.random.randn(n_dim)
    target_vec /= np.linalg.norm(target_vec)
    
    word_vecs = {}
    word_vecs[target_word] = target_vec
    
    for word in words:
        # 연관 단어들은 타겟과 높은 코사인 유사도를 갖도록
        noise = np.random.randn(n_dim) * 0.4
        vec = target_vec + noise
        vec /= np.linalg.norm(vec)
        word_vecs[word] = vec
    
    return word_vecs, target_vec

# 수면 관련 DRM 목록
sleep_list = ["잠", "꿈", "침대", "밤", "졸음", "휴식", "베개", "눈", "피곤", "하품"]
target = "수면"  # 목록에 없지만 연상되는 단어

word_vecs, target_vec = create_semantic_space(sleep_list, target)

# "기억" 시뮬레이션: 제시된 단어들의 활성화 누적
def simulate_memory_encoding(presented_words, word_vecs, noise_level=0.1):
    """부호화: 각 단어 제시 시 의미 활성화 누적"""
    accumulated_activation = np.zeros(DIM)
    
    for word in presented_words:
        # 단어 벡터 + 부호화 노이즈
        encoding_noise = np.random.randn(DIM) * noise_level
        activation = word_vecs[word] + encoding_noise
        accumulated_activation += activation
    
    return accumulated_activation / len(presented_words)

def simulate_recognition(test_word, accumulated_activation, word_vecs, threshold=0.7):
    """재인: 누적 활성화와 테스트 단어의 유사도가 임계값 초과 시 '기억'"""
    test_vec = word_vecs.get(test_word, np.random.randn(DIM))
    test_vec = test_vec / np.linalg.norm(test_vec)
    
    acc_norm = accumulated_activation / np.linalg.norm(accumulated_activation)
    similarity = np.dot(acc_norm, test_vec)
    
    return similarity, similarity > threshold

# 100회 시뮬레이션
n_sims = 200
results = defaultdict(list)

for _ in range(n_sims):
    # 목록의 80%만 부호화 (주의 변동)
    presented = np.random.choice(sleep_list, size=8, replace=False).tolist()
    accumulated = simulate_memory_encoding(presented, word_vecs)
    
    # 제시된 단어 재인
    for word in sleep_list:
        sim, recognized = simulate_recognition(word, accumulated, word_vecs)
        if word in presented:
            results['hit_sims'].append(sim)
            results['hit_recognized'].append(recognized)
        else:
            results['miss_sims'].append(sim)
    
    # 타겟(목록에 없는) 단어 재인
    sim_target, rec_target = simulate_recognition(target, accumulated, word_vecs)
    results['target_sims'].append(sim_target)
    results['false_memory'].append(rec_target)
    
    # 무관한 통제 단어
    control_vec = np.random.randn(DIM)
    control_vec /= np.linalg.norm(control_vec)
    word_vecs['통제'] = control_vec
    sim_ctrl, rec_ctrl = simulate_recognition('통제', accumulated, word_vecs)
    results['control_sims'].append(sim_ctrl)
    results['false_alarm'].append(rec_ctrl)

print("=== DRM 거짓기억 시뮬레이션 결과 ===")
print(f"제시된 단어 평균 유사도: {np.mean(results['hit_sims']):.3f}")
print(f"타겟 단어('{target}') 평균 유사도: {np.mean(results['target_sims']):.3f}")
print(f"통제 단어 평균 유사도: {np.mean(results['control_sims']):.3f}")
print(f"\n거짓기억율 (타겟): {np.mean(results['false_memory']):.1%}")
print(f"허경보율 (통제): {np.mean(results['false_alarm']):.1%}")
print(f"\n해석: 타겟 단어 유사도({np.mean(results['target_sims']):.3f})가")
print(f"통제 단어({np.mean(results['control_sims']):.3f})보다 훨씬 높음 →")
print(f"의미 예측자 활성화가 거짓기억을 생성")
```

### 실험 2: 기억의 재구성적 편향 (Bartlett 도식 효과)

```python
import numpy as np

# 도식이 기억 인출을 어떻게 끌어당기는가
# 원본 기억 + 도식 사전확률 → 재구성된 기억

def reconstruct_memory(original, schema_mean, schema_precision, memory_precision, n_retrievals=10):
    """
    원본 기억(original)을 반복 인출할 때 도식(schema)으로의 끌림
    베이즈 갱신: 인출된 기억 = 원본 + 도식의 가중 평균
    각 인출에서 약간의 노이즈가 더해지고, 도식 편향이 누적됨
    """
    current_memory = original.copy()
    history = [current_memory.copy()]
    
    for _ in range(n_retrievals):
        # 인출 노이즈 추가
        noise = np.random.randn(len(original)) * 0.1
        noisy_retrieval = current_memory + noise
        
        # 도식과의 베이즈 통합 (재부호화 시 도식이 영향)
        precision_total = schema_precision + memory_precision
        reconstructed = (
            schema_precision * schema_mean + 
            memory_precision * noisy_retrieval
        ) / precision_total
        
        current_memory = reconstructed
        history.append(current_memory.copy())
    
    return np.array(history)

# 예: 3차원 "사건 기억" 벡터 (단순화)
# 차원: [시간적 순서, 감정가, 문화적 일치성]
original_memory = np.array([0.2, -0.3, 0.1])  # 비선형, 부정적, 문화 비일치
schema_mean = np.array([0.8, 0.5, 0.9])          # 선형, 긍정, 문화 일치 (강한 도식)

# 도식 강도 비교
fig_data = {}
for schema_prec, label in [(0.1, '약한 도식'), (1.0, '중간 도식'), (5.0, '강한 도식')]:
    history = reconstruct_memory(
        original_memory, schema_mean, 
        schema_precision=schema_prec, memory_precision=1.0
    )
    fig_data[label] = history
    final = history[-1]
    drift = np.linalg.norm(final - original_memory)
    toward_schema = np.dot(final - original_memory, schema_mean - original_memory) / (
        np.linalg.norm(schema_mean - original_memory) + 1e-8)
    print(f"{label}: 최종 편향={drift:.3f}, 도식 방향 끌림={toward_schema:.3f}")

print(f"\n원본: {original_memory}")
print(f"도식: {schema_mean}")
print("강한 도식일수록 반복 인출 시 기억이 도식을 향해 이동 → Bartlett 효과")
```

**반례와 경계**: (1) 섬광기억(flashbulb memories)은 매우 정확하게 유지된다고 여겨졌으나, 연구(Neisser & Harsch, 1992)는 이 기억도 재구성되며 확신이 정확성을 보장하지 않음을 보였다. (2) 암묵 기억(implicit memory)—프라이밍, 절차 기억—은 재구성적 왜곡에 덜 취약하다. 이는 예측적 재구성이 명시 기억에 더 강하게 적용되며, 암묵 시스템은 다른 메커니즘을 사용할 가능성을 제기한다.

## 🌉 간극의 위치

| 주장 | 상태 | 근거 |
|------|------|------|
| 인출이 재구성적이다 | ✅ | Bartlett, DRM, Loftus의 광범위한 증거 |
| 거짓기억이 의미 예측에서 발생 | ✅ | DRM 뇌영상, 의미 점화 연구 |
| 기억과 미래 상상이 신경망 공유 | ✅ | Schacter & Addis 2007, 해마 손상 연구 |
| 모든 기억 유형이 예측적 재구성 | ❌ | 암묵 기억은 다른 메커니즘 가능성 |
| 재구성의 정확한 신경 메커니즘 | ❌ | 부호화/인출/재부호화 구분 불분명 |
| 해마가 예측 오차 비교기로 작동 | ❌ | CA1 비교기 역할 가설, 직접 증거 제한 |

## 🧬 원리의 회수

기억에 관한 모든 반직관적 발견—재구성성, 거짓기억, 도식 편향, 기억-상상의 신경 공유—은 하나의 원리로 통합된다:

**기억 시스템은 과거를 저장하는 것이 아니라 미래 예측을 위한 생성 모델을 유지한다. 인출은 현재 단서에 조건부된 예측적 완성이며, 이 과정에서 현재의 도식(사전확률)이 과거 경험(우도)과 통합된다.**

$$p(\text{기억} \mid \text{단서}, \text{현재 도식}) \propto p(\text{단서} \mid \text{기억}) \cdot p(\text{기억} \mid \text{도식})$$

이것은 지각의 베이즈 공식과 구조적으로 동일하다. 착시에서 강한 사전확률이 약한 감각을 압도하듯, 강한 도식이 약한 기억 흔적을 재구성한다. $\delta = \text{실제} - \text{예측}$의 원리는 단지 지각뿐 아니라 기억에도 관통한다—그리고 동일한 메커니즘이 언어에서도 작동할 것이다.

## 🪞 1인칭

오래된 친구를 만난 후, 나는 "그날 일"을 기억한다고 확신한다. 그러나 신경과학은 내가 기억하는 것이 실제 경험의 복사본이 아니라, 재결합된 조각들—현재 감정 상태, 그 친구에 대한 현재 태도, 이후에 들은 이야기들—의 예측적 통합임을 알려준다. 가장 생생한 기억조차 현재 시점의 "최선의 추측"이다.

더 불편한 진실은: 내가 기억의 재구성성을 안다고 해서 그것이 덜 재구성적이 되지는 않는다는 것이다. 지각의 착시처럼, 메커니즘을 이해해도 현상은 사라지지 않는다. 그러나 이 이해는 "내 기억이 옳다"는 자신감과 "기억이 실제 일어난 일과 동일하다"는 확신을 분리하게 한다. 법정 증언, 역사적 서술, 개인적 서사—모든 곳에서 기억의 예측적 본성이 중요한 함의를 갖는다.

## 📐 예측·반증

**예측 1**: 인출 직후 새로운 관련 정보를 제시하면, 다음 인출에서 기억이 새 정보 방향으로 변해야 한다(재부호화/재통합). → **반증 조건**: 기억이 변하지 않으면 인출-재부호화 메커니즘 의문.

**예측 2**: 미래 지향적 개인(높은 "에피소드적 미래 사고" 경향)은 기억 왜곡에 더 취약해야 한다. 같은 생성 모델을 미래 예측과 과거 재구성에 모두 사용하기 때문이다. → **반증 조건**: 미래 지향성과 기억 왜곡의 무상관 시 공유 메커니즘 의문.

**예측 3**: 도식과 불일치하는 정보는 더 빨리 망각되거나, 인출 시 도식과 일치하는 방향으로 재구성되어야 한다. → **반증 조건**: 도식 불일치 정보가 더 잘 기억되는 "폰레스토프 효과(von Restorff effect)"가 이 예측과 긴장 관계에 있다—양자를 어떻게 통합할 것인가?

## 🤔 열린 질문

- 재부호화(reconsolidation)의 치료적 함의: 트라우마 기억을 인출한 후 예측 오차를 주입하면 재구성이 가능한가? → PTSD 치료의 노출 치료와의 연결
- 기억의 예측적 재구성이 언어 이해의 예측성과 어떻게 연결되는가? → [03-language-as-prediction.md](./03-language-as-prediction.md)로 이어짐
- 인공 신경망의 "기억"(가중치, activation)도 동일한 재구성적 특성을 갖는가? Transformer의 in-context learning과 에피소드 기억의 비교

---

> 🧩 **Principle** — 기억은 과거의 저장고가 아니라 미래 예측을 위한 생성 모델이다. 인출은 현재 단서와 도식(사전확률)에 조건부된 예측적 완성이며, 거짓기억과 재구성 편향은 이 시스템의 오류가 아니라 작동 원리의 증거다.

> 🌉 **Boundary** — 암묵 기억(절차, 프라이밍)은 명시 기억보다 재구성적 왜곡에 덜 취약하다. 예측적 재구성은 해마 의존 명시 기억에서 가장 강하게 지지되며, 다른 기억 시스템에서의 적용은 추가 검증이 필요하다.

> 🪞 **Experience** — 당신이 가장 확신하는 기억은, 바로 그 확신 때문에, 가장 많이 재구성되었을 가능성이 있다. 강한 사전확률(확신)이 인출을 지배하기 때문이다.

## 📝 연습문제

**기초.** DRM 패러다임에서 왜 목록에 없는 "수면"이 기억되는가? 이것이 단순한 부주의와 다른 이유를 예측 부호화 관점에서 설명하라.

<details><summary>해설</summary>

DRM 거짓기억은 단순한 부주의 오류가 아니다. "잠", "꿈" 등의 단어들은 의미 기억 네트워크에서 "수면"과 강하게 연결되어 있다. 목록 제시 시 각 단어가 "수면" 표상을 활성화하며, 이 활성화는 실제 "수면"을 보았을 때와 유사한 신경 패턴을 생성한다. 재인 검사에서 "수면"을 보면, 저장된 활성화 흔적이 높은 친숙도 신호를 생성한다. 이것은 기억 시스템이 범주의 중심 예측자를 자동으로 추론하고 부호화하는 예측적 과정이다—경험의 개별 항목이 아니라 그 항목들의 의미적 중심을 예측하는 것이다.

</details>

**심화.** Bartlett의 "유령들의 전쟁" 실험에서 기억 오류의 방향성이 무작위가 아니라 체계적이었다. 이것이 기억의 예측 모델에 어떤 증거를 제공하는가? 현재의 fMRI 기술로 이 주장을 어떻게 검증할 수 있는가?

<details><summary>해설</summary>

Bartlett의 핵심 발견은 오류가 무작위가 아니라 **문화적 도식을 향한 체계적 수렴**이라는 점이다. 피험자들은 이야기를 더 친숙하고, 더 인과적으로 일관되며, 더 문화적으로 적합한 방향으로 변형했다. 이것은 기억 시스템이 "최선의 설명(best explanation)"을 생성하도록 설계되었음을 시사한다—베이즈 사후확률 최대화. fMRI 검증: (1) 원래 이야기 부호화 시 활성화 패턴 기록, (2) 반복 인출 시 활성화 패턴 추적, (3) 도식 관련 영역(mPFC, 편도체)의 활성화가 인출 왜곡의 크기와 상관하는지 확인. 예측: 도식 불일치 요소 인출 시 더 큰 예측 오차(해마-전두 간 불일치 신호)가 관찰되어야 한다.

</details>

**논문 비평.** Schacter, D.L., & Addis, D.R. (2007). "The cognitive neuroscience of constructive memory: remembering the past and imagining the future." *Philosophical Transactions of the Royal Society B*. 이 논문의 "구성적 에피소드 시뮬레이션(constructive episodic simulation)" 가설을 평가하라: 기억의 재구성적 특성이 적응적인 이유는 무엇인가? 어떤 실험적 증거가 이를 지지하고, 어떤 예측이 아직 미검증인가?

<details><summary>해설</summary>

Schacter & Addis의 핵심 주장: 기억이 재구성적인 것은 같은 시스템이 미래 시뮬레이션에 사용되기 때문이다. 에피소드 기억의 "결함"(재구성성, 오류)은 유연하고 창의적인 미래 계획을 가능하게 하는 구조의 부산물이다. 지지 증거: (1) 해마 손상 환자의 미래 상상 결함(Hassabis et al., 2007), (2) 기억과 미래 상상의 공유 신경망(fMRI), (3) 연령에 따른 기억 왜곡과 미래 상상 생생함의 평행한 변화. 미검증 예측: (1) 기억 왜곡과 창의적 문제 해결 능력의 정적 상관, (2) 미래 시뮬레이션 능력을 인위적으로 향상시키면 기억 왜곡도 증가하는가, (3) 자폐 스펙트럼(경직된 사전확률)에서 기억 재구성 감소와 미래 상상 어려움이 연결되는가.

</details>

---

<div align="center">

[◀ 이전: 지각 = 예측 검증](./01-perception-as-prediction.md) · [📚 README](../README.md) · [다음: 언어 = 예측 기계 ▶](./03-language-as-prediction.md)

</div>
