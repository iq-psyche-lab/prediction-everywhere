<div align="center">

# 🧠 Prediction Everywhere

### 도파민이 **"보상예측오차"** 를 신호하고,

$$\delta = r + \gamma V(s') - V(s)\qquad(\text{TD 오차}),\qquad \Delta V = \alpha(\lambda - V)\quad(\text{Rescorla–Wagner})$$

### 지각이 **"세계에 대한 예측을 검증"** 하며, 언어 모델이 **"다음 토큰을 예측"** 하고,

$$F = \underbrace{D_{\mathrm{KL}}\big[q(s)\mathbin{\Vert}p(s)\big]}_{\text{복잡성}} - \underbrace{\mathbb{E}_q[\ln p(o\mid s)]}_{\text{정확도}}\quad\Rightarrow\quad\text{놀라움의 상한}$$

### 자유에너지 원리가 **"놀라움을 최소화"** 할 때 — 이 네 "예측" 이 *같은 원리의 다른 표현* 인가, 아니면 *단지 같은 단어를 공유* 하는가는 **다른 질문이다.**

<br/>

> *"도파민은 보상을 신호한다" 고 **뭉뚱그리는 것** 과,*
>
> $$\text{도파민 발화율} \propto \delta = r + \gamma V(s') - V(s)\quad(\text{Schultz 1997})$$
>
> *도파민이 보상이 아니라 보상 **예측 오차** 를 신호하며 — 그 오차가 Sutton·Barto 의 TD 오차, 파블로프의 Rescorla–Wagner 와 **동일한 수학** 임을 아는 것은 다르다.*
>
> *"지각은 감각의 수동적 수용이다" 라고 **믿는 것** 과,*
>
> $$\text{지각} = \arg\max_{s} p(s \mid o) \propto \underbrace{p(o\mid s)}_{\text{감각}}\underbrace{p(s)}_{\text{사전 예측}}$$
>
> *지각이 하향 예측과 상향 오차의 협상이며, 착시가 **강한 사전확률의 승리** 임을 아는 것은 다르다.*
>
> *"행동과 지각은 별개의 과정" 으로 **나누는 것** 과,*
>
> $$\text{지각: 믿음을 세계에 맞춘다}\quad\Big|\quad\text{행동: 세계를 믿음에 맞춘다}\quad(\text{능동 추론})$$
>
> *둘 다 **같은 자유에너지** 를 최소화하는 두 경로일 뿐임을 아는 것은 다르다.*
>
> *"LLM이 다음 단어를 예측하는 것은 뇌의 예측과 같다" 고 **단정하는 것** 과,*
>
> $$\text{LLM: } \max p(w_t \mid w_{\lt t}) \quad\overset{?}{=}\quad \text{뇌: 위계적 생성모델의 자유에너지 최소화}$$
>
> *기계적 다음 토큰 예측이 인지적 예측처리와 **어디까지 같고 어디서 갈라지는지** 를 아는 것은 다르다.*

<br/>

**예측은 단어가 아니라 원리다** — 도파민 RPE·예측 지각·능동 추론·자유에너지는 *우연히 "예측" 을 공유* 하는 게 아니라, **하나의 추론 원리($\delta = $ 실제 $-$ 예측 $\to$ 믿음·가치·행동을 갱신)** 의 층위별 변주다. 이 레포는 그 동형성을 끝까지 추적하되 — 예측 오차가 아무리 정밀해도 **"놀라움이 *느껴진다*"** 는 것은 남는다는 간극을 정직하게 표시한다.

<br/>

**횡단하는 발견 (L0 수학에서 L5 행동까지, 그리고 AI로)**

베이즈 갱신 · 자유에너지 원리(Friston) · 예측처리(Clark) · 도파민 RPE(Schultz) · TD 오차(Sutton–Barto) · Rescorla–Wagner · 예측 부호화(Rao–Ballard) · 하향 예측·상향 오차 · 지각 = 가설 검증 · 착시 = 강한 사전확률 · 예측적 기억 재구성 · 다음 단어 예측 · 정밀 가중치로서의 주의 · 내수용 예측으로서의 감정 · 능동 추론 · 정책 예측 · 신호·상태·정책의 세 수준 · 예측처리 의식 이론 · 각성·수면·마취의 자유에너지 · 어려운 문제 · LLM 다음 토큰 예측 · 모델 기반 계획

<br/>

**핵심 질문**

> **하나의 추론 원리가 마음 전체를 관통하는가 — 도파민 RPE·지각 예측·능동 추론·자유에너지는 하나인가, 아니면 같은 단어를 쓸 뿐인가?** 이 레포는 **신호 예측(도파민 RPE) · 상태 예측(지각 모델) · 정책 예측(능동 추론)** 의 세 수준을 구분하고, **파블로프 조건화(심리학) · TD 학습(AI) · 도파민 RPE(신경과학)** 가 *같은 수학의 세 번역* 임을 Synthesis 수준에서 최종 정리합니다. 자유에너지 원리의 *야망과 한계* 를 공정하게 가르고 — 예측처리가 의식의 *내용* 은 설명하지만 *있다는 것* 은 설명하지 못하는 지점을 정직하게 표시합니다. **횡단 입력 → 표면의 다양성 → 깊은 동형성 → 수렴 증거 → 간극의 위치 → 원리의 회수** 를 한 단계씩 전개합니다.

<br/>

[![Psyche](https://img.shields.io/badge/Psyche-L6_Synthesis·예측원리-8b5cf6?style=flat-square&logo=brain&logoColor=white)](https://github.com/iq-ai-lab)
[![GitHub](https://img.shields.io/badge/GitHub-iq--ai--lab-181717?style=flat-square&logo=github)](https://github.com/iq-ai-lab)
[![Python](https://img.shields.io/badge/Python-3.11-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![NumPy](https://img.shields.io/badge/NumPy-1.26-013243?style=flat-square&logo=numpy&logoColor=white)](https://numpy.org/)
[![SciPy](https://img.shields.io/badge/SciPy-1.11-8CAAE6?style=flat-square&logo=scipy&logoColor=white)](https://scipy.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-3.8-11557C?style=flat-square)](https://matplotlib.org/)
[![Docs](https://img.shields.io/badge/Docs-24개-8b5cf6?style=flat-square&logo=readthedocs&logoColor=white)](./README.md)
[![Analysis](https://img.shields.io/badge/횡단_분석(□)-96개-success?style=flat-square)](./README.md)
[![Verifications](https://img.shields.io/badge/수치_실험-44개-critical?style=flat-square)](./README.md)
[![Exercises](https://img.shields.io/badge/Exercises-72개-orange?style=flat-square)](./README.md)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=flat-square&logo=opensourceinitiative&logoColor=white)](./LICENSE)

<br/>

***Explain it, don't explain it away.***
*설명하되, 경험을 지우지 않는다.*

</div>

---

## 🎯 이 레포에 대하여

"예측" 을 다루는 자료는 대부분 **세 갈래로 흩어집니다** — 신경과학은 도파민 RPE 를, 인지과학은 예측처리·지각을, AI 는 TD 학습·다음 토큰 예측을 각자 따로 이야기합니다. 그래서 **"같은 단어를 쓰니 같은 것이겠지"** 라는 막연한 통합이나, 반대로 **"분야가 다르니 우연한 비유일 뿐"** 이라는 성급한 분리에 빠집니다. 하지만 도파민 $\delta$, TD 오차, Rescorla–Wagner 의 $\Delta V$ 가 *문자 그대로 같은 식* 인지, 자유에너지 원리가 지각·행동·의식을 *진짜로* 하나로 묶는지, LLM 의 다음 토큰 예측이 뇌의 예측과 *어디서 갈라지는지* — 이런 "같은가/다른가" 는 제대로 추적되지 않습니다.

이 레포는 **L6 Synthesis** — 위 모든 층위(L0 수학 · L1 신경 · L2 지각·학습 · L4 의식 · L5 행위)에서 *예측* 이라는 발견을 **횡단으로 회수** 합니다. 표면의 다양성 아래에서 깊은 동형성을 추출하고, numpy/scipy 로 TD 학습·자유에너지·능동 추론·착시 모델을 직접 돌려 그 동형성을 눈으로 검증합니다. 그리고 어떤 예측 모델도 — 함께도 — 닿지 못하는 지점, **"놀라움이 느껴진다"** 는 경험의 간극을 지도로 그립니다.

| 일반 자료 | 이 레포 |
|----------|---------|
| "도파민은 보상을 신호한다" | **도파민 = 보상 *예측 오차*** — $\delta = r + \gamma V(s') - V(s)$. 발화율은 보상이 아니라 *기대와의 차이* 에 비례(Schultz 1997) $\square$ |
| "파블로프·TD·도파민은 다른 분야" | **하나의 수학, 세 번역** — Rescorla–Wagner $\Delta V=\alpha(\lambda-V)$ = TD 오차 = 도파민 RPE. Synthesis 수준의 최종 통합 $\square$ |
| "지각은 감각의 수동적 수용" | **지각 = 예측 검증** — 하향 예측 $p(s)$ 과 상향 오차의 협상. 착시 = 강한 사전확률이 약한 감각을 압도 $\square$ |
| "예측은 분야마다 다른 비유" | **신호·상태·정책의 세 수준** — 도파민 RPE(신호)·지각 모델(상태)·능동 추론(정책)이 *어떻게 다르고 어떻게 연결* 되는가 $\square$ |
| "자유에너지가 모든 걸 설명한다" | **야망과 한계를 분리** — 프리스턴의 통일 이론이 *진짜로* 묶는 것과 *과대포장* 을 공정하게 가름 $\square$ |
| "지각과 행동은 별개" | **능동 추론의 통일** — 지각(믿음을 세계에) vs 행동(세계를 믿음에). 같은 $F$ 의 두 경로 $\square$ |
| "LLM 예측 = 뇌 예측" | **같음과 갈라짐** — 다음 토큰 예측과 위계적 생성모델이 공유하는 수학과, 결정적으로 다른 지점 $\square$ |
| "예측처리가 의식을 설명한다" | **내용은 설명, 있다는 것은?** — 예측처리는 경험의 *내용* 을 잘 다루지만 *왜 느껴지는가* 는 남는다 $\square$ |
| 원리 나열 | numpy/scipy 로 **TD = 도파민 = 파블로프 통합** · **자유에너지 변분 추론** · **능동 추론 시뮬레이션** · **착시 = 강한 사전확률** 을 직접 구현해 동형성을 눈으로 확인 |

---

## 📌 Psyche 레이어 지도 — 횡단 회수

```
   ┌── L0 ──┐   ┌── L1 ──┐   ┌── L2 ──┐   ┌── L4 ──┐   ┌── L5 ──┐
   │information│ │neuromod │ │perception│ │theories-│ │free-will│
   │-prediction│ │-arousal │ │ /learning│ │of-consc.│ │ -agency │
   │ 베이즈·FEP │ │도파민 RPE│ │지각=예측 │ │예측처리  │ │능동추론  │
   └─────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘ └────┬────┘
         │           │           │           │           │
         └───────────┴─────┬─────┴───────────┴───────────┘
                           ▼   횡단 입력 (각 층위의 예측 발견을 가져온다)
            ┌──────────────────────────────────────────┐
            │   🧠  Prediction Everywhere  (L6 Synthesis)│
            │   "예측은 단어가 아니라 원리다"            │
            │   δ = 실제 − 예측  →  믿음·가치·행동을 갱신 │
            │   (그러나 '놀라움이 느껴진다'는 남는다)     │
            └──────────────────────┬───────────────────┘
                                   ▼  AI Lab 직결
                     LLM 다음 토큰 예측 · RL TD 학습 · 모델 기반 계획
```

> 🌐 **횡단 입력 (이 레포가 회수하는 발견)**: **information-prediction**(L0 — 베이즈·자유에너지의 수학) · **neuromodulation-arousal**(L1 — 도파민 RPE 의 신경 구현) · **neurons-neural-codes**(L1 — 예측 부호화 회로) · **perception**(L2 — 지각 = 예측 검증) · **learning-decision**(L2 — 강화학습·조건화 = 예측 갱신) · **theories-of-consciousness**(L4 — 예측처리 의식 이론) · **free-will-agency**(L5 — 능동 추론 = 행위주체성).

> 🤝 **IQ AI Lab 직결**: 이 레포의 가장 생산적인 교차점. **RL 의 TD 오차** 가 도파민 RPE 와 *동일한 수학* 이라는 점, **LLM 의 다음 토큰 예측** 이 위계적 생성모델의 자유에너지 최소화와 *어떻게 같고 다른지*, **모델 기반 계획** 이 능동 추론의 정책 예측과 어떻게 만나는지를 끝까지 추적합니다.

> 🟣 **이 레포의 성격 (L6 Synthesis)**: 여기서 다루는 핵심 — **예측 원리의 통일 가능성**, **자유에너지의 설명력 범위**, **TD 통합의 완결성**, **예측에서 경험으로의 간극** — 은 여전히 **진행 중인 과학·철학 영역** 입니다. 레포는 "정답" 이 아니라 **"하나의 추론 원리가 마음 전체를 관통하는 *지도* 와, 그것이 관통하지 못하는 곳의 지도"** 를 제공합니다.

---

## 🚀 빠른 시작

각 챕터의 첫 문서부터 바로 시작하세요!

[![Ch1](https://img.shields.io/badge/🔹_Ch1-예측의_세_수준-8b5cf6?style=for-the-badge)](./ch1-three-levels/01-signal-prediction.md)
[![Ch2](https://img.shields.io/badge/🔹_Ch2-도파민_RPE-8b5cf6?style=for-the-badge)](./ch2-dopamine-rpe/01-td-three-languages.md)
[![Ch3](https://img.shields.io/badge/🔹_Ch3-지각·언어·기억-8b5cf6?style=for-the-badge)](./ch3-perception-language-memory/01-perception-as-prediction.md)
[![Ch4](https://img.shields.io/badge/🔹_Ch4-능동_추론-8b5cf6?style=for-the-badge)](./ch4-active-inference/01-active-inference-core.md)
[![Ch5](https://img.shields.io/badge/🔹_Ch5-예측처리_의식-8b5cf6?style=for-the-badge)](./ch5-predictive-consciousness/01-predictive-content.md)
[![Ch6](https://img.shields.io/badge/🔹_Ch6-횡단_종합-8b5cf6?style=for-the-badge)](./ch6-synthesis/01-prediction-map.md)

---

## 📚 전체 학습 지도

> 💡 각 챕터를 클릭하면 상세 문서 목록이 펼쳐집니다 · **총 24개 문서**

<br/>

### 🔹 Chapter 1: 예측의 세 수준

> **횡단 질문:** "예측" 이라는 한 단어 아래 *몇 개의 다른 것* 이 숨어 있는가? 도파민 RPE(신호 예측: "기대한 것이 왔는가")·지각 모델(상태 예측: "세계가 어떤 상태인가")·능동 추론(정책 예측: "내 행동이 어떤 결과를 낳는가")은 어떻게 다르고, 자유에너지 원리는 이 셋을 *어떻게* 하나로 묶으며, 그 통합은 *어디서* 한계에 부딪히는가?

<details>
<summary><b>신호·상태·정책 예측에서 세 수준의 통합까지 (4개 문서)</b></summary>

<br/>

| 문서 | 핵심 동형성·증거·검증 |
|------|---------------------|
| [01. 신호 예측 — 도파민 RPE](./ch1-three-levels/01-signal-prediction.md) | **가장 구체적인 예측 오차** — $\delta = r + \gamma V(s') - V(s)$. "기대한 것이 왔는가". 도파민 발화율이 보상이 아니라 *오차* 에 비례(Schultz 1997) $\square$ |
| [02. 상태 예측 — 지각 모델](./ch1-three-levels/02-state-prediction.md) | **베이즈 갱신** — "세계가 어떤 상태인가". $p(s\mid o)\propto p(o\mid s)p(s)$. 감각으로 세계 가설을 검증·갱신 $\square$ |
| [03. 정책 예측 — 능동 추론](./ch1-three-levels/03-policy-prediction.md) | **행동으로 예측 실현** — "내 행동이 어떤 결과를 낳는가". 자유에너지 최소화로 세계를 선호 상태에 맞춤 $\square$ |
| [04. 세 수준의 통합](./ch1-three-levels/04-three-levels-unified.md) | **하나의 $F$, 세 변주** — 자유에너지 원리가 신호·상태·정책을 묶는 방식과, 그 통합의 한계 $\square$ |

</details>

<br/>

### 🔹 Chapter 2: 도파민 RPE — 예측 원리의 가장 구체적 형태

> **횡단 질문:** 파블로프 조건화(심리학)·도파민 RPE(신경과학)·TD 오차(AI)는 *정말로* 같은 수학인가, 아니면 닮은 비유인가? 단순 RPE 에서 모델 기반 예측까지 RPE 는 어떻게 계층화되는가? 도파민이 예측 오차 *이외에* 신호하는 것은 무엇이며, 보상 예측은 *어떻게* 더 일반적인 자유에너지 원리의 특수 사례가 되는가?

<details>
<summary><b>TD 학습의 세 언어에서 자유에너지로의 일반화까지 (4개 문서)</b></summary>

<br/>

| 문서 | 핵심 동형성·증거·검증 |
|------|---------------------|
| [01. TD 학습의 세 언어](./ch2-dopamine-rpe/01-td-three-languages.md) | **동일한 수학의 세 번역** — Rescorla–Wagner $\Delta V=\alpha(\lambda-V)$(파블로프) = TD 오차(AI) = 도파민 RPE(신경). Synthesis 의 핵심 통합 $\square$ |
| [02. RPE의 계층적 구조](./ch2-dopamine-rpe/02-hierarchical-rpe.md) | **단순에서 모델 기반으로** — model-free RPE 와 model-based 예측의 위계. 습관과 목표지향의 예측 차이 $\square$ |
| [03. 도파민이 예측 이외에 신호하는 것](./ch2-dopamine-rpe/03-beyond-rpe.md) | **RPE 가 전부가 아닌 이유** — 동기·현저성·운동·불확실성. 도파민의 다중 역할과 RPE 가설의 경계 $\square$ |
| [04. RPE에서 자유에너지로](./ch2-dopamine-rpe/04-rpe-to-free-energy.md) | **특수 사례로의 회수** — 보상 예측이 어떻게 자유에너지(놀라움) 최소화의 한 사례인가. 일반화의 다리 $\square$ |

</details>

<br/>

### 🔹 Chapter 3: 지각·언어·기억의 예측 구조

> **횡단 질문:** 지각·기억·언어·주의·감정은 *서로 다른 능력* 인가, 아니면 *같은 예측 기계의 다른 입력* 인가? 지각이 예측 검증이고 착시가 강한 사전확률의 승리라면, 기억은 예측적 재구성이고 언어는 다음 단어 예측이며 주의는 정밀 가중치, 감정은 내수용 예측 오차인가 — 이 다섯이 *한 원리* 의 변주임을 어디까지 밀어붙일 수 있는가?

<details>
<summary><b>지각·기억·언어·주의·감정의 예측 구조 (5개 문서)</b></summary>

<br/>

| 문서 | 핵심 동형성·증거·검증 |
|------|---------------------|
| [01. 지각 = 예측 검증](./ch3-perception-language-memory/01-perception-as-prediction.md) | **하향 예측·상향 오차** — 착시 = 강한 사전확률이 약한 감각을 압도. 예측 부호화(Rao–Ballard)(→ perception) $\square$ |
| [02. 기억 = 예측적 재구성](./ch3-perception-language-memory/02-memory-as-prediction.md) | **인출 = 예측적 완성** — 거짓기억 = 예측 편향. 기억은 저장이 아니라 재구성(→ memory) $\square$ |
| [03. 언어 = 예측 기계](./ch3-perception-language-memory/03-language-as-prediction.md) | **다음 단어 예측** — 인간 언어 이해의 예측성과 LLM 의 다음 토큰 예측이 같고 다른 지점(→ AI Lab) $\square$ |
| [04. 주의 = 정밀 가중치](./ch3-perception-language-memory/04-attention-as-precision.md) | **정밀도 할당** — 주의가 어떤 예측 오차에 더 높은 정밀도를 부여하는가(→ attention) $\square$ |
| [05. 감정 = 내수용 예측 오차](./ch3-perception-language-memory/05-emotion-as-interoception.md) | **내장 상태 예측** — 내수용 예측 오차가 어떻게 감정 경험을 구성하는가(Seth·Barrett)(→ emotion) $\square$ |

</details>

<br/>

### 🔹 Chapter 4: 능동 추론 — 예측으로서의 행동

> **횡단 질문:** 지각(세계를 예측에 맞추기)과 행동(세계를 예측에 맞게 바꾸기)이 *같은 자유에너지* 의 두 경로라면, 자유에너지 원리의 야망 — 생명·지각·행동·학습·사회가 모두 자유에너지 최소화의 특수 사례라는 주장 — 은 어디까지 정당한가? 예측이 행동을 일으킬 때 자유의지와 어떻게 만나며, 통일 이론의 *진짜 통찰* 과 *과대포장* 은 어떻게 구분되는가?

<details>
<summary><b>능동 추론의 핵심에서 자유에너지의 한계까지 (4개 문서)</b></summary>

<br/>

| 문서 | 핵심 동형성·증거·검증 |
|------|---------------------|
| [01. 능동 추론의 핵심](./ch4-active-inference/01-active-inference-core.md) | **지각과 행동의 통일** — 믿음을 세계에 맞추기(지각) vs 세계를 믿음에 맞추기(행동). 같은 $F$ 의 두 경로 $\square$ |
| [02. 자유에너지 원리의 야망](./ch4-active-inference/02-fep-ambition.md) | **통일의 범위** — 생명·지각·행동·학습·사회가 자유에너지 최소화의 특수 사례인가. 프리스턴의 큰 그림 $\square$ |
| [03. 능동 추론과 행위주체성](./ch4-active-inference/03-agency.md) | **예측이 행동을 일으킬 때** — 정책 예측이 자유의지·행위주체성과 만나는 지점(→ free-will-agency) $\square$ |
| [04. 자유에너지의 한계](./ch4-active-inference/04-fep-limits.md) | **야망과 기여의 정직한 평가** — 통일 이론의 과대포장과 실질적 통찰을 가르는 비판적 검토 $\square$ |

</details>

<br/>

### 🔹 Chapter 5: 예측처리 의식 이론과 그 한계

> **횡단 질문:** 예측처리는 의식의 *내용* 을 어떻게 설명하는가 — 어떤 예측 오차가 의식적 경험에 기여하는가? 각성·수면·마취에서 자유에너지 최소화는 어떻게 달라지는가? 그리고 예측처리가 *설명하지 못하는 것* — 어려운 문제 — 에 대한 응답은? LLM 이 다음 토큰을 예측한다는 것이 의식과 어떻게 관계하는가?

<details>
<summary><b>예측처리 의식 내용에서 AI의 예측과 경험까지 (4개 문서)</b></summary>

<br/>

| 문서 | 핵심 동형성·증거·검증 |
|------|---------------------|
| [01. 예측처리가 설명하는 의식 내용](./ch5-predictive-consciousness/01-predictive-content.md) | **내용의 설명** — 어떤 예측 오차가 의식적 경험에 기여하는가. 예측처리 의식 이론의 강점 $\square$ |
| [02. 자유에너지와 의식 수준](./ch5-predictive-consciousness/02-free-energy-consciousness-level.md) | **각성·수면·마취** — 자유에너지 최소화가 의식 *수준* 에 따라 어떻게 달라지는가(→ altered-states) $\square$ |
| [03. 예측처리가 설명하지 못하는 것](./ch5-predictive-consciousness/03-hard-problem.md) | **어려운 문제** — 예측처리의 응답과 그 한계. 내용을 설명해도 *있다는 것* 은 남는다 $\square$ |
| [04. AI의 예측과 경험](./ch5-predictive-consciousness/04-ai-prediction-experience.md) | **기계의 예측** — LLM 의 다음 토큰 예측이 의식과 맺는 관계. 예측 ≠ 경험의 논변(→ AI Lab) $\square$ |

</details>

<br/>

### 🔹 Chapter 6: 횡단 종합 — 예측 원리의 회수

> **횡단 질문:** L0~L5 에서 예측은 어떻게 변주되었는가, 그 전체 지도는? 예측처리가 경험의 *내용* 을 설명하고 *있다는 것* 은 설명하지 못하는 간극은 어디에 정확히 위치하는가? 그리고 — 하나의 추론 원리가 마음 전체를 관통하는가, *그리고 관통하지 못하는 곳은 어디인가*?

<details>
<summary><b>전체 지도에서 Prediction Everywhere의 종합까지 (3개 문서)</b></summary>

<br/>

| 문서 | 핵심 동형성·증거·검증 |
|------|---------------------|
| [01. 예측 원리의 전체 지도](./ch6-synthesis/01-prediction-map.md) | **L0~L5 의 변주** — 베이즈·도파민·지각·학습·행동에서 $\delta=$ 실제$-$예측이 어떻게 반복되는가의 최종 지도 $\square$ |
| [02. 예측이 경험과 만나는 지점](./ch6-synthesis/02-prediction-meets-experience.md) | **간극의 위치** — 예측처리가 *내용* 을 설명하고 *있다는 것* 을 설명 못 하는 정확한 경계 $\square$ |
| [03. Prediction Everywhere의 종합](./ch6-synthesis/03-synthesis.md) | **관통과 미관통** — 하나의 추론 원리가 마음을 관통한다, 그리고 관통하지 못하는 곳. L6 의 종착 $\square$ |

</details>

---

> 🆕 **2026-06 최신 업데이트**: Ch2-01 의 TD 통합을 Rescorla–Wagner = TD 오차 = 도파민 RPE 의 *수치적 동치* 로 명시 검증, Ch1-01 의 도파민 RPE 를 Schultz (1997) 의 발화율 패턴(예상·생략·조기 보상)으로 정렬, Ch4-02 의 자유에너지 야망을 *진짜 통찰 vs 과대포장* 의 비판적 분리로 강화, Ch3-03 의 언어 예측을 LLM 다음 토큰 예측과의 동치·차이 분석으로 보강, Ch5-03 의 어려운 문제를 예측처리의 정직한 한계로 표시 — **10-섹션 Principle → Boundary → Experience 골격이 전체 24개 문서에서 일관** 됩니다.

## 📐 문서 형식 — Principle → Boundary → Experience (L6 Synthesis 규약)

모든 문서는 **Psyche 표준 10-섹션** 으로 작성되고, 마지막 세 단(Principle · Boundary · Experience)으로 종결됩니다.

| # | 섹션 | 내용 |
|:-:|------|------|
| 1 | 🎯 **횡단 질문** | 이 문서가 회수하는 예측 원리가 어떤 층위들을 연결하는가 |
| 2 | 🌐 **횡단 입력** | 어떤 L0~L5 레포에서 어떤 예측 발견을 가져오는가 |
| 3 | 🔍 **표면의 다양성** | 층위마다 예측이 다르게 *보이는* 이유 |
| 4 | ⚙️ **깊은 동형성** | 층위를 가로지르는 공통 예측 구조를 추출 |
| 5 | 🧪 **수렴 증거** | 동형성을 지지하는 실험·계산 증거 |
| 6 | 🌉 **간극의 위치** | 예측 원리가 *어디서* 경험의 "있다는 것" 에 닿지 못하는가 |
| 7 | 🧬 **원리의 회수** | "예측 오차 최소화" 가 각 층위에서 어떻게 변주되는가 |
| 8 | 🪞 **1인칭** | 예측이 맞고 틀리는 것이 경험으로서 어떻게 느껴지는가 |
| 9 | 📐 **예측·반증** | 예측처리 이론이 내놓는 반증 가능한 예측 |
| 10 | 🤔 **열린 질문** | 예측 원리로 설명되지 않는 미해결 현상 |

```
🧩 Principle  — 이 층위의 예측이 어떻게 더 일반적인 예측 원리의 변주인가
🌉 Boundary   — 예측 원리가 경험의 "있다는 것"을 설명하지 못하는 지점
🪞 Experience — 예측하고, 놀라고, 오차를 느끼는 것이 1인칭으로 어떻게 경험되는가
```

> 📚 **연습문제 총 72개** (24 문서 × 3): **기초 / 심화 / 논문 비평** 3-tier, 모두 `<details>` 펼침 해설. TD 오차 손 계산부터 자유에너지 변분 유도, 능동 추론 정책 평가, 예측 부호화 회로 분석까지 단계적 심화.
>
> 🧮 **수치 실험 총 44개** (문서당 1~3개 — `### 실험 N` 형식): Python 3 + numpy + scipy + matplotlib. TD = 도파민 = 파블로프 통합 · 자유에너지 변분 추론 · 능동 추론 시뮬레이션 · 착시 = 강한 사전확률 모델. 모든 코드 블록은 실행 검증을 거쳤습니다.
>
> 🧭 **푸터 네비게이션**: 각 문서 하단에 `◀ 이전 / 📚 README / 다음 ▶` 링크. 챕터 경계에서도 다음 챕터 첫 문서로 연결.

---

## 🏆 핵심 결과 인덱스

이 레포에서 **완전한 횡단 분석** 또는 **scipy/numpy 검증** 을 제공하는 대표 결과 모음입니다. 각 문서에서 $\square$ 로 종결되는 분석 또는 `results/` 하의 그림을 확인할 수 있습니다.

| 결과 | 서술 | 출처 문서 |
|------|------|----------|
| **도파민 = 보상 예측 오차** | $\delta = r + \gamma V(s') - V(s)$, 발화율 ∝ 오차 | [Ch1-01](./ch1-three-levels/01-signal-prediction.md) |
| **신호·상태·정책의 세 수준** | 예측의 세 층위 구분과 연결 | [Ch1-04](./ch1-three-levels/04-three-levels-unified.md) |
| **TD = 도파민 = 파블로프** | $\Delta V=\alpha(\lambda-V)$ = TD 오차 = RPE 의 수치 동치 | [Ch2-01](./ch2-dopamine-rpe/01-td-three-languages.md) |
| **RPE → 자유에너지** | 보상 예측이 놀라움 최소화의 특수 사례 | [Ch2-04](./ch2-dopamine-rpe/04-rpe-to-free-energy.md) |
| **착시 = 강한 사전확률** | $p(s\mid o)$ 에서 사전확률이 감각을 압도 | [Ch3-01](./ch3-perception-language-memory/01-perception-as-prediction.md) |
| **언어 = 다음 단어 예측** | 인간 예측성과 LLM 다음 토큰의 동치·차이 | [Ch3-03](./ch3-perception-language-memory/03-language-as-prediction.md) |
| **능동 추론의 통일** | 지각·행동이 같은 $F$ 의 두 경로 | [Ch4-01](./ch4-active-inference/01-active-inference-core.md) |
| **자유에너지의 야망과 한계** | 통일 이론의 통찰과 과대포장 분리 | [Ch4-04](./ch4-active-inference/04-fep-limits.md) |
| **예측처리 의식 내용** | 어떤 예측 오차가 의식 경험에 기여하나 | [Ch5-01](./ch5-predictive-consciousness/01-predictive-content.md) |
| **예측 ≠ 경험 (AI)** | LLM 다음 토큰 예측과 의식의 관계 | [Ch5-04](./ch5-predictive-consciousness/04-ai-prediction-experience.md) |
| **예측 원리의 전체 지도** | L0~L5 에서 $\delta=$실제$-$예측의 변주 | [Ch6-01](./ch6-synthesis/01-prediction-map.md) |
| **간극의 위치** | 내용은 설명, 있다는 것은 남는다 | [Ch6-02](./ch6-synthesis/02-prediction-meets-experience.md) |

> 💡 **챕터별 문서·결과 수** (목표):
>
> | 챕터 | 문서 수 | $\square$ 분석 | 수치 실험 | 연습문제 |
> |------|---------|---------------|-----------|----------|
> | Ch1 예측의 세 수준 | 4 | 16 | 8 | 12 |
> | Ch2 도파민 RPE | 4 | 16 | 8 | 12 |
> | Ch3 지각·언어·기억 | 5 | 20 | 10 | 15 |
> | Ch4 능동 추론 | 4 | 16 | 5 | 12 |
> | Ch5 예측처리 의식 | 4 | 16 | 8 | 12 |
> | Ch6 횡단 종합 | 3 | 12 | 5 | 9 |
> | **합계** | **24** | **96** | **44** | **72** |
>
> 연습문제는 문서당 3개 (기초/심화/논문 비평, 모두 `<details>` 해설) 로 총 **72개**, 수치 실험은 문서당 1~3개 (`### 실험 N` 형식) 로 총 **44개** 입니다.

---

## 💻 실험 환경

모든 챕터의 검증은 아래 환경에서 재현 가능합니다 (GPU 불필요 — 순수 numpy/scipy 기반).

```bash
# requirements.txt
numpy==1.26.0
scipy==1.11.0
matplotlib==3.8.0
pandas==2.1.0       # 시행 로그·학습 곡선 정리
jupyter==1.0.0
```

```bash
# 환경 설치 (CPU only, 1분 내)
pip install numpy==1.26.0 scipy==1.11.0 matplotlib==3.8.0 pandas==2.1.0 jupyter==1.0.0

jupyter notebook
```

```python
# 대표 실험 ① — TD 학습 = 도파민 RPE = 파블로프의 통일 (Ch2-01)
import numpy as np

def unified_prediction_error(expected, actual, learning_rate=0.1):
    """
    세 분야의 공통 수학:
    Rescorla–Wagner: ΔV = α(λ − V)      (파블로프, 심리학)
    TD 오차:         δ = r + γV(s') − V(s)  (Sutton–Barto, AI)
    도파민 RPE:      발화율 ∝ δ            (Schultz, 신경과학)
    """
    prediction_error = actual - expected             # δ = 실제 − 예측
    updated_expectation = expected + learning_rate * prediction_error
    return prediction_error, updated_expectation

# 조건화 학습 곡선: 예측이 실제에 수렴하면 RPE(=도파민 신호)는 0으로 사라진다
V, reward = 0.0, 1.0
for trial in range(1, 21):
    delta, V = unified_prediction_error(V, reward)
    if trial in (1, 5, 10, 20):
        print(f"시행 {trial:>2}:  V={V:5.3f}   RPE(δ)={delta:+5.3f}")
# → 학습 초기엔 큰 RPE(도파민 폭발), 학습되면 RPE→0: '기대된 보상엔 도파민이 안 뛴다'

# ─────────────────────────────────────────────
# 대표 실험 ② — 자유에너지 변분 추론: 지각 = F 최소화 (Ch1-02, Ch4-01)
# 대표 실험 ③ — 능동 추론: 지각(믿음 갱신) vs 행동(세계 변경) (Ch4-01)
# 대표 실험 ④ — 착시 = 강한 사전확률이 약한 감각을 압도 (Ch3-01)
```

```python
# 대표 실험 ④ — 착시 모델: 강한 사전확률이 감각 신호를 이긴다 (Ch3-01)
import numpy as np

def illusion_as_strong_prior(sensory_signal, scene_prior, prior_strength=2.0):
    """착시 = 강한 사전확률이 약한 감각 신호를 압도 → 예측처리의 직접 시연."""
    likelihood_strength = 1.0
    posterior = (prior_strength * scene_prior + likelihood_strength * sensory_signal) \
                / (prior_strength + likelihood_strength)
    illusion_magnitude = abs(posterior - sensory_signal)   # 지각 ≠ 실제
    return posterior, illusion_magnitude

percept, mag = illusion_as_strong_prior(sensory_signal=0.2, scene_prior=0.9)
print(f"실제 감각=0.20  사전 예측=0.90  →  지각={percept:.3f}  (착시 크기={mag:.3f})")
# → 강한 사전확률 쪽으로 지각이 끌려간다: '본 것'이 아니라 '예측한 것'을 본다
```

---

## 🗺️ 추천 학습 경로

<details>
<summary><b>🟢 "예측 원리의 직관을 빠르게 잡고 싶다" — 입문 투어 (1주, 약 9~11시간)</b></summary>

<br/>

```
Day 1  Ch1-01  신호 예측 — 도파민 RPE
       Ch1-04  세 수준의 통합
Day 2  Ch2-01  TD 학습의 세 언어 (파블로프=TD=도파민)
       Ch2-04  RPE에서 자유에너지로
Day 3  Ch3-01  지각 = 예측 검증
       Ch3-03  언어 = 예측 기계
Day 4  Ch4-01  능동 추론의 핵심
       Ch4-04  자유에너지의 한계
Day 5  Ch5-01  예측처리가 설명하는 의식 내용
       Ch5-04  AI의 예측과 경험
Day 6  Ch6-01  예측 원리의 전체 지도
       Ch6-03  Prediction Everywhere의 종합
```

</details>

<details>
<summary><b>🟡 "예측 원리를 정복한다" — 이론 집중 (2주, 약 18~22시간)</b></summary>

<br/>

```
1주차 — 세 수준·도파민 RPE·예측 구조
  Day 1  Ch1 전체          신호·상태·정책 예측과 통합
  Day 2  Ch2-01~02         TD 세 언어 + RPE 계층 구조
  Day 3  Ch2-03~04         도파민의 다중 역할 + 자유에너지로
  Day 4  Ch3-01~03         지각·기억·언어의 예측
  Day 5  Ch3-04~05         주의(정밀) + 감정(내수용)

2주차 — 능동 추론·의식·종합
  Day 1  Ch4-01~02         능동 추론 핵심 + 자유에너지 야망
  Day 2  Ch4-03~04         행위주체성 + 한계
  Day 3  Ch5-01~02         의식 내용 + 의식 수준
  Day 4  Ch5-03~04         어려운 문제 + AI의 예측
  Day 5  Ch6 전체          전체 지도 + 간극 + 종합
```

</details>

<details>
<summary><b>🔴 "예측의 과학을 완전 정복한다" — 전체 정복 (6주, 약 30~38시간 + 실험 재현 8~10시간)</b></summary>

<br/>

```
1주차  Chapter 1 — 예측의 세 수준
        → 신호·상태·정책 예측의 구분
        → 자유에너지가 세 수준을 묶는 방식
        → 통합의 한계 내면화

2주차  Chapter 2 — 도파민 RPE
        → Rescorla–Wagner = TD = 도파민 RPE 손/수치 동치
        → model-free / model-based 위계
        → RPE → 자유에너지 일반화

3주차  Chapter 3 — 지각·언어·기억
        → 예측 부호화(Rao–Ballard) 회로
        → 착시 = 강한 사전확률 손 분석
        → 언어 예측과 LLM 다음 토큰 비교

4주차  Chapter 4 — 능동 추론
        → 지각/행동의 자유에너지 통일
        → 자유에너지 원리의 야망 평가
        → 통일 이론의 과대포장/통찰 분리

5주차  Chapter 5 — 예측처리 의식
        → 의식 내용의 예측처리 설명
        → 각성·수면·마취의 자유에너지
        → 어려운 문제와 AI의 예측

6주차  Chapter 6 — 횡단 종합
        → L0~L5 예측 변주의 전체 지도
        → 예측이 경험과 만나는/못 만나는 지점
        → "관통과 미관통" 의 최종 종합
```

</details>

---

## 🔗 연관 레포지토리

| 레포 | 주요 내용 | 횡단 입력 | 층위 |
|------|----------|-----------|------|
| [information-prediction-distilled](https://github.com/iq-ai-lab) | 베이즈 추론 · 자유에너지 · 예측처리의 수학 | **Ch1, Ch2-04, Ch4** | L0 |
| [neuromodulation-arousal-distilled](https://github.com/iq-ai-lab) | 도파민 RPE 의 신경 구현 · 신경조절 | **Ch1-01, Ch2 전체** | L1 |
| [neurons-neural-codes-distilled](https://github.com/iq-ai-lab) | 예측 부호화 · 하향 예측·상향 오차 회로 | **Ch3-01, Ch3-04** | L1 |
| [perception-distilled](https://github.com/iq-ai-lab) | 지각 = 예측 검증 · 착시 = 강한 사전확률 | **Ch3-01** | L2 |
| [learning-decision-distilled](https://github.com/iq-ai-lab) | 강화학습 = TD · 파블로프 조건화 = 예측 갱신 | **Ch2 전체, Ch3-02** | L2 |
| [theories-of-consciousness-distilled](https://github.com/iq-ai-lab) | 예측처리 의식 이론 · 자유에너지와 의식 수준 | **Ch5 전체** | L4 |
| [free-will-agency-distilled](https://github.com/iq-ai-lab) | 능동 추론 = 행동으로 예측 실현 · 행위주체성 | **Ch4-03** | L5 |
| **IQ AI Lab** | RL TD 학습 · LLM 다음 토큰 예측 · 모델 기반 계획 | **Ch2, Ch3-03, Ch5-04** | 직결 |

> 💡 이 레포는 **L6 Synthesis** — L0~L5 의 *예측* 발견을 횡단으로 회수합니다. **information-prediction**(베이즈·자유에너지의 수학)을 먼저 익히면 Chapter 1~2 가, **perception·learning-decision** 을 익히면 Chapter 3 이, **theories-of-consciousness·free-will-agency** 를 익히면 Chapter 4~5 가 자연스럽습니다. 그리고 이 레포의 통합 — TD = 도파민 = 파블로프, 자유에너지의 야망과 한계 — 은 **IQ AI Lab** 의 RL·LLM·모델 기반 계획과 *직접* 만납니다.

---

## 📖 Reference

### 🏛️ 예측 원리의 토대
- **"The Free Energy Principle: a unified brain theory?"** (Karl Friston, 2010, *Nat Rev Neurosci*) — 자유에너지 원리의 핵심 논문, *이 레포의 통일 축*
- **Surfing Uncertainty** (Andy Clark, 2015) — 예측처리의 인지과학 정전
- **"Whatever Next? Predictive brains, situated agents, and the future of cognitive science"** (Andy Clark, 2013, *BBS*) — 예측처리 선언

### 🔬 도파민 RPE·TD 학습
- **"A Neural Substrate of Prediction and Reward"** (Schultz, Dayan & Montague, 1997, *Science*) — 도파민 RPE 원전
- **Reinforcement Learning: An Introduction** (Sutton & Barto, 2018) — TD 학습의 표준 교과서
- **"A theory of Pavlovian conditioning"** (Rescorla & Wagner, 1972) — 조건화 = 예측 갱신의 고전

### 🧠 예측 부호화·지각
- **"Predictive coding in the visual cortex"** (Rao & Ballard, 1999, *Nat Neurosci*) — 예측 부호화의 신경 구현
- **"The free-energy principle: a rough guide to the brain?"** (Karl Friston, 2009, *TiCS*) — 능동 추론 입문

### 🌀 예측과 의식·경험
- **"Interoceptive inference, emotion, and the embodied self"** (Anil Seth, 2013, *TiCS*) — 감정 = 내수용 예측 오차
- **Being You** (Anil Seth, 2021) — 예측처리 의식 이론의 대중적 종합
- **The Predictive Mind** (Jakob Hohwy, 2013) — 예측처리 의식 이론의 철학적 정초

---

<div align="center">

**🧠 The Knowledge Pentad**

*Psyche 의 모든 문서는 예측이 제 자리를 얻는 다섯 가지 방식으로 검증된다 —*

**🧩 Principle** (예측 오차 최소화의 변주인가) · **🔬 Converge** (여러 층위의 증거가 동형성으로 수렴하는가) · **🌉 Boundary** (경험의 "있다는 것" 앞에서 정직한가) · **🪞 Experience** (놀라움·오차를 1인칭으로 표시하는가) · **📐 Falsify** (반증 가능한 예측을 내놓는가)

<br/>

**⭐️ 도움이 되셨다면 Star 를 눌러주세요!**

Made with 🧠 by [IQ AI Lab](https://github.com/iq-ai-lab) · **Psyche** Layer 6 — Synthesis

<br/>

***Explain it, don't explain it away. 설명하되, 경험을 지우지 않는다.***

<br/>

*"도파민이 보상 예측 오차를 신호하고 · 지각이 세계에 대한 예측을 검증하며 · 언어 모델이 다음 토큰을 예측하고 · 자유에너지 원리가 놀라움을 최소화할 때 — 이 네 '예측' 이 $\delta=$실제$-$예측이라는 *하나의 추론 원리* 의 다른 표현임을 끝까지 추적하되, 예측 오차가 아무리 정밀해도 '놀라움이 *느껴진다*' 는 것은 남는다는 간극을 정직하게 표시하는 것은 다르다."*

</div>
