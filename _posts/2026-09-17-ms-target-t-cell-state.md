---
title: MS에서 B세포를 제거하면 왜 T세포가 변할까? — TARGET T-cell state
date: 2026-09-18T00:54:25+09:00
---

**Anti-CD20 치료는 B세포를 줄이는 데서 끝나지 않을 수 있다.** 이 연구는 B세포 제거 뒤 감소하는 염증성 T세포 상태를 찾아, 혈액·CSF·만성 MS 병변의 자료를 연결했다.

핵심 제안은 **B세포가 특정 T세포 상태를 유지하고, 이 T세포가 CNS로 이동해 만성 염증에 기여한다**는 모델이다. 여러 자료가 같은 방향을 지지하지만, 전체 인과 경로를 직접 증명한 연구는 아니다.[1]

### 1. 연구 설계

| Dataset | Participants | Main question |
| --- | --- | --- |
| Ocrelizumab discovery cohort | 14 treatment-naive patients: RR-high 5, RR-low 4, PPMS 5 | Which immune states change after B-cell depletion? |
| Blood–CSF validation | MS/CIS 21; healthy controls 9 | Is TARGET enriched in CSF? |
| Paired RNA/TCR validation | MS/CIS 12; healthy controls 3 | Is TARGET associated with CSF-enriched clones? |
| Post-mortem brain validation | SPMS 12; healthy controls 6 | Is TARGET present in chronic lesion rims? |
| Natalizumab validation | RRMS 9 | Does blocking trafficking increase TARGET in blood? |

*Author-created summary of study datasets. In the blood–CSF dataset, paired samples were available for 18/21 MS/CIS participants and all controls.*

- **발견 단계:** ocrelizumab 전, 첫 투여 2주 후, 이후 재투여 직전의 혈액을 CITE-seq로 분석했다.
- **측정:** 단일세포 RNA와 표면 단백질을 함께 확인했다. 분석 세포는 **264,512개**지만 독립적인 환자 수는 **14명**이다.
- **투여 맥락:** CD19+ B세포 재출현에 맞춘 extended-interval dosing이었다. 후기 검체는 고정된 동일 시점이 아니다.
- **분석의 특징:** CD4/CD8 같은 세포 분류만 비교하지 않고, 여러 세포에 걸쳐 나타나는 연속적인 유전자 발현 프로그램을 추적했다.

### 2. TARGET은 어떤 세포인가?

**TARGET = Trafficking, Activated, Residency-primed, Granzyme K-Effector T cell state**

새로운 독립 세포 계통이라기보다, 아래 **세 가지 프로그램을 합친 전사 상태**다. 높은 점수의 세포는 주로 CD8+ 및 CD4+ memory T세포였다.

| Component | Representative features | Interpretation |
| --- | --- | --- |
| Cytotoxic inflammatory | GZMK, GZMA, EOMES, IFNG, CCL3/4/5 | Inflammatory effector function |
| Th1-like / trafficking / residency | CXCR3, ITGA4, PRDM1, ZNF683 | Migration and tissue-residency priming |
| Activation signalling | FOS/JUN, NF-κB-related genes, CD69, TNF | Ongoing T-cell activation |

- **Granzyme K가 중요:** 전형적인 granzyme B/perforin 중심의 직접 세포 살상과 비교해, 염증 신호 전달 성격이 강조된다.
- **표면 단백질도 일치:** 활성화, 이동, 조직 잔류 관련 표지자들이 함께 증가했다.
- **주의:** 이 표현형만으로 모든 TARGET-high 세포가 병원성이거나 EBV 특이적이라고 단정할 수 없다.

### 3. 왜 ‘B cell-dependent’라고 해석했나?

[![Figure 4. TARGET phenotype and longitudinal changes](/assets/ms-target-2026/figure-4.jpg)](/assets/ms-target-2026/figure-4.jpg)

*Original Figure 4. TARGET transcriptional programs, surface markers and treatment-associated changes. Click to enlarge.*

**Figure 4F가 핵심이다.**

- **2주 후:** TARGET 점수의 유의한 감소가 없었다 (**p = 0.176**).
- **후기:** 치료 전보다 유의하게 감소했다 (**p = 1.16 × 10⁻⁴**).
- TARGET-high memory T세포 중 **CD20-dim은 1.23%**에 불과했다.

**저자의 해석:** 약물이 이 T세포를 직접 제거했다기보다, B세포가 제공하던 항원 자극·생존 신호 등이 줄어든 **간접 효과**와 더 잘 맞는다.

**아직 남은 질문:** T세포가 죽은 것인지, 활성 상태가 바뀐 것인지, 해당 상태로 새로 분화하는 세포가 줄었는지는 구분되지 않았다. 점수 감소를 곧바로 절대 세포 수 감소와 동일시해서는 안 된다.

또한 치료 전 TARGET 점수는 RR-high군에서 RR-low군보다 높았다 (**p = 0.031**). 그러나 각각 5명과 4명의 비교이므로, 개인의 재발을 예측하는 검사로 검증된 것은 아니다.

### 4. 혈액에서 CNS 병변까지 연결되는가?

[![Figure 5. TARGET in CSF, expanded clonotypes and brain lesions](/assets/ms-target-2026/figure-5.jpg)](/assets/ms-target-2026/figure-5.jpg)

*Original Figure 5. Cross-compartment validation in CSF, TCR clonotypes and post-mortem brain tissue. Click to enlarge.*

- **CSF:** MS/CIS에서는 혈액보다 TARGET 신호가 높았고, 건강 대조군에서는 같은 차이가 유의하지 않았다.
- **TCR:** CSF에 상대적으로 많이 확장된 clonotype에서 TARGET 신호가 높았다.
- **뇌 조직:** 만성 병변의 rim과 주변 NAWM에서 높은 신호가 관찰됐다. 본문에서는 chronic active rim과 lesion core, 그리고 healthy white matter 사이의 유의한 차이를 보고했다.

**의미:** 재발성 질환의 말초 면역 상태와 진행성 질환의 만성 병변을 연결하는 후보가 된다.

**한계:** 서로 다른 코호트의 자료를 연결한 것이다. **같은 환자의 혈액 T세포가 뇌로 들어가 병변의 tissue-resident T세포가 되는 과정은 직접 추적하지 못했다.**

*원고 확인 사항: 제공된 accepted manuscript의 Figure 5G에 표시된 p값은 본문의 혼합모형 비교 p값과 일치하지 않는다. 그림은 원문 그대로 실었으며, 두 값을 같은 분석 결과로 합쳐 해석하지 않았다.*

### 5. EBV는 어디에 들어가는가?

- 재분석한 기존 TCR 연구에서 **CSF-enriched clonotype 3개가 EBV 특이적**인 것으로 확인돼 있었다.
- 이 연구는 해당 clonotype들이 포함된 CSF-enriched 집단과 TARGET 상태의 연관성을 보여준다.
- 이를 바탕으로 저자들은 **잠복 EBV를 가진 memory B세포가 T세포를 반복 자극할 가능성**을 제안한다.

**구분할 점:** 모든 TARGET 세포의 항원이 EBV라는 뜻은 아니다. CNS에서의 재자극이 EBV 감염 B세포 때문인지, CNS 항원과의 교차반응 때문인지도 아직 가설이다.

### 6. Natalizumab에서는 왜 혈액 신호가 오히려 증가했나?

[![Figure 6. TARGET enrichment during natalizumab treatment](/assets/ms-target-2026/figure-6.jpg)](/assets/ms-target-2026/figure-6.jpg)

*Original Figure 6. Circulating TARGET signature before and during natalizumab treatment. Click to enlarge.*

9명의 별도 자료에서 natalizumab 후 혈액의 TARGET 점수가 증가했다 (**p = 0.00319**).

| Therapy | Blood TARGET signal | Proposed explanation |
| --- | --- | --- |
| Ocrelizumab | Decreased at later time points | Reduced B-cell-dependent support |
| Natalizumab | Increased | Restricted trafficking into tissues, including the CNS |

**혈액에서 증가했다고 질환이 악화됐다는 뜻은 아니다.** 이동을 차단하면 혈액에 남는 세포가 늘 수 있다. 서로 다른 기전의 치료에서 관찰된 반대 방향의 변화가 저자 모델을 뒷받침한다.

다만 natalizumab 결과 역시 실제 CNS 이동을 직접 측정한 실험은 아니다.

### 7. 이 논문이 보여준 것과 아직 못 보여준 것

| Supported by these data | Not yet established |
| --- | --- |
| A reproducible treatment-associated T-cell signature | A single causal B–T interaction mechanism |
| Association with CSF enrichment and chronic lesion niches | Direct blood-to-brain lineage tracing |
| A link to a subset of EBV-specific clonotypes | Universal EBV specificity of TARGET cells |
| A candidate therapeutic pathway | Benefit from selectively targeting TARGET cells |
| Association with disease activity | A validated diagnostic or response biomarker |

- **임상적 함의:** anti-CD20의 작용을 항체 감소뿐 아니라 **B–T세포 상호작용 변화**로 이해하게 한다.
- **치료 실패 자료는 1명:** B세포가 고갈됐는데도 TARGET 감소가 뚜렷하지 않은 사례는 흥미롭지만 탐색적 관찰이다.
- **치료 전략의 제안:** 광범위한 세포 제거 대신 병원성 상태를 선택적으로 조절하는 방향이다. 아직 임상적 유효성을 검증한 단계는 아니다.

### 세 줄 요약

1. **B세포 제거 뒤 지연되어 감소하는 TARGET T세포 상태를 발견했다.**
2. **이 신호는 CSF 확장 clonotype과 만성 MS 병변에도 나타나, 말초 면역과 CNS 만성 염증을 연결한다.**
3. **설득력 있는 기전 모델이지만, EBV–B세포–T세포–병변의 전체 인과 경로와 치료 표적으로서의 효용은 추가 검증이 필요하다.**

### Reference

1. Farooq R, Cutler B, Pisa M, et al. Multimodal discovery of a pathogenic B cell-dependent T cell state in multiple sclerosis. *Brain.* 2026. Accepted manuscript. doi:[10.1093/brain/awag303](https://doi.org/10.1093/brain/awag303).

*첨부된 accepted manuscript 전문을 바탕으로 작성했다. 표는 요약 재구성이며, Figures 4–6은 영어 원본을 내용 변경 없이 재현했다. © The Authors 2026, Oxford University Press on behalf of The Guarantors of Brain, [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Figures 5–6 include BioRender elements credited in the original manuscript: Farooq, R. (2026), [BioRender](https://BioRender.com/bte9vv0).*
