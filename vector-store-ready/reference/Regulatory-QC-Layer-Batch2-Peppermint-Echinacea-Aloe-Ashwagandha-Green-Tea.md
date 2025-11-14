---
title: "Regulatory & Quality Control Layer — Batch 2 (Peppermint, Echinacea, Aloe, Ashwagandha, Green Tea)"
category: "Regulatory & Quality Control"
tags: ["regulatory", "quality_control", "batch2", "peppermint", "echinacea", "aloe", "ashwagandha", "green_tea"]
date: "2025-11-14"
source: "WHO monographs; EMA/HMPC; ESCOP; pharmacopoeias; project regulatory batch 2"
---

# Regulatory & Quality Control Layer — Batch 2  
Peppermint · Echinacea · Aloe · Ashwagandha · Green Tea

> This batch adds a regulatory & quality-control overlay on top of your existing clinical monographs.  
> Use it as a compact, parseable layer (indications, use category, posology, QC tests, GACP/GMP hooks) that you can tag or chunk separately.

---

## 1. Peppermint (Mentha × piperita L.)

> Attach this section to your core **Peppermint** monograph (leaf + oil).

### 1.1 Regulatory status snapshot

- **WHO** – Peppermint leaf and peppermint oil are covered in the *WHO Monographs on Selected Medicinal Plants* for use as carminative, spasmolytic and for symptoms of digestive discomfort and tension-type headache.  
- **EMA/HMPC (EU herbal monographs)**  
  - *Mentha × piperita* **folium (leaf)** – Community herbal monograph with **well‑established use (WEU)** and **traditional use (TU)** indications for short‑term relief of mild spasmodic gastrointestinal complaints (bloating, flatulence, minor cramping) and digestive upset.  
  - *Mentha × piperita* **aetheroleum (oil)** – Monograph for oral, inhalation and cutaneous preparations based on **traditional use** (IBS‑type abdominal discomfort, digestive colic, coughs/colds, mild muscle pain, tension‑type headache in topical use).  
- **ESCOP & other expert monographs** – ESCOP peppermint leaf/oil monographs broadly match WHO/HMPC indications and are cited in EU assessment work.  
- **Pharmacopoeias (identity/purity)** – Peppermint leaf and oil have detailed monographs in major pharmacopoeias (e.g., Ph. Eur., USP), specifying identity tests, essential‑oil content, marker ranges and impurity limits.

### 1.2 Indications & use categories (link these as structured KB fields)

**Well‑established use (EU; leaf, oral)**  

- Short‑term relief of **mild spasmodic gastrointestinal complaints** (e.g., bloating, flatulence, digestive cramping).  
- Supportive treatment of **mild dyspeptic symptoms**.

**Traditional use (EU; leaf & oil)**  

- Leaf infusions for **mild digestive complaints**, flatulence, feeling of fullness.  
- Oil (enteric‑coated capsules) for **abdominal pain/discomfort in IBS‑like patterns**.  
- Cutaneous or inhaled oil for **tension‑type headache**, coughs/colds and minor muscle pain.

**Suggested KB field mapping**

- `peppermint.reg.weu_indications` → GI spasm / bloating / flatulence, mild dyspepsia (leaf).  
- `peppermint.reg.trad_indications` → IBS‑type abdominal discomfort (oil), tension‑type headache (topical oil), coughs/colds (inhalation/oral sprays/lozenges), mild muscle pain (topical).  
- `peppermint.reg.key_compendia` → WHO, EMA/HMPC (folium, aetheroleum), ESCOP, Ph. Eur., USP.

### 1.3 Posology ranges (regulatory‑aligned; adults unless noted)

*These are **regulatory monograph ranges**, not prescribing advice. Always check specific product SPC.*

**Peppermint leaf (oral)**  

- **Herbal tea**: comminuted leaf equivalent to a **daily dose ~4.5–9 g**, typically as **1.5–3 g per cup, 2–3×/day**.  
- **Liquid preparations (e.g., tinctures)**: daily doses roughly equivalent to the tea dose (e.g., about **6–9 mL tincture divided in 2–3 doses**), depending on drug:extract ratio defined in the monograph.

**Peppermint oil (oral, enteric‑coated)**  

- Typical **single dose** around **0.08–0.12 mL**, **3–4×/day**, corresponding to a **daily dose ~0.24–0.48 mL**, in line with HMPC IBS indications.  

**Peppermint oil (cutaneous / inhalation)**  

- Doses are normally defined as “thin layer applied to affected area” or a fixed number of drops or spray actuations; the exact numeric range is product‑ and country‑specific.  

**Suggested KB field mapping**

- `peppermint.posology.tea_leaf_daily_g` → 4.5–9  
- `peppermint.posology.tincture_daily_ml_range` → 6–9  
- `peppermint.posology.oil_oral_single_ml` → 0.08–0.12  
- `peppermint.posology.oil_oral_daily_ml` → 0.24–0.48  
- `peppermint.posology.notes` → “Check local product monograph / SPC; paediatric dosing and duration limits vary.”

### 1.4 Pharmacopoeial identity & purity tests (high‑level)

**Identity (leaf)**  

- Macroscopic & microscopic identification of *Mentha × piperita* leaf (opposite, serrate leaves; characteristic glandular trichomes with essential‑oil droplets).  
- Thin‑layer chromatography (TLC) fingerprint showing characteristic phenolic/terpenoid profile (e.g., rosmarinic acid) compared against reference.  

**Identity (oil)**  

- Organoleptic properties (odour, taste) plus physicochemical constants (refractive index, relative density, optical rotation).  
- **Gas chromatography** profile: specified ranges for menthol, menthone, menthyl acetate and other characteristic constituents depending on pharmacopoeia.  
- Assay for **menthol and total esters**: minimum concentrations of menthol and menthyl acetate (e.g., NLT ~50% total menthol and specified ester content in Ph. Eur./USP).  

**Purity – common themes**  

- Foreign organic matter limits for leaf; maximum total ash and acid‑insoluble ash.  
- Limits for **pesticide residues**, **heavy metals**, **microbial contamination** and **aflatoxins** per WHO/EMA guidelines.  
- Peroxide value, residual solvents and limits on non‑volatile residue and adulterants for oil.

**KB tags**

- `peppermint.qc.id_methods` → [macro, micro, TLC (leaf); GC (oil), organoleptics, physicochemical].  
- `peppermint.qc.assay_markers` → menthol, menthone, menthyl acetate, essential‑oil content.  
- `peppermint.qc.purity_focus` → foreign matter, ash, moisture, pesticides, heavy metals, microbes, aflatoxins, oil oxidation.

### 1.5 GACP/GMP & special quality notes

- Prioritise **GACP‑grade cultivation**: verified botanical identity at source, voucher specimens, traceability, and correct harvest stage (pre‑flowering/early flowering for optimal oil content).  
- Dry leaf at low temperatures to preserve essential oil; monitor **loss on drying** and **oil content** against pharmacopoeial minima.  
- For oil: confirm **absence of adulteration** (e.g., synthetic menthol, dementholised mint oils) using GC fingerprint and comparison with reference standards.  
- GMP manufacturing should ensure **enteric‑coating robustness** for oral oil capsules and adequate labelling of menthol content, contraindications (e.g., biliary disorders) and age limits.

---

## 2. Echinacea (Echinacea purpurea (L.) Moench)

> Attach this section to your **Echinacea purpurea** monograph. Focus here is on *herba recens* expressed juice and related preparations.

### 2.1 Regulatory status snapshot

- **WHO** – Echinacea species are discussed in WHO monographs mainly for **prevention and treatment of common cold and upper respiratory tract infections**, reflecting modern clinical and traditional uses.  
- **EMA/HMPC (EU herbal monographs)**  
  - *Echinacea purpurea herba recens* (expressed juice from fresh flowering aerial parts):  
    - **Well‑established use** / “herbal medicinal product” for **short‑term prevention and treatment of common cold** (oral use).  
  - *Echinacea purpurea herba* (liquid/solid herbal preparations):  
    - **Traditional herbal medicinal product** for **relief of cold symptoms** and for **treatment of small superficial wounds** (topical use), based on longstanding use.  
- **ESCOP** – ESCOP monographs support these indications for Echinacea aerial parts and roots, often cited in HMPC assessments.  
- **Pharmacopoeias** – Ph. Eur. and other pharmacopoeias define identity and purity requirements for *Echinaceae purpureae herba* and preparations (TLC profile, caffeic acid derivatives, polysaccharides).

### 2.2 Indications & use categories

**Well‑established / evidence‑supported use (oral)**  

- **Short‑term prevention and treatment of common cold** in adults, initiated at first signs of infection.  

**Traditional use (oral / topical)**  

- Relief of **mild upper respiratory tract infections** and associated symptoms (e.g., sore throat, runny nose) in adults and adolescents.  
- **Topical preparations** of E. purpurea or related species for **small superficial wounds and minor skin inflammations**.

**KB field mapping**

- `echinacea.reg.weu_indications` → short‑term prevention/treatment of common cold (herba recens expressed juice).  
- `echinacea.reg.trad_indications` → mild URTI symptom relief; topical for small superficial wounds.  
- `echinacea.reg.key_compendia` → WHO, EMA/HMPC (E. purpurea herba recens, herba), ESCOP, Ph. Eur.

### 2.3 Posology ranges (regulatory‑aligned; adults)

*Always consult the specific EU monograph / SPC for exact strengths and max duration.*

**Expressed juice from fresh aerial parts (herba recens, oral)**  

- Typical **single dose**: around **1.5–3 mL** of expressed juice, several times daily.  
- Typical **daily dose**: in the range of **6–9 mL/day**, divided, for a limited duration (e.g., up to 10–14 days) for cold prevention/treatment.

**Other liquid preparations (oral)**  

- Tinctures/fluid extracts: dosing adjusted to deliver an amount of herb comparable to the expressed juice dose, often given several times daily during the acute phase.  

**Topical preparations**  

- Applied undiluted or in defined dilutions to small superficial wounds **several times daily** according to product instructions.

**KB fields**

- `echinacea.posology.expressed_juice_single_ml` → 1.5–3  
- `echinacea.posology.expressed_juice_daily_ml` → 6–9  
- `echinacea.posology.max_duration_days` → approx. 10–14 (check product label / monograph).  
- `echinacea.posology.route_notes` → oral short‑term use only; avoid prolonged continuous use per HMPC safety guidance.

### 2.4 Pharmacopoeial identity & purity tests

**Identity**  

- Macroscopic and microscopic ID of aerial parts (conical receptacle, purple ray florets, rough stems) where relevant.  
- TLC fingerprint for **caffeic acid derivatives** (especially **cichoric acid**) and related phenolic markers vs. reference standard.  
- Where applicable, HPLC assay for cichoric acid or total caffeic acid derivatives to support batch consistency.

**Purity**  

- Limits on **foreign organic matter**, **total ash**, **acid‑insoluble ash** and **loss on drying** per pharmacopoeial specifications.  
- Microbial contamination limits aligned with WHO/Ph. Eur. (TAMC, TYMC, absence of specific pathogens).  
- Limits for **pesticide residues**, **heavy metals** and **aflatoxins** following WHO/EMA guidelines.

**KB tags**

- `echinacea.qc.id_markers` → cichoric acid, caffeic acid derivatives, characteristic TLC pattern.  
- `echinacea.qc.assay_targets` → total caffeic acid derivatives (where required), phenolic content.  
- `echinacea.qc.purity_focus` → ash, moisture, foreign matter, pesticides, heavy metals, microbes, aflatoxins.

### 2.5 GACP/GMP & special notes

- Use **botanically verified E. purpurea** (avoid confusion with other Echinacea spp. unless intentionally blended and labelled).  
- Maintain traceability of plant part (flowering aerial parts vs. root) and harvest stage; standardise expressed juice to consistent marker levels where possible.  
- Under GMP, monitor **microbial quality** carefully for fresh‑juice preparations (risk of microbial growth) and ensure adequate preservation / stability data.

---

## 3. Aloe (Aloe barbadensis Miller / Aloe vera; primarily dried latex & gel)

> Attach this section to your **Aloe** monograph. Distinguish clearly between **dried latex** (anthranoid laxative) and **leaf gel** (topical and oral nutraceutical use).

### 3.1 Regulatory status snapshot

- **WHO** – Aloe latex and aloe gel are both covered in the WHO monographs; latex is recognised as a **stimulant laxative** for short‑term use, while the gel is used mainly for **topical treatment of minor burns and skin irritation**.  
- **EMA/HMPC (EU herbal monographs)**  
  - **Aloe leaf latex (folii succus siccatus)** – Traditional herbal medicinal product for **short‑term relief of occasional constipation** in adults, based on long‑standing use.  
- **ESCOP** – ESCOP monographs similarly focus on dried latex as a stimulant laxative and on gel/topical preparations for minor skin conditions.  
- **Pharmacopoeias** – Aloe latex/gels have monographs defining identity, content of **hydroxyanthracene derivatives** and purity requirements.

### 3.2 Indications & use categories

**Traditional use (latex, oral)**  

- **Short‑term relief of occasional constipation** in adults and adolescents above a defined age (often ≥12 years), where lifestyle measures are insufficient.

**Traditional / evidence‑supported topical use (gel)**  

- **Minor burns, sunburn, superficial wounds, and irritant skin conditions**, typically as a gel or cream.  
- Supportive use in minor inflammatory skin conditions; not primarily a regulatory HMPC monograph but recognised in WHO and other expert sources.

**KB field mapping**

- `aloe.reg.trad_indications_laxative` → short‑term relief of occasional constipation (dried latex).  
- `aloe.reg.trad_indications_topical` → minor burns, sunburn, superficial wounds, irritant dermatoses (gel).  
- `aloe.reg.key_compendia` → WHO (Aloe and Aloe vera gel), EMA/HMPC (folii succus siccatus), ESCOP, major pharmacopoeias.

### 3.3 Posology ranges (regulatory‑aligned; adults)

**Dried latex (folii succus siccatus; oral)**  

- WHO/HMPC describe **single doses of dried latex corresponding to ~10–30 mg of hydroxyanthracene derivatives per day**, calculated as aloin.  
- This typically equates to **~0.04–0.11 g of dried latex** once daily at night for 1–2 weeks maximum.  
- Paediatric use is restricted or contraindicated in many monographs.

**Topical gel**  

- Applied **externally 2–4×/day** as needed to affected skin; dose defined by thin uniform film over the area rather than mg/kg.

**KB fields**

- `aloe.posology.laxative_daily_hydroxyanthracenes_mg` → 10–30  
- `aloe.posology.laxative_daily_dried_latex_g` → 0.04–0.11  
- `aloe.posology.laxative_max_duration_days` → 7–14, depending on monograph.  
- `aloe.posology.gel_application_freq_per_day` → 2–4 (topical).

### 3.4 Pharmacopoeial identity & purity tests

**Identity – latex**  

- Macroscopic/microscopic ID of aloe leaf exudate; presence of characteristic crystals and cells in transverse sections.  
- TLC / HPLC fingerprinting of **anthraquinone derivatives** (e.g., aloin A/B) vs. reference standards.

**Identity – gel**  

- Tests to distinguish genuine aloe gel from reconstituted powder or adulterated products (e.g., TLC profile of polysaccharides, absence of added sugars in compendial products).

**Purity**  

- Assay of **total hydroxyanthracene derivatives**: not less than a specified % in latex for pharmacopoeial grade.  
- Limits for **pesticides, heavy metals, microbial contamination and aflatoxins** per WHO/EMA guidance.  
- Specifications for **preservatives** and **microbial limits** in gels, if preserved.  

**KB tags**

- `aloe.qc.id_markers` → aloin A/B, other anthraquinone glycosides; polysaccharide profile (gel).  
- `aloe.qc.assay_targets` → total hydroxyanthracene derivatives; solids content of gel.  
- `aloe.qc.purity_focus` → contaminants, residual solvents (if extracted), microbes, aflatoxins.

### 3.5 GACP/GMP & safety notes

- Under GACP, harvesting should avoid contamination of gel with excessive latex when a non‑laxative product is intended.  
- For laxative products, strictly enforce **duration limits** and contraindications (e.g., intestinal obstruction, inflammatory bowel disease, pregnancy) in line with HMPC/WHO warnings.  
- GMP QC should verify **anthranoid content** and ensure accurate labelling of strength and maximum use duration.

---

## 4. Ashwagandha (Withania somnifera (L.) Dunal) — Radix Withaniae

> Attach this section to your **Ashwagandha / Radix Withaniae** monograph.

### 4.1 Regulatory status snapshot

- **WHO** – *Radix Withaniae* is included in the *WHO Monographs on Selected Medicinal Plants* (Vol. 3) as the dried root of *Withania somnifera*. Uses described include a **general tonic** and **antistress agent** to improve energy and overall health, and some specific clinical data for antistress effects.  
- **EMA/HMPC (EU herbal monographs)** – As of current public information, there is **no final EU herbal monograph** for *Withania somnifera*, although HMPC has discussed development and some national authorities allow traditional herbal products.  
- **ESCOP / other expert monographs** – ESCOP and various national expert bodies describe ashwagandha as an **adaptogenic root** used as a tonic for fatigue, stress and convalescence.  
- **USP / HMC** – USP’s Herbal Medicines Compendium and related resources describe identity/purity tests and marker specifications for ashwagandha root or extracts, with emphasis on **withanolides** as key constituents.

### 4.2 Indications & use categories

*Because there is no EU WEU monograph yet, categorise mainly as “traditional / evidence‑informed” rather than WEU.*

**Uses described in pharmacopoeias & authoritative monographs**  

- **General tonic / rasayana** to **increase energy and overall health**, particularly in the elderly or debilitated.  
- **Antistress / adaptogenic** agent to improve reaction to stressors and recovery.  

**Traditional uses (Ayurvedic & ethnomedical)**  

- Supportive treatment for **weakness, fatigue, insomnia, nervous exhaustion**, and as an adjunct in **convalescence**.  
- Additional historical uses include bronchitis, dyspepsia, sexual weakness and skin conditions; these are variably emphasised in modern monographs.

**Evidence‑supported indications (non‑regulatory, for tagging only)**  

- Modern clinical studies often focus on **stress/anxiety**, **sleep quality** and **subjective wellbeing**, using standardised root extracts.

**KB field mapping**

- `ashwagandha.reg.status` → “WHO monograph; no EU WEU monograph; traditional/adaptogenic use recognised in ESCOP/other expert sources.”  
- `ashwagandha.reg.pharmacopoeial_uses` → general tonic; antistress/adaptogen; support in elderly/fatigued.  
- `ashwagandha.reg.trad_uses` → fatigue, insomnia, nervous exhaustion, convalescence, broader rasayana roles.  

### 4.3 Posology ranges

*Split between (a) pharmacopoeial / traditional crude root and (b) modern standardised extracts.  
These are **literature‑level ranges**, not official EU posology; your KB should preserve that distinction.*

**Crude dried root (traditional)**  

- Many authoritative sources based on WHO and traditional literature describe **daily doses in the gram range**, commonly about **3–6 g/day** of dried root, usually divided in 1–3 doses (capsules, powders, decoctions).  

**Standardised extracts (modern)**  

- Clinical guidelines and monographs commonly reference **300–600 mg/day of standardised root extract** (often ~5% withanolides) in 1–2 divided doses, with trials sometimes using up to ~600 mg twice daily.  

**KB fields**

- `ashwagandha.posology.trad_root_daily_g_range` → 3–6 (tag clearly as “traditional / non‑EU regulatory”)  
- `ashwagandha.posology.extract_daily_mg_range` → 300–600 (standardised extract; non‑EU regulatory)  
- `ashwagandha.posology.notes` → “No harmonised EU regulatory posology; align with product‑specific monographs and national rules.”

### 4.4 Pharmacopoeial identity & purity tests

**Identity**  

- Macroscopic/microscopic description of dried root (buff to grey‑yellow, longitudinally wrinkled taproot with fibrous side roots).  
- Powder microscopy: cork, parenchyma with abundant starch, xylem fibres; typical calcium oxalate crystals.  
- TLC / HPLC profiles with **withanolides** (withaferin A, withanolide D, withanosides, etc.) as major markers.

**Purity (WHO Radix Withaniae template)**  

- **Foreign organic matter**: NMT ~2%.  
- **Total ash**: NMT ~7%.  
- **Acid‑insoluble ash**: NMT ~1%.  
- **Alcohol‑soluble extractive**: NLT ~15%, with water‑soluble extractive defined per national specifications.  
- Limits for **pesticides, heavy metals and radioactive residues** as per WHO guidelines on contaminants and residues.  
- Microbiological quality aligned with WHO/Ph. Eur. limits.

**KB tags**

- `ashwagandha.qc.id_markers` → withaferin A, withanolide D and related withanolides; characteristic TLC/HPLC profile.  
- `ashwagandha.qc.assay_targets` → total alkaloids (≥0.2% in WHO template), withanolide ranges if specified by pharmacopeia or product.  
- `ashwagandha.qc.purity_focus` → ash, extractives, contaminants, microbial quality.

### 4.5 GACP/GMP & special notes

- Under GACP, maintain **chemotype consistency** and document provenance (soil, climate) because withanolide profiles vary with cultivation conditions.  
- GMP should define **spec limits for withanolides and total alkaloids**, and verify absence of adulterants or misidentified roots.  
- Safety tagging in your KB should flag: **avoidance in pregnancy**, caution in hyperthyroid patients or those on sedatives/antihypertensives, as reflected in modern safety assessments.

---

## 5. Green Tea (Camellia sinensis (L.) O. Kuntze, non‑fermentatum folium)

> Attach this section to your **Green Tea** monograph (non‑fermented leaf / extracts).

### 5.1 Regulatory status snapshot

- **WHO** – Camellia sinensis leaf appears in WHO monographs with focus on **traditional beverage use** and as a source of caffeine and polyphenols (catechins).  
- **EMA/HMPC (EU herbal monographs)** – EU herbal monograph on **non‑fermented green tea leaf** describes use as a **traditional herbal medicinal product for relief of fatigue and sensation of weakness**, and includes guidance on safety concerns (especially high‑dose extracts and hepatic risk).  
- **ESCOP / expert monographs** – ESCOP and other expert sources discuss green tea for **fatigue**, **cognitive performance** and as an antioxidant, but with emphasis on safety when using concentrated extracts.  
- **USP** – USP monographs for **decaffeinated powdered green tea extract** specify assay limits for catechins (especially **EGCG**) and very low caffeine levels, providing a strong QC framework for standardised products.

### 5.2 Indications & use categories

**Traditional use (leaf infusions)**  

- Relief of **fatigue and sensation of weakness** in adults, typically as **infusions prepared from green tea leaf**.  
- General supportive use for **alertness** and **mild mental/physical performance enhancement** due to caffeine and catechins.

**Non‑regulatory / nutraceutical tagging**  

- Antioxidant support, cardiometabolic support and cognitive performance: to be clearly labelled as **evidence‑emerging / non‑regulatory** in your KB, as these are not formal HMPC indications.

**KB field mapping**

- `green_tea.reg.trad_indications` → fatigue, sensation of weakness, mild mental/physical performance support.  
- `green_tea.reg.key_compendia` → WHO, EMA/HMPC (non‑fermentatum folium), ESCOP, USP green tea extract monographs.

### 5.3 Posology ranges

*Keep a clear distinction between (a) traditional infusions and (b) concentrated extracts.*

**Traditional infusions (leaf)**  

- HMPC monograph describes daily use of infusions prepared from small amounts of comminuted leaf in hot water, taken **several times per day**, with total daily herb intake in the low gram range.  
- For KB tagging, treat this as “**multiple cups of standard‑strength green tea per day**”, without hard‑coding a strict gram range unless you mirror a specific monograph or product SPC.

**Standardised extracts (capsules / tablets)**  

- USP monographs for decaffeinated green tea extract often require defined ranges of total catechins and EGCG per dose and **very low caffeine content**; dosing regimens in clinical studies vary widely (e.g., several hundred mg EGCG/day).  
- Because hepatotoxicity signals have been reported at higher EGCG doses, note in your KB that **high‑dose extracts require stricter safety and liver‑function oversight** than traditional tea use.

**KB fields**

- `green_tea.posology.trad_use_pattern` → “several cups of infusion daily for fatigue/weakness relief (adult).”  
- `green_tea.posology.extract_notes` → “dose dependent on catechin content; follow product‑specific monograph; heed liver‑safety warnings.”  

### 5.4 Pharmacopoeial identity & purity tests

**Identity (leaf)**  

- Macroscopic and microscopic ID of non‑fermented C. sinensis leaves (shape, venation, trichomes).  
- TLC / HPLC fingerprint of **catechins** (EGCG, EGC, ECG, EC) against reference.

**Identity & assay (extracts)**  

- HPLC assays for **total polyphenols**, **total catechins** and **EGCG**, with defined minimum and maximum ranges per USP/other pharmacopeias.  
- Limit tests for **caffeine** in decaffeinated extracts (e.g., NMT low % levels).  

**Purity**

- Standard pharmacopoeial limits for **foreign matter, ash, moisture**.  
- **Pesticide residues**, **heavy metals**, **microbial counts** and **mycotoxins** per WHO/Ph. Eur./USP guidance.  
- Additional control of **solvent residues** and **residual extraction aids** for concentrated extracts.

**KB tags**

- `green_tea.qc.id_markers` → EGCG, other catechins, caffeine profile.  
- `green_tea.qc.assay_targets` → catechin content (especially EGCG), caffeine limits.  
- `green_tea.qc.purity_focus` → pesticide/heavy‑metal control (tea crops), solvent residues, microbes, mycotoxins.

### 5.5 GACP/GMP & safety notes

- GACP: document origin (country/region, altitude, cultivation system), as **pesticide use and environmental contaminants** vary significantly in tea cultivation.  
- GMP: ensure validated methods for quantifying **catechins and caffeine**; for extracts, implement **liver‑safety risk management** (dose limits, contraindications, monitoring advice).  
- In your KB, tag **special caution for high‑dose green tea extracts in patients with liver disease or on hepatotoxic drugs**, in line with regulatory warnings.

---

## Batch‑level implementation notes

For ingestion into your KB / vector store, you can treat each herb section as its own chunk group and derive structured tags:

- `*.reg.weu_indications` / `*.reg.trad_indications`  
- `*.posology.*` (sub‑fields per route/preparation)  
- `*.qc.id_markers`, `*.qc.assay_targets`, `*.qc.purity_focus`  
- `*.reg.key_compendia`  
- `*.safety.flags` / `*.gacp_gmp.notes`

This keeps the regulatory/QC layer separable from clinical narrative monographs while preserving direct linkage at the herb level.


