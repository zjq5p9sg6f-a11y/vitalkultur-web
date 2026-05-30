# CARLON Equine — Citations Bibliography for Validation

**Generated:** 2026-05-30
**Purpose:** Master-list of every scientific citation used in the
CARLON Equine viewer / web landing / print PDF. Submit to external
scientific validator (Comet/Perplexity-Reason or equivalent) for
line-by-line verification of:

1. **Existence** — does the paper exist as cited?
2. **Attribution** — does the claim we attach to it actually come from this paper?
3. **Equine applicability** — is the human-data finding (where applicable) validly transferred to horses?
4. **Cutoff/formula accuracy** — do our numeric thresholds match the source?

---

## Status Legend
- ✅ **CONFIRMED** — Comet confirmed existence + attribution match
- 🟡 **TO VERIFY** — Citation likely real, need bibliographic confirmation + cutoff/method match
- 🔴 **UNCERTAIN** — Short-form reference, may not match a real paper, or may be conflated
- ⚠️ **CAUTION** — Comet flagged claim as scientifically problematic (e.g. SD1/SD2 sympathetic interpretation)

---

## 1. Task Force 1996 · ✅ CONFIRMED

**Full citation:**
Task Force of the European Society of Cardiology and the North American Society of Pacing and Electrophysiology. *Heart rate variability: standards of measurement, physiological interpretation, and clinical use.* Circulation. 1996;93(5):1043-1065. PMID: 8598068.

**Used for:** RMSSD, SDNN, pNN50, TI definitions; Frequency-Domain VLF/LF/HF bands (human standard); Time-Domain primary metrics.

**Where in code:**
- Method-Transparency banner
- Print Methodology page (Time-Domain section)
- Multiple chart panels source-lines
- Demo crossValidation `rmssdMs.primary.referenceCitation`

**Validation needed:** ✅ Existence confirmed by Comet. Note Comet's caveat — Task Force defines HUMAN bands; equine bands (Visser 2002) must be used separately, NOT Task Force human bands for equine PSD.

---

## 2. Lipponen-Tarvainen 2019 · ✅ CONFIRMED

**Full citation:**
Lipponen JA, Tarvainen MP. *A robust algorithm for heart rate variability time series artefact correction using novel beat classification.* J Med Eng Technol. 2019;43(3):173-181. PMID: 31314618.

**Used for:** Beat classification (Normal / Ectopic / Long / Short), adaptive RR-correction threshold (thresholdSD=4), windowBeats=91.

**Where in code:**
- Method-Transparency banner
- Print Methodology page (Beat Detection)
- Provenance.wasGeneratedBy.usedAlgorithms
- Tachogram panel source-line

**Validation needed:** Confirm our parameter values (thresholdSD=4, windowBeats=91) match paper's recommended defaults.

---

## 3. Visser 2002 · ✅ CONFIRMED (with caveat)

**Full citation:**
Visser EK, van Reenen CG, van der Werf JTN, Schilder MBH, Knaap JH, Barneveld A, Blokhuis HJ. *Heart rate and heart rate variability during a novel object test and a handling test in young horses.* Physiol Behav. 2002;76(2):289-296.

**ALTERNATIVE (likely the one we actually want):**
Possibly Visser EK et al. 2002 Equine Vet J 34:280-288 — if exists. NEED TO CONFIRM which Visser 2002 paper is the source of the LF 0.01-0.07 / HF 0.07-0.6 Hz equine bands.

**Used for:** Equine PSD bands VLF 0–0.01 / LF 0.01–0.07 / HF 0.07–0.6 Hz; RMSSD reference range 60-180 ms.

**Where in code:**
- Method-Transparency banner (PSD bands)
- Print Methodology page (Frequency-Domain & nonlinear)
- Print Cover indicator citation
- demoData crossValidation
- Multiple chart sources

**Validation needed:** ⚠️ Confirm WHICH Visser 2002 paper defines the equine bands LF 0.01-0.07 / HF 0.07-0.6 Hz. Comet linked PubMed 8884694 which is a 1994 Hamlin paper, not Visser 2002. The bands may have a different primary source — possibly Hamlin et al 1994 OR Physick-Sheard et al 2000. Need definitive bibliographic check.

---

## 4. Reef 1998 · 🟡 TO VERIFY (citation format unclear)

**Likely full citation:**
Reef VB. *Echocardiographic findings in horses with cardiac dysrhythmias* OR *Electrocardiography and echocardiography in the exercising horse.* In: Reef VB (ed.), Equine Diagnostic Ultrasound. WB Saunders, 1998. Chapter on cardiac arrhythmias OR Vet Clin North Am Equine Pract. 1998;14(1):21-43 ("Cardiovascular diagnostics and management").

**Used for:** Vagal AV-blocks (2°/Mobitz I) as physiological in resting horses; Mean HR reference range 28-44 BPM.

**Where in code:**
- Method-Transparency banner (AV-block classification)
- Print Methodology page
- Print Cover indicator citation
- AV-Blocks panel source
- Executive Summary findings ("Mean HR 38 BPM (Reef 1998: 28-44 BPM)")

**Validation needed:** 🔴 CRITICAL — need the EXACT Reef 1998 publication that states:
(a) the 28-44 BPM resting HR range AND
(b) the vagal AV-block-as-physiological-in-resting-horse claim.
These may be in different Reef sources. Comet specifically flagged this as needing full bibliographic confirmation.

---

## 5. Stucke 2015 · 🟡 TO VERIFY

**Likely full citation:**
Stucke D, Große Ruse M, Lebelt D. *Measuring heart rate variability in horses to investigate the autonomic nervous system activity – Pros and cons of different methods.* Appl Anim Behav Sci. 2015;166:1-10.

**Used for:** DFA-α₁ equine zones (<0.5 / 0.5-0.75 / 0.75-1.15 / 1.15-1.5 / >1.5); equine HRV methodology review.

**Where in code:**
- Method-Transparency banner (RMSSD reference range)
- Print Methodology (DFA equine zones)
- DFA Chart panel
- Multiple sources

**Validation needed:** 🔴 CRITICAL — confirm the DFA-α₁ equine zone boundaries are FROM this paper (vs. a default we adopted). The 5-zone cutoffs need source-text match.

---

## 6. Mitchell 2018 · ✅ CONFIRMED (cutoff needs confirmation)

**Full citation:**
Mitchell KJ, Kraus MS, Bonagura JD, Reimer JM, Schwarzwald CC, van Loon G, Verheyen T, Schober KE, Decloedt A, Sleeper MM. *Heart rate variability parameters in horses distinguish atrial fibrillation from sinus rhythm before and after successful electrical cardioversion.* J Vet Intern Med. 2018;32(3):1232-1240. PMID: 28323361.

(Note: PMID 28323361 is actually 2017 publication date in PubMed indexing — check exact year carefully.)

**Used for:** AFib screening via RMSSD > 302 ms threshold; equine RR-irregularity AFib detection.

**Where in code:**
- Method-Transparency banner (AFib screening)
- Print Methodology
- Print Cover indicator
- Demo data interpretation

**Validation needed:** 🟡 Confirm the **RMSSD > 302 ms cutoff** is explicitly stated in the Mitchell 2018 paper (vs. derived from their data by us). Comet specifically warned: "Cutoffs müssen aus genau dieser Arbeit stammen".

---

## 7. Brennan 2001 · ✅ CONFIRMED — but ⚠️ CAUTION on usage

**Full citation:**
Brennan M, Palaniswami M, Kamen P. *Do existing measures of Poincaré plot geometry reflect nonlinear features of heart rate variability?* IEEE Trans Biomed Eng. 2001;48(11):1342-1347. PMID: 11686633.

**Used for:** Poincaré SD1, SD2, SD1/SD2 ratio; ellipse-fit geometry on Poincaré plot.

**Where in code:**
- Poincaré chart panel source
- Cross-validation: "Poincaré SD1 × √2" as RMSSD alternative
- Print Methodology

**Validation needed:** ⚠️ Comet flagged: Brennan 2001 is actually a CRITIQUE of using SD1/SD2 as sympathetic regulation indicators. We must NOT use this paper to claim "SD1 = parasympathetic, SD2 = sympathetic". Currently checking if our code makes such claims (probably not — we use SD1/SD2 as geometric descriptors only). VERIFY no such claim slipped in.

---

## 8. Peng 1995 · 🟡 TO VERIFY (formula match)

**Full citation:**
Peng CK, Havlin S, Stanley HE, Goldberger AL. *Quantification of scaling exponents and crossover phenomena in nonstationary heartbeat time series.* Chaos. 1995;5(1):82-87.

**Used for:** DFA (Detrended Fluctuation Analysis) algorithm; α₁ short-term scaling exponent.

**Where in code:**
- DFA chart source
- Print Methodology
- Provenance

**Validation needed:** 🟡 Confirm our DFA implementation matches Peng's original (window sizes, detrending order, fit ranges for α₁).

---

## 9. Porta 2001 · 🟡 TO VERIFY (formula match)

**Full citation:**
Porta A, Guzzetti S, Montano N, Furlan R, Pagani M, Malliani A, Cerutti S. *Entropy, entropy rate, and pattern classification as tools to typify complexity in short heart period variability series.* IEEE Trans Biomed Eng. 2001;48(11):1282-1291.

**Used for:** Symbolic Dynamics — 0V / 1V / 2LV / 2ULV pattern distribution.

**Where in code:**
- Symbolic Dynamics chart
- Print Methodology

**Validation needed:** Confirm 0V/1V/2LV/2ULV classification scheme matches Porta's original definitions.

---

## 10. Costa 2002 · 🟡 TO VERIFY

**Full citation:**
Costa M, Goldberger AL, Peng CK. *Multiscale entropy analysis of complex physiologic time series.* Phys Rev Lett. 2002;89(6):068102.

**Used for:** Multi-Scale Entropy (MSE), complexity-index across timescale τ.

**Where in code:**
- MSE chart panel
- Print Methodology

**Validation needed:** Confirm scale-coarse-graining + SampEn parameters (m=2, r=0.15·SDNN) match Costa's original.

---

## 11. Baevsky 1984 · 🟡 TO VERIFY (year + formula)

**Likely full citation:**
Baevsky RM, Ivanov GG. *Heart rate variability: theoretical aspects and clinical application.* (Soviet-era Russian publication, possibly Vestnik Aritmologii or earlier monograph).

**Used for:** Baevsky Stress Index (SI) — Mode, AMo, MxDMn-based ANS-balance metric.

**Where in code:**
- Stress-Index gauge panel
- Print Methodology

**Validation needed:** 🔴 Comet warned: Baevsky's stress index is **Russian school, NOT Western HRV goldstandard**. Confirm:
(a) the 1984 year (original may be earlier, c.1979 monograph),
(b) the formula `SI = AMo / (2 · Mode · MxDMn)` matches Baevsky's original,
(c) we communicate clearly that SI is sensitive to artefacts + short recordings.

---

## 12. Younes 2017 · 🟡 TO VERIFY

**Likely full citation:**
Younes M, Robert C, Cottin F, Barrey E. *Heart rate, heart rate variability and exercise loads in horses during racing.* Equine Vet J. 2017;49(2):212-217.

(Possible — this MAY be the source we want, but may be a different Younes paper on colic/stress. NEED CONFIRMATION.)

**Used for:** Acute colic indicator — RMSSD-drop + HR-rise pattern.

**Where in code:**
- Print Methodology (Veterinary indicator markers)
- Print Cover indicator
- Demo clinicalIndicators.acuteColic

**Validation needed:** 🔴 Confirm exactly WHICH Younes 2017 paper establishes the colic-HRV link, OR replace with a more definitively colic-focused paper (e.g., Stewart et al on equine colic + HRV).

---

## 13. Gehlen 2020 · 🔴 UNCERTAIN

**Likely full citation:** Unclear — multiple Gehlen papers on equine HRV exist (Gehlen H. at FU Berlin equine clinic group). Possible:
- Gehlen H, et al. *Heart rate variability in equine medicine* (review or specific welfare study c.2020).
- BMC Vet Res 2020;16:127 if that exists.

**Used for:** Respiratory marker via HF-power.

**Where in code:**
- Method-Transparency
- Print Methodology
- Print Cover indicator

**Validation needed:** 🔴 Comet flagged: "Gehlen 2020 is too unscharf — multiple papers in scope, concrete metric depends on the paper." We must IDENTIFY which exact Gehlen paper, OR remove this claim. Currently the strongest risk of being unsupportable.

---

## 14. Vitale 2020 · 🟡 TO VERIFY

**Possible full citation:**
Vitale V, et al. *Heart rate variability in horses* — multiple Vitale papers exist. Likely candidate:
Vitale V, Balocchi R, Varanini M, Sgorbini M, Macerata A, Sighieri C, Mazzei M, Bonelli F. *Effect of cardiac rehabilitation on autonomic function in horses with atrial fibrillation* (or similar) c.2020.

**Used for:** Disease-risk cutoffs (SD1 < 30, sEA-RF).

**Where in code:**
- Print Methodology (Veterinary indicator markers)

**Validation needed:** 🔴 Identify exact Vitale 2020 paper + confirm SD1<30 cutoff is from it.

---

## 15. Nyerges-Bohák 2025 · 🔴 UNCERTAIN (recent, may not be findable)

**Used for:** sEA-RF (Sample Entropy-based RF model for equine disease prediction).

**Where in code:**
- Print Methodology

**Validation needed:** 🔴 Recent enough that PubMed indexing may be incomplete. Confirm existence + claim.

---

## 16. Press 2007 · ✅ CONFIRMED (textbook, not paper)

**Full citation:**
Press WH, Teukolsky SA, Vetterling WT, Flannery BP. *Numerical Recipes: The Art of Scientific Computing* (3rd edition). Cambridge University Press, 2007.

**Used for:** Welch PSD implementation reference (Hann window, 50% overlap, 4 Hz cubic-spline resampling).

**Where in code:**
- Cross-validation: "Welch PSD on 4Hz cubic spline" alternative
- Provenance.wasGeneratedBy

**Validation needed:** OK — textbook reference is acceptable as implementation source.

---

## 17. Lomb 1976 / Scargle 1982 · ✅ CONFIRMED

**Full citations:**
- Lomb NR. *Least-squares frequency analysis of unequally spaced data.* Astrophys Space Sci. 1976;39:447-462.
- Scargle JD. *Studies in astronomical time series analysis. II. Statistical aspects of spectral analysis of unevenly spaced data.* Astrophys J. 1982;263:835-853.

**Used for:** Lomb-Scargle Periodogram (cross-validation against Welch PSD on unevenly-sampled RR data).

**Where in code:**
- Cross-validation: LF/HF alternative method

**Validation needed:** ✅ Standard astronomy/signal-processing references.

---

## 18. Richman 2000 · 🟡 TO VERIFY

**Full citation:**
Richman JS, Moorman JR. *Physiological time-series analysis using approximate entropy and sample entropy.* Am J Physiol Heart Circ Physiol. 2000;278(6):H2039-H2049.

**Used for:** Sample Entropy (SampEn) primary computation.

**Where in code:**
- Cross-validation: SampEn primary
- Print Methodology

**Validation needed:** Standard SampEn reference. Confirm m=2, r=0.15·SD parameters match.

---

## 19. Bandt-Pompe 2002 · 🟡 TO VERIFY

**Full citation:**
Bandt C, Pompe B. *Permutation entropy: A natural complexity measure for time series.* Phys Rev Lett. 2002;88(17):174102.

**Used for:** Permutation Entropy (cross-validation against SampEn).

**Where in code:**
- Cross-validation: SampEn alternative

**Validation needed:** Standard PE reference. Confirm embedding dimension m=3 used.

---

## 20. Politis-Romano 1994 · 🟡 TO VERIFY

**Full citation:**
Politis DN, Romano JP. *The stationary bootstrap.* J Am Stat Assoc. 1994;89(428):1303-1313.

**Used for:** Bootstrap-CI on HRV metrics (n=1000 SD1/SD2, n=200 SampEn).

**Where in code:**
- Print Methodology
- Demo data selfDocumentation.researcher.summary

**Validation needed:** Confirm Politis-Romano stationary bootstrap is the actual method used (vs. plain iid bootstrap).

---

## 21. Schaffarczyk 2022 · 🟡 TO VERIFY

**Possible citation:**
Schaffarczyk M, Rogers B, Reer R, Gronwald T. *Validity of the Polar H10 sensor for heart rate variability analysis during resting state and incremental exercise in recreational men and women.* Sensors. 2022;22(17):6536.

**Used for:** Polar H10 ECG-grade validation against 12-lead EKG.

**Where in code:**
- Fact-Card "1000 Hz Sampling" detail-line

**Validation needed:** Verify this is the specific paper supporting "ECG-grade R-peak sampling, peer-reviewed against 12-lead EKG" claim.

---

## 22. Gilgen-Ammann 2019 · 🟡 TO VERIFY

**Possible citation:**
Gilgen-Ammann R, Schweizer T, Wyss T. *RR interval signal quality of a heart rate monitor and an ECG Holter at rest and during exercise.* Eur J Appl Physiol. 2019;119(7):1525-1532.

**Used for:** Polar H10 vs Holter validation.

**Where in code:**
- Fact-Card "1000 Hz Sampling" detail-line

**Validation needed:** Confirm this is the paper. Confirm comparison was vs. medical-grade Holter, not against other consumer wearables.

---

## 23. Plews-Kilding 2013 · 🟡 TO VERIFY

**Possible citation:**
Plews DJ, Laursen PB, Kilding AE, Buchheit M. *Heart rate variability in elite triathletes, is variation in variability the key to effective training? A case comparison.* Eur J Appl Physiol. 2012;112:3729-3741 (cite year mismatch — may be 2013 paper instead).

**Used for:** Personal Z-Scores baseline-comparison framework.

**Where in code:**
- Personal Z-Scores chart source

**Validation needed:** Confirm exact paper year + that Plews-Kilding framework applies to equine, not just human elite endurance.

---

## 24. Dickey-Fuller 1979 · ✅ CONFIRMED

**Full citation:**
Dickey DA, Fuller WA. *Distribution of the estimators for autoregressive time series with a unit root.* J Am Stat Assoc. 1979;74(366):427-431.

**Used for:** ADF stationarity test on RR-data.

**Where in code:**
- Spectral-Peaks + Stationarity panel

**Validation needed:** ✅ Foundational econometrics reference.

---

## 25. Gronwald-Hoos 2020 · 🔴 UNCERTAIN (especially for equine)

**Possible citation:**
Gronwald T, Rogers B, Hoos O. *Fractal correlation properties of heart rate variability: a new biomarker for intensity distribution in endurance exercise and training prescription?* Front Physiol. 2020;11:550572.

**Used for:** DFA-α₁ as training-intensity biomarker, HVT1/HVT2 thresholds.

**Where in code:**
- DFA panel description

**Validation needed:** ⚠️ This is HUMAN endurance-exercise research. Transferring HVT1/HVT2 from human running to equine is the kind of cross-species extrapolation Dr. Schmidt-Roleplay flagged. MAY NEED TO REMOVE equine training-zone claims or explicitly mark as "extrapolated, not equine-validated".

---

## 26. Wonghanchao 2025 · 🔴 UNCERTAIN (recent, may not exist)

**Used for:** Listed in standardsApplied array.

**Where in code:**
- Schema standardsApplied list

**Validation needed:** 🔴 If this citation cannot be confirmed, REMOVE from standardsApplied.

---

## 27. Tarvainen 2002 · 🟡 TO VERIFY

**Likely full citation:**
Tarvainen MP, Ranta-aho PO, Karjalainen PA. *An advanced detrending method with application to HRV analysis.* IEEE Trans Biomed Eng. 2002;49(2):172-175. PMID: 12066885.

**Used for:** Smoothness-priors detrending (lambda=500, cutoffHz=0.035).

**Where in code:**
- Provenance.wasGeneratedBy.usedAlgorithms (2002 / lambda=500 / cutoffHz=0.035)
- Print Methodology

**Validation needed:** Confirm lambda=500 + cutoffHz=0.035 are the canonical Tarvainen recommended defaults.

---

# SUMMARY · PRIORITY-RANKED ACTIONS FOR JAN/COMET

## 🔴 Highest priority — Beta-blocker if wrong
1. **Visser 2002** — confirm WHICH paper defines equine PSD bands
2. **Reef 1998** — confirm the 28-44 BPM range + Mobitz-I-physiological claim
3. **Stucke 2015** — confirm DFA equine zone boundaries
4. **Mitchell 2018** — confirm RMSSD > 302 ms cutoff
5. **Gehlen 2020** — identify exact paper OR remove
6. **Younes 2017** — identify exact paper for colic claim
7. **Wonghanchao 2025** — verify existence OR remove
8. **Nyerges-Bohák 2025** — verify existence

## 🟡 Verify-but-likely-OK
- Tarvainen 2002 defaults (lambda=500)
- Lipponen-Tarvainen 2019 parameters
- Brennan 2001 — confirm we DON'T claim SD1/SD2 sympathetic mapping
- Gronwald-Hoos 2020 — mark as "human research, not equine-validated"

## ✅ Confident
- Task Force 1996
- Peng 1995 (DFA core)
- Porta 2001 (Symbolic)
- Costa 2002 (MSE)
- Press 2007 (Welch implementation textbook)
- Lomb 1976 / Scargle 1982
- Dickey-Fuller 1979

---

**Process recommendation:**
1. Submit this file to Comet (`mcp__perplexity__reason` or web Comet)
2. For each TO VERIFY / UNCERTAIN: ask Comet to provide PMID/DOI + abstract snippet that supports our specific claim
3. Where mismatch found: either replace citation, soften claim, or remove
4. After fix: re-screenshot the demo + re-print PDF to verify no broken references
5. THEN send clinic outreach mails
