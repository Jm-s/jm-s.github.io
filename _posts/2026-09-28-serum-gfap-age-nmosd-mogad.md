---
title: 혈청 GFAP와 나이로 NMOSD와 MOGAD를 구분할 수 있을까?
date: 2026-09-28T09:36:21+09:00
---

**발작 후 90일 이내의 혈청 GFAP와 나이를 조합하면 AQP4-IgG 양성 NMOSD와 MOGAD를 잘 구분했다. 하지만 double-seronegative NMOSD의 정체를 규명하거나, 항체검사를 대체한 연구는 아니다.**

Rival 등의 *European Journal of Neurology* 연구는 항체 결과를 기다리는 동안 사용할 수 있는 **보조 감별진단 지표**를 탐색했다.[1]

### 핵심 세 가지

- **AQP4-NMOSD vs MOGAD:** sGFAP + age 모델의 보정 AUC는 **0.939**.
- **Double-seronegative NMOSD:** 최근 발작군에서 GFAP가 높았지만 **8명**에 불과했고, AQP4 양성군과 구별되지 않았다는 결과만으로 같은 병태생리를 증명하지는 못했다.
- **임상 적용:** 내부 검증은 했지만 외부 검증은 없다. 현재는 항체검사·MRI·임상 양상을 보완할 후보 지표다.

### 1. 무엇을 어떻게 조사했나?

프랑스 **OFSEP 코호트의 보관 혈청을 이용한 후향적 탐색 연구**다. 2014–2018년 등록되고 최소 24개월간 전향적으로 추적된 환자들의 자료를 분석했다.

| Study feature | Details |
| --- | --- |
| Total cohort | 640 patients |
| AQP4-IgG-positive NMOSD | 88 |
| Double-seronegative NMOSD | 28 |
| MOGAD | 61 |
| CIS / RRMS / PPMS | 64 / 237 / 162 |
| Recent attack | Symptom onset ≤90 days before sampling |
| Recent-attack subgroup | 240 patients |
| Assay | Simoa HD-1, Neurology 4-Plex A |
| Internal validation | 1,000 bootstrap resamples |

- DN-NMOSD는 **2015 IPND 기준**을 충족하고 전문가 위원회의 검토를 거쳤다.
- AQP4-IgG와 MOG-IgG는 **live cell-based assay로 최소 한 차례** 검사했다.
- **sGFAP:** 주로 성상세포 손상을 반영하는 혈청 단백질.
- **sNfL:** 신경축삭 손상을 반영하는 혈청 단백질.
- **GFAP 농도 측정과 anti-GFAP 항체검사는 전혀 다른 검사**다. 이 연구는 anti-GFAP 항체를 검사하지 않았다.

### 2. 발작 후 실제 수치는 얼마나 달랐나?

아래는 **최근 발작 후 채혈한 환자만** 비교한 결과다. 전체 640명에서 얻은 평균적인 진단 성능으로 읽으면 안 된다.

| Recent-attack group | n | sGFAP, pg/mL, median [IQR] | sNfL, pg/mL, median [IQR] |
| --- | ---: | --- | --- |
| AQP4-NMOSD | 21 | 215.9 [162.4–635.3] | 34.1 [21.9–103.2] |
| DN-NMOSD | 8 | 175.8 [66.4–484.9] | 57.7 [8.5–312.7] |
| MOGAD | 19 | 71.1 [42.6–153.3] | 13.6 [7.9–36.6] |
| CIS | 34 | 64.3 [44.0–85.9] | 9.3 [6.3–14.2] |
| RRMS | 158 | 74.6 [56.3–105.9] | 11.5 [7.3–20.5] |

*Selected data from Table 2.[1] These are group distributions, not diagnostic cutoffs.*

- **AQP4-NMOSD의 GFAP는 MOGAD·CIS·RRMS보다 유의하게 높았다.**
- AQP4-NMOSD에서는 최근 발작군이 안정군보다 GFAP와 NfL 모두 높았다.
- DN-NMOSD도 발작군에서 중앙값이 높았지만, 안정군과의 차이는 **GFAP p=0.3, NfL p=0.2**로 유의하지 않았다.
- 이 비교는 **동일 환자의 발작 전후 변화량을 측정한 결과가 아니라, 발작군과 안정군 사이의 비교**다.

[Original Figure 1 — biomarker distributions](https://www.researchgate.net/figure/sNfL-and-sGFAP-concentration-among-different-populations-of-NMO-and-MS-patients-Values_fig1_414819586)

**그림을 읽는 포인트:** A/B는 전체 환자, C/D는 발작 여부를 나눈 분포다. DN-NMOSD는 분포가 넓고 다른 군과 겹친다. 중앙값 하나보다 이 겹침과 표본 수가 중요하다.

### 3. GFAP에 나이를 더하면 진단 성능은?

최종 다변량 모델에는 **log(sGFAP)와 나이**가 남았다. NfL은 단변량 분석에서는 유용했지만 최종 모델에는 포함되지 않았다.

| Diagnostic comparison | Optimism-corrected AUC [95% CI] |
| --- | --- |
| AQP4-NMOSD vs MOGAD | 0.939 [0.910–0.982] |
| AQP4-NMOSD vs DN-NMOSD/MOGAD/RRMS/CIS | 0.950 [0.918–0.987] |
| AQP4-NMOSD + DN-NMOSD vs MOGAD | 0.863 [0.776–0.977] |

*Multivariable models using age and log(sGFAP); Table 3.[1] PPMS was not included in these recent-attack diagnostic comparisons.*

- **AUC 0.939는 환자 93.9%를 정확히 진단했다는 뜻이 아니다.** 두 진단군을 점수로 얼마나 잘 구별하는지 나타내는 지표다.
- DN-NMOSD를 AQP4 양성군에 합치면 MOGAD와의 구분 성능은 낮아졌다.
- **DN-NMOSD 단독 vs MOGAD 모델의 검증된 성능**을 제시한 것은 아니다. 합친 군의 AUC를 DN-NMOSD 자체의 성능으로 해석하면 안 된다.

[Original Figure 3 — age–GFAP probability heatmaps](https://www.researchgate.net/figure/Probability-heatmaps-of-belonging-to-one-diagnostic-group-against-other-groups_fig3_414819586)

**그림을 읽는 포인트:** 같은 GFAP라도 나이에 따라 모델의 추정 확률이 달라진다. 다만 이 확률은 연구에 포함된 질환들의 상대적 구성에 영향을 받으므로, 다른 병원의 환자에게 그대로 적용할 수 있는 확정적 진단 확률은 아니다.

### 4. Double-seronegative NMOSD에 대해 무엇을 말해주나?

이전 [double-seronegative NMOSD 리뷰](/posts/double-seronegative-nmosd)에서 다룬 질문과 직접 연결되는 부분이다.

**이번 연구가 보여준 관찰**

- 전체 코호트에서는 AQP4 양성군의 GFAP가 DN-NMOSD보다 높았다: **145.5 vs 92.3 pg/mL, p=0.005**.
- 그러나 **최근 발작군**에서는 GFAP·NfL·나이·EDSS 등의 단변량 지표로 두 군을 유의하게 구별하지 못했다.
- DN-NMOSD에서 GFAP와 장애 정도의 연관성이 관찰되어, 이 군에서도 성상세포 손상이 중요할 가능성을 제시했다.

**여기서 넘어가면 안 되는 해석**

| Question | What this study supports |
| --- | --- |
| Astrocyte injury in DN-NMOSD? | A plausible signal in this cohort |
| Same mechanism as AQP4-NMOSD? | Not established |
| A distinct, uniform DN-NMOSD disease? | Not established |
| A different immune-cell or cytokine profile? | Not investigated |
| Reliable DN-NMOSD vs MOGAD classification? | Not independently validated |

GFAP는 **손상의 결과를 반영하는 지표**다. 같은 세포가 손상되었다고 해서 그 손상을 일으킨 항체, 보체 활성화, T세포 반응까지 같다고 결론낼 수 없다.

특히 다음 세 가지가 중요하다.

1. **표본 수:** 최근 발작 DN-NMOSD는 8명이다. 차이를 발견하지 못한 결과는 동등성의 입증이 아니다.
2. **기존 연구와의 불일치:** 저자들도 DN-NMOSD의 GFAP가 더 낮았던 이전 연구들과 차이가 있음을 인정한다. 환자군의 이질성과 채혈 시점 등이 설명 후보로 남는다.
3. **감별진단의 잔여 문제:** anti-GFAP 항체를 검사하지 않아 GFAP astrocytopathy가 일부 포함되었을 가능성을 완전히 배제하지 못했다.

**따라서 “DN-NMOSD에서도 AQP4 양성 NMOSD와 겹치는 성상세포 손상 양상이 있을 수 있다”까지는 가능하지만, “두 질환은 같다” 또는 “DN-NMOSD는 하나의 독립 질환이다”라는 결론은 어렵다.**

### 5. 임상적으로 어디까지 활용할 수 있을까?

저자들은 항체 결과를 기다리는 상황에서 GFAP와 나이가 **초기 감별과 신속한 치료 판단을 보조할 가능성**을 제안했다. 하지만 이 연구에서 GFAP 점수에 따라 치료를 배정하거나, 그 전략이 예후를 개선하는지 시험하지는 않았다.

- **채혈 시점:** ‘발작 후 90일 이내’는 넓은 범위다. 실제 채혈 중앙값은 주요 세 군에서 약 22–41일로, 응급실 도착 직후의 성능과 동일하지 않다.
- **외부 검증:** bootstrap 내부 검증만 시행했다. 다른 국가·인종·질환 구성에서 재현되는지 확인해야 한다.
- **교란 요인:** BMI와 신기능 자료가 없어 보정하지 못했고, 병변의 위치·범위와 치료의 영향을 충분히 반영하지 못했다.
- **통계적 한계:** 탐색 연구로 다중비교 보정을 하지 않았고, 작은 하위군에서 변수 선택을 시행했다.
- **치료 연결:** 높은 점수만으로 PLEX를 결정하거나 낮은 점수로 치료를 늦추는 기준은 검증되지 않았다.

**읽고 남는 점:** 이 연구의 강점은 GFAP를 나이와 발작 시점까지 고려하는 감별 도구로 발전시켰다는 것이다. DN-NMOSD에 대해서는 면역학적 정체를 규명했다기보다, 성상세포 손상의 이질성을 더 연구해야 한다는 근거를 보탰다.

### Reference

1. Rival M, Rollot F, Laurent-Chabalier S, et al. Serum GFAP and age accurately distinguish AQP4-IgG positive and double seronegative NMOSD from MOGAD after a recent attack. *Eur J Neurol.* 2026;33:e70767. doi:[10.1111/ene.70767](https://doi.org/10.1111/ene.70767).

*Wiley가 ResearchGate에 제공한 공개 전문을 바탕으로 정리했다. 원문은 CC BY-NC 4.0으로 공개되어 있다. 표는 원문 Tables 1–3에서 주요 수치를 선별해 재구성했으며, 원본 그림은 링크로 연결했다. 별도로 표시한 해석은 연구 결과의 범위를 평가한 리뷰 의견이다.*
