---
title: "Regulatory & Quality Control Layer — Batch 3 (Milk Thistle, Lavender, St. John’s Wort, Rosemary, Ginkgo)"
category: "Regulatory & Quality Control"
tags: ["regulatory", "quality_control", "batch3", "milk_thistle", "lavender", "st_johns_wort", "rosemary", "ginkgo"]
date: "2025-11-14"
source: "WHO monographs; EMA/HMPC; ESCOP; pharmacopoeias; project regulatory batch 3"
---

# Regulatory & Quality Control Layer — Batch 3  
Milk Thistle · Lavender · St. John’s Wort · Rosemary · Ginkgo

This batch adds a **regulatory + quality control overlay** on top of your existing clinical monographs.  
Use it as a separable layer in your KB (indications, use category, posology, QC tests, GACP/GMP hooks).

---

## 1. Milk Thistle (*Silybum marianum* (L.) Gaertn., fructus)

> Attach to your **Milk Thistle** monograph (fruit/“seed” and standardised extracts).

### 1.1 Regulatory status snapshot

- **WHO** – *Fructus Silybi mariani* monograph describes the dried fruit for use as a **hepatoprotective and cholagogue herb**, with data for chronic liver disease and dyspeptic complaints.  
- **EMA/HMPC (EU herbal monographs)**  
  - European work (including older Commission E/ESCOP material and national assessments) supports herbal medicinal products with **standardised silymarin extracts** for:
    - Supportive treatment in **chronic inflammatory liver disease** and **hepatic cirrhosis**.  
    - **Hepatoprotective** use in toxic liver damage.  
  - More recent EU harmonisation tends to emphasise **relief of digestive disturbances and sensation of fullness** and **support of liver function** as the core indication set; precise WEU vs TU categorisation is product- and country-specific.
- **ESCOP & Commission E** – Endorse silymarin-containing milk thistle fruit preparations as adjunctive therapy in **toxic and inflammatory liver conditions**, and for **dyspeptic complaints**.  
- **Pharmacopoeias** – Ph. Eur., national pharmacopoeias and USP/HMC define identity and assay specs for the **fruit** and **standardised extracts** (silymarin content).

### 1.2 Indications & use categories

**Evidence-supported / pharmacopoeial focus**

- **Supportive treatment** in chronic inflammatory liver disease and hepatic cirrhosis (adjunct to standard care).  
- **Hepatoprotective** use in toxic liver injury (e.g., alcohol, certain medications) as part of broader management.  
- **Dyspeptic complaints** and digestive disturbances (fullness, flatulence).

**Traditional use**

- General **“liver tonic”** and **cholagogue** in traditional medicine systems.  
- Support in convalescence after hepatitis or liver overload (dietary/alcohol).

**KB field mapping**

- `milk_thistle.reg.hepatic_support_indications` → supportive treatment in chronic inflammatory liver disease/cirrhosis; hepatoprotective use in toxic liver damage.  
- `milk_thistle.reg.dyspepsia_indications` → dyspeptic complaints / sense of fullness.  
- `milk_thistle.reg.key_compendia` → WHO, ESCOP, Commission E, EU assessments, Ph. Eur., USP/HMC.

### 1.3 Posology ranges (adults; non–product-specific)

*These are standard monograph/compendium ranges, not prescribing advice.*

**Crude fruit (whole or coarsely ground)**  

- Daily dose often cited as **12–15 g** of fruit, divided in **2–3 doses** (e.g., decoction or infusion).

**Standardised extracts (silymarin)**  

- Many authoritative sources point to **200–420 mg silymarin per day**, usually as:
  - 140 mg standardised extract (approx. 70–80% silymarin) **3×/day**, or  
  - Equivalent regimens providing **~420 mg/day** total silymarin.  

**KB fields**

- `milk_thistle.posology.fruit_daily_g` → 12–15  
- `milk_thistle.posology.silymarin_daily_mg_range` → 200–420  
- `milk_thistle.posology.notes` → “Adjunctive therapy over weeks–months under professional supervision; safety in severe hepatic failure must be handled cautiously.”

### 1.4 Pharmacopoeial identity & purity tests

**Identity (fruit)**  

- Macroscopic: brownish, oblong, slightly flattened fruits with a shiny surface and distinctive tuft scars (pappus remnants).  
- Microscopic: thick pericarp with sclerenchymatous tissue, oil-containing endosperm and embryo.  
- TLC/HPLC: characteristic **flavonolignan (silymarin) profile** (silybin A/B, silychristin, silydianin, isosilybin, etc.) vs reference standard.

**Identity / assay (extracts)**  

- Drug–extract ratio (DER) and extraction solvent defined (often ethanol-based).  
- HPLC assay for **total silymarin** and sometimes for individual flavonolignans.  

**Purity**

- Limits on **foreign organic matter**, **total ash**, **acid-insoluble ash** and **extractables**.  
- Microbial purity: TAMC/TYMC within herbal limits; absence of specified pathogens.  
- Contaminants: **pesticides**, **heavy metals**, **mycotoxins** (especially in stored fruits), **residual solvents** for extracts.

**KB tags**

- `milk_thistle.qc.id_markers` → silybin A/B, silychristin, silydianin, isosilybin.  
- `milk_thistle.qc.assay_targets` → total silymarin (defined % range for crude fruit and for extracts).  
- `milk_thistle.qc.purity_focus` → mycotoxins (storage), pesticides, heavy metals, microbes, residual solvents.

### 1.5 GACP/GMP notes

- GACP:  
  - Reliable identification of **Silybum marianum** stands; documentation of herbicide/pesticide use.  
  - Proper drying and storage of fruits to prevent mould and **aflatoxin** contamination.  
- GMP:  
  - Spec-defined silymarin content and validated analytical methods for flavonolignans.  
  - Long-term stability studies for extracts and finished dosage forms (capsules, tablets) with monitoring of silymarin profile and degradation products.

---

## 2. Lavender (*Lavandula angustifolia* Mill., flos & aetheroleum)

> Attach to your **Lavender** monograph (flower and essential oil).

### 2.1 Regulatory status snapshot

- **WHO** – Monographs describe lavender flower and oil for **nervous tension**, **insomnia** and **digestive complaints**, internally and externally.  
- **EMA/HMPC (EU herbal monographs)**  
  - *Lavandulae flos* (flower):  
    - Traditional herbal medicinal product for **relief of mild symptoms of mental stress** and **exhaustion** and/or **aid to sleep**, as well as **digestive complaints** such as mild spasms.  
  - *Lavandula angustifolia aetheroleum* (oil):  
    - Oral preparations of standardised oil used in several EU countries for **treatment of mild anxiety**, supported by clinical data (product-specific WEU registrations).  
    - Traditional use topically or in baths for **mild rheumatic complaints** and **circulatory disorders**.  
- **ESCOP & other expert monographs** – Broadly support these indications and add details on dosage forms (infusions, baths, oil preparations).  
- **Pharmacopoeias** – Ph. Eur./USP specify detailed identity/assay ranges for **lavender oil** and identity/purity criteria for **lavender flowers**.

### 2.2 Indications & use categories

**Traditional use (flower / tea)**  

- Relief of **mild symptoms of mental stress and exhaustion**.  
- **Sleep aid** in mild insomnia.  
- Mild **spasmodic digestive complaints** (e.g., bloating, nervous stomach).

**Evidence-supported oral oil use**

- Standardised oral lavender oil (e.g., 80 mg/day) for **treatment of mild anxiety**, with documented clinical studies in generalised anxiety and related syndromes.  

**Topical/bath use (traditional)**  

- **Mild rheumatic or muscular pain** and **circulatory disturbances** (e.g., warm baths with lavender oil/flower infusions).  

**KB field mapping**

- `lavender.reg.trad_indications_neuro` → mild stress, nervous tension, insomnia.  
- `lavender.reg.trad_indications_gi` → nervous stomach, mild digestive spasms.  
- `lavender.reg.evidence_oil_anxiety` → oral standardised oil 80 mg/day for mild anxiety (clinical evidence; product-specific).  

### 2.3 Posology ranges

**Lavender flower (infusion; adults)**  

- **2–3 g** of comminuted flower per cup, taken **2–3×/day** for nervousness/digestive complaints or in the evening as sleep aid.  

**Lavender oil (oral; standardised preparations)**  

- Many clinical trials and product monographs use **80 mg standardised essential oil once daily** for mild anxiety.  

**Topical/bath use**  

- Baths: a few **drops of essential oil** or a strong infusion of flowers in bathwater for **10–20 minutes**, typically once daily or several times weekly.  

**KB fields**

- `lavender.posology.flower_tea_single_g` → 2–3  
- `lavender.posology.flower_tea_freq_per_day` → 2–3  
- `lavender.posology.oil_oral_mg_per_day` → ~80  
- `lavender.posology.notes` → “Exact posology per national product monographs; oral oil use constrained by age and safety warnings.”

### 2.4 Pharmacopoeial identity & purity tests

**Identity — flower**

- Macroscopic: dried whole or cut flower spikes with calyx and corolla of *L. angustifolia*; characteristic fragrance.  
- Microscopic: glandular trichomes with essential-oil droplets; diagnostic calyx/corolla morphology.  
- TLC fingerprint of **linalool, linalyl acetate** and other constituents.

**Identity — oil**

- Organoleptic and physicochemical constants: refractive index, optical rotation, relative density.  
- GC profile: specified ranges for **linalool**, **linalyl acetate**, and limits for camphor and other constituents.  

**Purity**

- Essential oil content of flowers: minimum % (e.g., ≥1−1.5% v/w depending on pharmacopoeia).  
- Limits on **foreign matter, ash, moisture**, **pesticides, heavy metals**, **microbial contamination**.  
- Oil: limits on **peroxide value**, **ester value**, **non-volatile residue** and adulteration (e.g., spike oil, artificial linalool).

**KB tags**

- `lavender.qc.id_markers` → linalool, linalyl acetate (oil/flower extracts).  
- `lavender.qc.assay_targets` → minimum essential-oil content in flowers; defined ranges of linalool/linalyl acetate in oil.  
- `lavender.qc.purity_focus` → camphor limits, oxidation state of oil (peroxide), adulteration checks, contaminants.

### 2.5 GACP/GMP notes

- GACP:  
  - Cultivar/chemotype selection to maintain desired **linalool/linalyl acetate profile** with low camphor.  
  - Harvesting at **full flowering**; gentle drying to preserve oil content.  
- GMP:  
  - For oral oil preparations, validated content uniformity and stability; clear labelling of indications and contraindications (e.g., pregnancy, children).  
  - Monitoring oxidation (peroxide value) during shelf-life and controlling exposure to light/heat.

---

## 3. St. John’s Wort (*Hypericum perforatum* L., herba)

> Attach to your **St. John’s Wort** monograph (aerial parts / standardised extracts).

### 3.1 Regulatory status snapshot

- **WHO** – Monographs describe *Hyperici herba* for treatment of **mild to moderate depressive episodes** and **psychovegetative disturbances**, supported by clinical data for certain standardised extracts.  
- **EMA/HMPC (EU herbal monographs)**  
  - EU herbal monograph on *Hypericum perforatum* herba recognises preparations with:
    - Evidence-based use for **mild to moderate depressive episodes** (standardised extracts; “well-established use” for certain extract types).  
    - Traditional-use indications for **short-term treatment of depressive mood, nervous exhaustion, and sleep disturbances** for less-standardised preparations.  
- **ESCOP & Commission E** – Support similar indications for depressive mood, anxiety, psychosomatic complaints and sleep disturbances.  
- **Pharmacopoeias** – Ph. Eur. and other pharmacopoeias define identity and assay parameters for **hypericin / pseudohypericin / hyperforin** content in standardised extracts.

### 3.2 Indications & use categories

**Well-established / evidence-based use (standardised extracts)**  

- Treatment of **mild to moderate depressive episodes** in adults.

**Traditional use**

- Short-term treatment of **depressive mood, nervous exhaustion and sleep disturbances**.  
- Relief of mild anxiety and psychosomatic complaints in some national monographs.

**KB field mapping**

- `st_johns_wort.reg.weu_indications` → mild to moderate depressive episodes (standardised extracts).  
- `st_johns_wort.reg.trad_indications` → short-term depressive mood, nervous exhaustion, sleep disturbance.  
- `st_johns_wort.reg.key_compendia` → WHO, EMA/HMPC, ESCOP, Commission E, Ph. Eur.

### 3.3 Posology ranges (adults)

**Standardised extracts (oral)**  

- Many monographs and clinical trials converge on **900 mg/day of standardised extract**, usually as:  
  - **300 mg extract three times daily**, or  
  - **450 mg twice daily**, depending on preparation.  
- Extracts are standardised typically to **0.2–0.3% total hypericins** and/or defined hyperforin content; product-specific ranges vary.

**Traditional crude or weakly standardised preparations**  

- Daily dried herb equivalent often in the **2–4 g** range, though modern products mostly use standardised extracts rather than crude herb.

**KB fields**

- `st_johns_wort.posology.extract_daily_mg` → ~900  
- `st_johns_wort.posology.extract_dosing_patterns` → 300 mg 3×/day or 450 mg 2×/day.  
- `st_johns_wort.posology.notes` → “Dose and extract standardisation must match product SPC; allow for 2–4 weeks before evaluating response.”

### 3.4 Pharmacopoeial identity & purity tests

**Identity**

- Macroscopic: flowering aerial parts of *H. perforatum* with perforated leaves (translucent oil glands) and yellow flowers with black glandular dots.  
- Microscopic: characteristic glandular structures; diagnostic leaf and petal anatomy.  
- TLC/HPLC: profiles for **hypericin, pseudohypericin, hyperforin** and other naphthodianthrones/phloroglucinols.

**Purity**

- Limits for foreign matter, ash, moisture.  
- Microbiological quality in line with oral herbal drugs.  
- Contaminants: pesticides, heavy metals, aflatoxins controlled per WHO/Ph. Eur. guidelines.

**Assay**

- For extracts, defined ranges for **total hypericins** and often for **hyperforin** (with upper limits to mitigate photosensitivity or interaction risk).  
- For crude herb, minimum content of total hypericins may be specified.

**KB tags**

- `st_johns_wort.qc.id_markers` → hypericin, pseudohypericin, hyperforin.  
- `st_johns_wort.qc.assay_targets` → total hypericins %, hyperforin range.  
- `st_johns_wort.qc.purity_focus` → drug interactions (CYP induction) flagged as safety, not as purity; contaminants and microbes per standard.

### 3.5 GACP/GMP & safety notes

- GACP: verified *H. perforatum* stands (avoid other Hypericum spp. or “St. John’s wort” surrogates).  
- GMP:  
  - Strict control of **extract standardisation** and **hyperforin** content.  
  - Labelling and risk management for **drug–herb interactions** (CYP3A4, P-gp induction, etc.), **photosensitivity**, and use in pregnancy.  

---

## 4. Rosemary (*Rosmarinus officinalis* L. / *Salvia rosmarinus* Spenn., folium & aetheroleum)

> Attach to your **Rosemary** monograph (leaf and essential oil).

### 4.1 Regulatory status snapshot

- **WHO** – Monographs describe rosemary leaf and oil for **dyspeptic complaints**, **mild spasmodic GI disorders**, and **minor peripheral circulatory disorders**, as well as for **minor muscle and joint pain** (topical, baths).  
- **EMA/HMPC (EU herbal monographs)**  
  - *Rosmarini folium*: traditional herbal medicinal product for **dyspeptic complaints** and **mild spasmodic GI disorders**.  
  - *Rosmarini aetheroleum* (oil): traditional use for **minor muscular and articular pain** (topical) and **mild circulatory disorders** (baths, rubs).  
- **ESCOP & national monographs** – Emphasise similar indications and detail dosage forms (tea, tincture, baths, rubs).  
- **Pharmacopoeias** – Ph. Eur., USP etc. define identity and assay specs for rosemary leaf and essential oil (e.g., camphor content ranges, 1,8‑cineole, α‑pinene).

### 4.2 Indications & use categories

**Traditional internal use (leaf)**  

- **Dyspeptic complaints**, bloating, flatulence.  
- Mild **spasmodic GI discomfort**.

**Traditional external use (leaf/oil)**  

- **Minor muscle or joint pain**, lumbago and neuralgic pains (topical liniments and baths).  
- **Peripheral circulatory disorders** (e.g., “cold hands and feet”) via warm baths or rubs.

**KB field mapping**

- `rosemary.reg.trad_indications_gi` → dyspepsia, mild spasmodic GI complaints.  
- `rosemary.reg.trad_indications_musculoskeletal` → minor muscle/joint pain, rheumatic discomfort (topical).  
- `rosemary.reg.trad_indications_circulation` → mild peripheral circulatory disorders (baths).  

### 4.3 Posology ranges

**Rosemary leaf (infusion; adults)**  

- Common monograph pattern: **1–2 g** of comminuted leaf per cup, **2–3×/day** for GI complaints.  

**Baths / topical rubs**  

- Herb baths: typically tens of grams of dried herb per bath or equivalent hydroalcoholic extracts.  
- Essential oil: a few **drops diluted in carrier oil or bathwater**, used locally 1–2×/day; undiluted topical use is generally not recommended in large areas.

**KB fields**

- `rosemary.posology.leaf_tea_single_g` → 1–2  
- `rosemary.posology.leaf_tea_freq_per_day` → 2–3  
- `rosemary.posology.topical_oil_use` → “few drops diluted; 1–2×/day to affected area.”  

### 4.4 Pharmacopoeial identity & purity tests

**Identity — leaf**

- Macroscopic: linear, revolute leaves with white felted underside and dark green upper surface.  
- Microscopic: strongly cutinised epidermis, small essential-oil glands.  
- TLC profile highlighting **phenolic diterpenes** (e.g., carnosic acid, carnosol) and essential-oil components (e.g., 1,8‑cineole, camphor).

**Identity — oil**

- Organoleptic + physicochemical constants (density, refractive index, optical rotation).  
- GC profile with defined ranges of **α‑pinene, 1,8‑cineole, camphor**, borneol and related monoterpenes; chemotype-specific ranges.

**Purity**

- Foreign matter, ash, moisture limits.  
- Pesticides, heavy metals, microbial load as usual for herbal drugs.  
- Oil purity checks for adulteration (e.g., addition of synthetic camphor or other cheap terpenes); limits on oxidation products (peroxide value).

**KB tags**

- `rosemary.qc.id_markers` → 1,8‑cineole, camphor, α‑pinene, carnosic acid/carnosol.  
- `rosemary.qc.assay_targets` → minimum essential-oil content in leaf; chemotype-specific terpene ranges in oil.  
- `rosemary.qc.purity_focus` → camphor levels (safety), oxidation, adulteration, contaminants.

### 4.5 GACP/GMP notes

- GACP:  
  - Distinguish **rosemary** from similar Lamiaceae shrubs; document location/conditions due to chemotype variations (camphor‑rich vs cineole‑rich oils).  
  - Harvest at flowering for best essential-oil content and phenolic diterpenes.  
- GMP:  
  - Set and maintain chemotype-specific specs (camphor content upper/lower limits).  
  - Ensure correct dilution and labelling of essential-oil products to minimise risk of irritation or seizure threshold issues at high camphor exposure.

---

## 5. Ginkgo (*Ginkgo biloba* L., folium)

> Attach to your **Ginkgo** monograph (leaf and standardised extracts).

### 5.1 Regulatory status snapshot

- **WHO** – Ginkgo leaf monograph focuses on **cognitive and circulatory indications**, including **symptoms of cerebral insufficiency** and **peripheral arterial occlusive disease**, based mainly on evidence from standardised extracts.  
- **EMA/HMPC and EU context**  
  - EU and national monographs/assessment reports for **standardised Ginkgo extracts** support indications such as:  
    - **Improvement of (age-associated) cognitive impairment** and quality of life in **mild dementia**.  
    - Improvement of **pain-free walking distance** in **peripheral arterial occlusive disease** in certain patient groups.  
  - Status (WEU vs national well-established use) varies by extract type and country; indications are tied tightly to specific, standardised extracts (e.g., defined DER and solvent).  
- **ESCOP & Commission E** – Support similar indications, emphasizing standardised extracts only.  
- **Pharmacopoeias** – Ph. Eur., USP etc. define monographs for **Ginkgo leaf** and **standardised extracts** with strict assay requirements for **flavone glycosides**, **terpene lactones** and **ginkgolic acids**.

### 5.2 Indications & use categories

**Evidence-based indications (standardised extracts only)**  

- **Symptomatic treatment of cognitive impairment and quality-of-life reduction in mild dementia**, including Alzheimer type, when standard therapy is unsuitable or as adjunct.  
- Improvement of **intermittent claudication** (peripheral arterial occlusive disease Fontaine stage II) to increase pain-free walking distance.

**Traditional / broader uses (tag separately)**  

- Some monographs mention tinnitus, vertigo and other circulatory/vestibular complaints; evidence is more heterogeneous and product- / country-specific.

**KB field mapping**

- `ginkgo.reg.evidence_indications` → mild dementia (cognitive impairment), intermittent claudication (PAOD).  
- `ginkgo.reg.trad_or_other_indications` → tinnitus, vertigo, other circulatory/vestibular complaints (flag as weaker-evidence / not harmonised).  
- `ginkgo.reg.key_compendia` → WHO, EU assessment reports, ESCOP, Commission E, Ph. Eur., USP.

### 5.3 Posology ranges (standardised extracts; adults)

*Always link to extract type: DER and solvent must match the clinical evidence.*

- Most evidence-based products use dry extracts with **DER approx. 35–67:1** (acetone–water or similar solvent), standardised to:  
  - **22–27% flavone glycosides** (as quercetin, kaempferol, isorhamnetin glycosides).  
  - **5–7% terpene lactones** (ginkgolides A, B, C and bilobalide).  
  - **≤5 ppm ginkgolic acids** (or an analogous very low upper limit).

**Typical daily dose**  

- **120–240 mg extract per day**, usually taken as:  
  - 40 mg **3×/day**, or  
  - 80 mg **2–3×/day**, or  
  - 120 mg **1–2×/day**, depending on product.  
- Treatment durations of **at least 8 weeks** (and often longer) are recommended before evaluating cognitive outcomes.

**KB fields**

- `ginkgo.posology.extract_daily_mg_range` → 120–240  
- `ginkgo.posology.dosing_patterns` → 40 mg 3×/day; 80 mg 2–3×/day; 120 mg 1–2×/day.  
- `ginkgo.posology.min_duration_weeks` → ≥8 (for cognitive outcomes).

### 5.4 Pharmacopoeial identity & purity tests

**Identity — leaf**

- Macroscopic: characteristic fan-shaped leaves with dichotomous venation.  
- Microscopic: epidermal features and internal tissues typical of Ginkgo.  
- TLC/HPLC fingerprint for **flavone glycosides** and **terpene lactones**.

**Identity / assay — standardised extracts**

- Defined **DER** and extraction solvent.  
- HPLC assay verifying:  
  - **Flavone glycosides** 22–27% (range varies slightly by monograph).  
  - **Terpene lactones** 5–7% (ginkgolides + bilobalide).  
  - **Ginkgolic acids** below very low maximum (e.g., ≤5 ppm).

**Purity**

- Foreign matter, ash, moisture within limits for herbal drugs.  
- Microbial quality as per oral herbal substances.  
- **Pesticides, heavy metals**, solvent residues (for extracts) and mycotoxins monitored per pharmacopeial guidance.

**KB tags**

- `ginkgo.qc.id_markers` → flavone glycosides (quercetin/kaempferol/isorhamnetin glycosides), ginkgolides A/B/C, bilobalide.  
- `ginkgo.qc.assay_targets` → 22–27% flavone glycosides, 5–7% terpene lactones, ≤5 ppm ginkgolic acids (or equivalent spec).  
- `ginkgo.qc.purity_focus` → ginkgolic acid minimisation, solvent residues, pesticide/heavy-metal burden.

### 5.5 GACP/GMP & safety notes

- GACP:  
  - Documented sourcing of Ginkgo leaves; control of pesticide use (Ginkgo is often treated as a plantation tree).  
  - Timing and conditions of leaf harvest affect flavonoid/terpene profiles.  
- GMP:  
  - Strict extract standardisation (flavone glycosides, terpene lactones, ginkgolic acids).  
  - Stability testing with monitoring of active markers and ginkgolic acids.  
  - Safety tagging in your KB should highlight: **bleeding risk** (caution with anticoagulants/antiplatelets), perioperative discontinuation, and seizure risk with high ginkgolic acids or seed extracts (not standard leaf extracts).

---

**Batch 3 summary for your KB**

Herbs in this file:  

- `milk_thistle` — hepatic support + dyspepsia; silymarin-centric QC.  
- `lavender` — mild anxiety/stress/insomnia; linalool/linalyl acetate QC.  
- `st_johns_wort` — mild–moderate depression; hypericin/hyperforin QC & interaction flags.  
- `rosemary` — dyspeptic and musculoskeletal/circulatory support; cineole/camphor QC.  
- `ginkgo` — mild dementia & PAOD; flavone glycosides/terpene lactones/ginkgolic acids QC.

Use each section as a coherent chunk group in your vector store, and mine structured fields like `*.reg.*`, `*.posology.*`, `*.qc.*` for your regulatory/quality control layer.


