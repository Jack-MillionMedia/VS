---
title: "Regulatory & Quality Control Layer — Batch 6 (Hawthorn, Gotu Kola, Schisandra, Rhodiola, Calendula)"
category: "Regulatory & Quality Control"
tags: ["regulatory", "quality_control", "batch6", "hawthorn", "gotu_kola", "schisandra", "rhodiola", "calendula"]
date: "2025-11-14"
source: "WHO monographs; EMA/HMPC; ESCOP; pharmacopoeias; project regulatory batch 6"
---

# Regulatory & Quality Control Layer — Batch 6  
*Hawthorn · Gotu Kola · Schisandra Berry · Rhodiola · Calendula*  

> **Scope.** This layer encodes a **regulatory + quality‑control view** on top of your existing elite clinical monographs.  
> Sources prioritised: **WHO “Monographs on Selected Medicinal Plants”, EMA/HMPC EU herbal monographs, ESCOP monographs, Ph. Eur./USP–NF/HMC where applicable.**  
> No claims, indications, or posology are invented; where the monographs are silent or divergent, this file explicitly says so instead of guessing.  

Shared field conventions (same as earlier batches):  

- `herb_key` — short snake‑case key used across your KB.  
- `linked_core_monograph_slug` — the slug/file name for your main clinical monograph.  
- `regulatory_status` — structured notes on **traditional use (TU)** vs **well‑established use (WEU)** and non‑EU sources (WHO/ESCOP/USP).  
- `posology.*` — **adult** dosage windows derived from monographs; always treat as **typical ranges**, not product instructions.  
- `identity_purity` — high‑level QC expectations (identity, assay, contaminants).  
- `gacp_gmp` — cultivation/processing themes that should be surfaced in your “manufacturing / safety” agents.  

---

## Hawthorn (Crataegus spp., folium cum flore) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `hawthorn`
- **latin_binomial (primary):** *Crataegus monogyna* Jacq., *Crataegus laevigata* (Poir.) DC, and their hybrids  
- **primary_part(s):** leaf with flower (*Crataegi folium cum flore*)  
- **linked_core_monograph_slug:** `hawthorn_crataegus_folium_cum_flore`
- **primary_regulatory_monographs (non‑exhaustive):**  
  - **WHO:** *Folium cum Flore Crataegi* — WHO Monographs on Selected Medicinal Plants, Vol. 2  
  - **EMA/HMPC:** *European Union herbal monograph on Crataegus spp., folium cum flore* (traditional herbal medicinal product)  
  - **ESCOP:** Hawthorn leaf & flower monograph  
  - **Ph. Eur.:** *Crataegi folium cum flore* (identity & purity; assay for flavonoids / procyanidins)  

Use these exact strings (or close variants) as `regulatory_source` tags in your vector store.  

### 2. Regulatory status & indication framing

**WHO / ESCOP / older tradition‑oriented sources**  

- Treat standardized hawthorn leaf‑and‑flower extracts as **adjunctive therapy in mild cardiac insufficiency (NYHA stage II)**, with improvement in exercise tolerance, reduced palpitations and dyspnoea, and better “cardiac performance”.  
- These uses are **evidence‑supported but still require physician diagnosis and supervision**; WHO warns that proper diagnosis of heart failure is mandatory and that medical care is required if symptoms worsen or suggest angina/MI.  

**EMA/HMPC (current EU regulatory view)**  

- Classified as a **Traditional Herbal Medicinal Product (THMP)**.  
- Authorised indications (wording varies slightly by MAH) focus on:  
  - **Short‑term relief of symptoms of temporary nervous cardiac complaints**, such as **palpitations** in otherwise healthy adults.  
  - **Relief of mild symptoms of mental stress and to aid sleep.**  
- EMA explicitly does **not** authorise hawthorn as a stand‑alone treatment for diagnosed heart failure; those WHO/ESCOP indications should be surfaced as **“adjunctive / historical”** with a **clear “requires cardiology supervision” flag** in your agent.  

**Encoding suggestions**  

- `regulatory_status.eu_weu`: `none`  
- `regulatory_status.eu_tu_indications`:  
  - `"temporary_nervous_cardiac_complaints_palpitations_adults_only"`  
  - `"mild_mental_stress_and_to_aid_sleep"`  
- `regulatory_status.who_escop_adjunctive_use`:  
  - `"adjunct_in_mild_cardiac_insufficiency_NYHA_II_under_medical_supervision"`  
- `regulatory_status.clinician_alerts`:  
  - `"do_not_substitute_for_heart_failure_medication_or_acute_coronary_syndrome_care"`  

### 3. Posology ranges (adult)  

> WHO and HMPC give compatible **order‑of‑magnitude ranges** for extracts and infusions. Use these as **regulatory reference windows** only. Product‑specific SmPCs always override.  

**Standardised dry extracts (leaf with flower)**  

- WHO: **160–900 mg/day** of standardized dry extracts (45% ethanol or 70% methanol, DER ~4–7:1) containing either **≈18.75% oligomeric procyanidins** or **≈2.2% flavonoids (as hyperoside equivalents)**, typically divided into 2–3 doses over 4–8 weeks.  
- EU products using similar extracts usually sit in the **~300–900 mg/day** range for adults.  

**Comminuted crude drug (herbal tea)**  

- WHO: **1.0–1.5 g comminuted leaf‑and‑flower** infused in hot water, **3–4 times daily**.  
- Therapeutic effects may require **4–6 weeks** of continuous therapy.  

**Treatment duration flags**  

- **Self‑care (EU TU indication):**  
  - Suggest a **max 2‑week window** for “palpitations/mild stress” before physician review.  
- **Adjunctive heart‑failure use (WHO/ESCOP):**  
  - Requires **medical diagnosis and follow‑up**; duration as per cardiologist.  

**Encoding suggestions**  

- `posology.adult.extract.dose_mg_per_day`: `160–900`  
- `posology.adult.extract.notes`: `"standardised to ≈18.75% OPC or 2.2% flavonoids; DER ≈4–7:1"`  
- `posology.adult.tea.comminuted_g_per_dose`: `1.0–1.5`  
- `posology.adult.tea.doses_per_day`: `3–4`  
- `posology.treatment_duration_weeks_for_full_effect`: `4–6`  
- `posology.self_care_reassessment_days`: `14`  

### 4. Pharmacopoeial identity & purity — key tests

**Monographs referenced**: WHO *Folium cum Flore Crataegi* + Ph. Eur. *Crataegi folium cum flore*.  

High‑level tests (do **not** guess numeric limits; treat these as “test types”):  

- **Identity (herbal substance)**  
  - *Macroscopic*: flower‑bearing branchlets of *Crataegus* species with characteristic lobed leaves and white/pinkish flowers.  
  - *Microscopic*: diagnostic features in leaf and flower (epidermis, stomata, calcium oxalate crystals, sclerenchyma, etc.).  
  - *Thin‑layer chromatography (TLC)*: characteristic flavonoid pattern with **hyperoside, vitexin, vitexin-2''-O-rhamnoside, rutin**, etc.  
- **Assay / marker content**  
  - WHO and Ph. Eur. specify **minimum flavonoid or procyanidin content**, expressed as hyperoside or OPC equivalents; your QC layer should store this as:  
    - `identity_purity.assay.marker_type`: `"total_flavonoids_or_OPC"`  
    - `identity_purity.assay.minimum_spec_reference`: `"per Ph. Eur./WHO; see pharmacopoeia for numeric threshold"`  
- **Purity**  
  - Limits for **foreign organic matter**, **total ash**, **acid‑insoluble ash**, and **extractable matter**.  
  - Contaminant tests for **heavy metals, pesticide residues, aflatoxins, microbial contamination** as per WHO QC guidelines and Ph. Eur. general chapters.  

### 5. GACP / GMP focus points

- Ensure **botanical authentication** (C. monogyna, C. laevigata or hybrids) and **exclusion of non‑approved Crataegus species**.  
- Harvest flowering branches at **early flowering**, which is when flavonoid/OPC levels are optimal.  
- **Drying conditions**: moderate temperatures with good airflow and protection from direct sunlight to preserve flavonoid content.  
- Define and validate a **solvent system and DER** for standardized extracts, with ongoing assay of OPC/flavonoids.  
- Implement clear **clinical warning labels**: seek medical attention for chest pain radiating to arm/jaw, severe dyspnoea, or oedema.  

---

## Gotu Kola (Centella asiatica L., Herba Centellae) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `gotu_kola`
- **latin_binomial:** *Centella asiatica* (L.) Urb.  
- **primary_part(s):** aerial parts / entire plant (*Herba Centellae*)  
- **linked_core_monograph_slug:** `gotu_kola_centella_asiatica`
- **primary_regulatory_monographs (non‑exhaustive):**  
  - **WHO:** *Herba Centellae* — WHO Monographs on Selected Medicinal Plants, Vol. 1 (definition, QC, safety, pharmacology)  
  - **EMA:** No HMPC herbal monograph; only **lists of references** for Centella‑containing products (no EU‑wide TU/WEU indications).  
  - **National/other:** Multiple national pharmacopoeias and formularies use Centella‑based preparations for venous insufficiency, wound healing, and scars.  

### 2. Regulatory status & indication framing

Because there is **no EMA/HMPC monograph**, Centella’s regulatory framing in Europe is **national / product‑specific**. WHO and national monographs provide the most structured guidance.  

**WHO & national monographs / dossiers** commonly frame uses as:  

- **Chronic venous insufficiency / varicose veins and associated symptoms** (heavy legs, oedema, cramps).  
- **Support of wound and ulcer healing, scars, and minor burns** — mostly with **triterpenoid‑rich extracts**.  
- **Cognitive and mood support, mild anxiety** — based on limited clinical data with standardized extracts.  

To stay honest and non‑fictional in your KB:  

- Treat venous insufficiency and wound‑healing uses as **core WHO‑aligned uses**, but still requiring clinician oversight in serious vascular disease or non‑healing ulcers.  
- Treat cognitive/mood effects as **“emerging / supportive evidence”**, not as a formal regulatory indication.  
- Do **not** pretend there is an EU‑level TU/WEU classification; explicitly mark it as `none`.  

**Encoding suggestions**  

- `regulatory_status.eu_weu`: `none`  
- `regulatory_status.eu_tu_indications`: `[]`  
- `regulatory_status.who_core_indications`:  
  - `"chronic_venous_insufficiency_and_related_symptoms"`  
  - `"support_of_wound_and_ulcer_healing_scars_minor_burns"`  
- `regulatory_status.emerging_or_limited_evidence`:  
  - `"cognition_and_mood_support_with_triterpenoid_extracts"`  
- `regulatory_status.notes`: `"Indications and dosing are national/product-specific; WHO monograph provides quality and safety framework but not unified global posology."`  

### 3. Posology ranges (adult)  

> WHO describes several preparations (whole herb, extracts, topical forms) but numeric daily doses vary widely by product and formulation. To avoid introducing fictional precision, this regulatory layer **does not hard‑code mg/g ranges** and instead points back to product‑level SmPC or your core clinical monograph.  

Use structure without filling in values here:  

- `posology.adult.oral.herbal_substance_g_per_day`: `null  # see core monograph/product label`  
- `posology.adult.oral.standardised_extract_mg_per_day`: `null`  
- `posology.adult.topical.preparations`: `"creams/gels/ointments with defined asiaticoside+madecassoside content"`  
- `posology.treatment_duration_notes`: `"Chronic venous insufficiency and scar protocols are typically long-term (weeks–months); reassessment interval defined by prescriber."`  

### 4. Pharmacopoeial identity & purity — key tests (WHO Herba Centellae)

WHO gives relatively detailed QC guidance for Centella; you can encode this clearly without guessing.  

- **Identity**  
  - *Definition*: dried aerial parts or entire plant of *Centella asiatica* (L.) Urb.  
  - *Macroscopic*: slender creeping herb with long prostrate stems, characteristic rounded to reniform leaves on long petioles, and small umbels of pinkish‑white flowers.  
  - *Microscopic*: features of leaves and stems that distinguish it from other Apiaceae.  

- **Assay / marker content**  
  - Contains **not less than ~2% triterpene ester glycosides** (asiaticoside + madecassoside) in the herbal material, determined by suitable chromatographic methods (e.g., HPLC).  
  - Encoding suggestion:  
    - `identity_purity.assay.marker_type`: `"total_triterpene_glycosides (asiaticoside+madecassoside)"`  
    - `identity_purity.assay.minimum_spec_reference`: `">= 2% (WHO Herba Centellae)"`  

- **Contaminants**  
  - **Pesticide residues**: explicit WHO note that the **max residue limit for aldrin + dieldrin is 0.05 mg/kg** in the herbal material.  
  - **Heavy metals**: recommended limits **≤10 mg/kg lead** and **≤0.3 mg/kg cadmium** in the final dosage form.  
  - **Radioactive residues**: where relevant, testing for Sr‑90, I‑131, Cs‑134/137, Pu‑239 is recommended per general WHO QC guidelines.  
  - Additional tests (moisture, other pesticides, etc.) to be set by national authorities.  

**Encoding suggestions**  

- `identity_purity.contaminants.pesticides.aldrin_dieldrin_mg_per_kg_max`: `0.05`  
- `identity_purity.contaminants.heavy_metals.lead_mg_per_kg_max`: `10`  
- `identity_purity.contaminants.heavy_metals.cadmium_mg_per_kg_max`: `0.3`  
- `identity_purity.contaminants.radioactive_residues_tests`: `"per WHO QC monograph (Sr-90, I-131, Cs-134/137, Pu-239 as applicable)"`  

### 5. GACP / GMP focus points

- Centella is often cultivated in **humid, warm environments** and can concentrate contaminants; enforce strict **soil, water, and pesticide monitoring**.  
- Because triterpene content is the main quality driver, control for **harvest at appropriate growth stage** and **post‑harvest drying** that preserves asiaticoside/madecassoside.  
- Standardize any concentrated extracts to a **defined range of total triterpene glycosides** and maintain validated HPLC methods.  
- Given reported **contact dermatitis/allergy** with topical Centella preparations, surface an **allergy warning** in patient‑facing layers and in your safety agent.  

---

## Schisandra Berry (Schisandra chinensis (Turcz.) Baill., Fructus Schisandrae) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `schisandra`
- **latin_binomial:** *Schisandra chinensis* (Turcz.) Baill.  
- **primary_part(s):** dried ripe fruit (*Fructus Schisandrae*)  
- **linked_core_monograph_slug:** `schisandra_schisandra_chinensis`
- **primary_regulatory_monographs (non‑exhaustive):**  
  - **WHO:** *Fructus Schisandrae* — WHO Monographs on Selected Medicinal Plants, Vol. 3 (traditional uses, safety, QC).  
  - **ESCOP:** Schisandra fruit monograph (fatigue, stress, hepatic support).  
  - **Pharmacopoeial:** Chinese Pharmacopoeia, other national pharmacopoeias for identity/purity and lignan content.  
  - **EMA/HMPC:** No EU community herbal monograph at present; use WHO/ESCOP/national pharmacopoeias as the regulatory backbone.  

### 2. Regulatory status & indication framing

**WHO / ESCOP / national monographs** generally converge on:  

- **Traditional adaptogen / tonic** for **physical and mental fatigue, reduced work capacity, and convalescence.**  
- **Supportive use in functional respiratory and cardiovascular complaints** (e.g., exertional dyspnoea, mild palpitations) — framed as traditional/adjunctive.  
- **Hepatoprotective support** (e.g., chronic viral hepatitis, toxic liver injury) using lignan‑standardised extracts — evidence‑based but still adjunctive to standard care, not a stand‑alone treatment.  

Because there is **no EMA HMPC monograph**, you should:  

- Treat all indications as **traditional / national** rather than EU‑harmonised.  
- Surface **hepatitis and serious hepatic disease** uses as **“research/adjunctive with specialist supervision only”**, never as self‑care.  

**Encoding suggestions**  

- `regulatory_status.eu_weu`: `none`  
- `regulatory_status.eu_tu_indications`: `[]`  
- `regulatory_status.who_escop_traditional_indications`:  
  - `"adaptogen_for_physical_mental_fatigue"`  
  - `"general_tonic_for_decreased_working_capacity_and_convalescence"`  
  - `"adjunct_in_chronic_liver_disease_specialist_supervision_required"`  
- `regulatory_status.clinician_alerts`:  
  - `"do_not_delay_evidence_based_treatment_for_hepatitis_or_serious_liver_disease"`  

### 3. Posology ranges (adult)  

> WHO/ESCOP detail decoctions, powdered fruit, and standardised lignan extracts. Exact numeric ranges vary across national monographs and proprietary products. To keep this layer non‑fictional and product‑agnostic, **store only qualitative frames here** and put mg/g values in your clinical monograph where you can tie them to specific standards.  

Suggested structure (no hard‑coded numbers here):  

- `posology.adult.oral.dried_fruit_g_per_day`: `null  # typical WHO/ESCOP ranges to be stored in core monograph`  
- `posology.adult.oral.decoction_description`: `"decoctions of dried fruit taken in divided doses"`  
- `posology.adult.oral.standardised_extract_notes`: `"lignan-standardised extracts (e.g., schisandrin) with product-specific dosing"`  
- `posology.treatment_duration_notes`: `"often used in 2–6 week cycles for fatigue/tonic indications; hepatic indications require specialist-defined duration"`  

### 4. Pharmacopoeial identity & purity — key tests

Across WHO/ESCOP and pharmacopoeias, Schisandra QC is centered on **correct species and lignan profile**. Encode at a high level as follows:  

- **Identity**  
  - Dried berries of *Schisandra chinensis* with characteristic **red colour, aromatic odour, and “five-flavour” taste** (sweet, sour, salty, bitter, pungent).  
  - Microscopy of pericarp and seed (sclereids, oil cells, etc.) distinguishes it from other berries.  
  - TLC / HPLC fingerprint showing key lignans (**schisandrin, gomisin A, deoxyschisandrin**, etc.).  

- **Assay / marker content**  
  - Monographs typically define **minimum total lignan content** in the dried fruit or extracts. Encode generically as:  
    - `identity_purity.assay.marker_type`: `"total_dibenzocyclooctadiene_lignans"`  
    - `identity_purity.assay.minimum_spec_reference`: `"per WHO/ESCOP/Chinese Pharmacopoeia; product-specific numeric limits"`  

- **Purity and contaminants**  
  - Standard limits for foreign matter, ash, moisture, pesticide residues, heavy metals, and microbial contamination according to WHO QC and national pharmacopoeias.  

### 5. GACP / GMP focus points

- Ensure **authentic *Schisandra chinensis*** (not *S. sphenanthera* unless specifically intended), as lignan profiles and safety differ.  
- Control for **post‑harvest drying** to preserve lignan content and prevent mould; berries are sugar‑rich and prone to microbial growth.  
- For extracts, standardise to clearly defined **lignan content** and maintain validated chromatographic assays.  
- Because Schisandra is used in **liver disease**, enforce stringent **residual solvent, mycotoxin, and heavy‑metal limits** and integrate them into your “hepatoprotective” safety checks.  

---

## Rhodiola (Rhodiola rosea L., rhizoma et radix) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `rhodiola`
- **latin_binomial:** *Rhodiola rosea* L.  
- **primary_part(s):** rhizome and root (*Rhodiolae roseae rhizoma et radix*)  
- **linked_core_monograph_slug:** `rhodiola_rhodiola_rosea`
- **primary_regulatory_monographs (non‑exhaustive):**  
  - **EMA/HMPC:** *European Union herbal monograph on Rhodiola rosea L., rhizoma et radix* (traditional use)  
  - **WHO:** No dedicated WHO monograph yet; evidence base summarised in EMA and national assessments.  
  - **Other:** National monographs (e.g., Nordic countries, Russia), ESCOP reviews, Health Canada NHP monograph aligned with HMPC.  

### 2. Regulatory status & indication framing

**EMA/HMPC traditional‑use classification**  

- Rhodiola is classified as a **Traditional Herbal Medicinal Product (THMP)** for:  
  - **Temporary relief of symptoms of stress**, such as **fatigue and sensation of weakness**, in adults.  
- HMPC emphasises:  
  - Use only in **adults**.  
  - Self‑medication should be **short‑term**, and medical advice is recommended if symptoms persist beyond about **2 weeks** or if signs of depression/serious disease appear.  

No EU **well‑established use** indication is granted. Antidepressant or cognitive claims remain outside the authorised wording and should be surfaced in your KB as **“research/adjunctive only”**.  

**Encoding suggestions**  

- `regulatory_status.eu_weu`: `none`  
- `regulatory_status.eu_tu_indications`:  
  - `"temporary_relief_of_stress_related_fatigue_and_weakness_in_adults"`  
- `regulatory_status.off_label_or_research_areas`:  
  - `"depressive_symptoms_and_anxiety (research-level, not authorised indication)"`  

### 3. Posology ranges (adult, HMPC‑aligned)

> HMPC and aligned national monographs give relatively tight windows for ethanol‑extract preparations of Rhodiola. Values below reflect **typical ranges for standardised dry extracts**, not all possible products. Always match to DER and extract solvent.  

**Standardised dry extract (oral, adults)**  

- Typical HMPC‑aligned preparations use **hydroalcoholic extracts** (e.g., 60% ethanol, DER ~1.5–5:1).  
- **Single dose:** ~**144–200 mg** extract.  
- **Daily dose:** approx. **288–400 mg/day**, with some products allowing up to **≈680 mg/day** for short‑term use.  
- **Duration:** usually **1–2 weeks** for self‑care in stress‑related fatigue before clinical reassessment.  

**Encoding suggestions**  

- `posology.adult.extract.single_dose_mg`: `144–200`  
- `posology.adult.extract.total_daily_dose_mg`: `288–400 (max ≈680)`  
- `posology.treatment_duration_self_care_max_days`: `14`  
- `posology.dosing_notes`: `"Take in the morning (and early afternoon if divided) to avoid insomnia; adults only."`  

### 4. Pharmacopoeial identity & purity — key tests

- **Identity (herbal substance)**  
  - Dried rhizomes and roots of *Rhodiola rosea* with characteristic **rose‑like aroma**, golden exterior, and fibrous fracture.  
  - Microscopy: parenchyma with oil cells, characteristic vascular patterns, etc.  
  - Chromatographic fingerprint with markers such as **rosavin, salidroside** and related phenylpropanoid glycosides.  

- **Assay / marker content**  
  - HMPC/national monographs typically require **standardisation to defined amounts of rosavin(s) and salidroside** in the extract.  
  - Encoding suggestion:  
    - `identity_purity.assay.marker_type`: `"rosavin_group_and_salidroside"`  
    - `identity_purity.assay.minimum_spec_reference`: `"per HMPC/national pharmacopoeias; product-specific"`  

- **Purity**  
  - Standard tests: foreign matter, ash values, loss on drying, extractable matter.  
  - Contaminants: heavy metals, pesticide residues, microbial contamination and residual solvents in line with Ph. Eur. general monographs.  

### 5. GACP / GMP focus points

- **Species and plant‑part authentication**: ensure only *R. rosea* rhizome/root is used; distinguish from other Rhodiola species with different profiles and potentially different safety.  
- **Sustainable sourcing**: wild populations have been overharvested in some regions; GACP should address cultivation or controlled wild‑collection with conservation measures.  
- **Standardisation**: maintain tight control of **rosavin/salidroside content** and define acceptable DER and solvent systems.  
- **Labeling**: emphasise **short‑term use for stress‑related fatigue** and clear warnings about depression, insomnia, and interactions with other CNS‑active agents.  

---

## Calendula (Calendula officinalis L., flos) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `calendula`
- **latin_binomial:** *Calendula officinalis* L.  
- **primary_part(s):** dried flower heads / ligulate florets (*Calendulae flos*)  
- **linked_core_monograph_slug:** `calendula_calendula_officinalis`
- **primary_regulatory_monographs (non‑exhaustive):**  
  - **WHO:** *Flos Calendulae* — WHO Monographs on Selected Medicinal Plants, Vol. 2 (topical/mucosal uses, QC).  
  - **EMA/HMPC:** *European Union herbal monograph on Calendula officinalis L., flos* (traditional use).  
  - **ESCOP:** Calendula flower monograph.  
  - **Ph. Eur.:** *Calendulae flos* (identity, purity, assay of flavonoids/triterpenoids).  

### 2. Regulatory status & indication framing

**EMA/HMPC (traditional‑use, topical + oromucosal)**  

Authorised traditional indications in adults and adolescents generally include:  

- **Symptomatic treatment of minor inflammations of the skin**, such as **mild sunburn and small superficial wounds**.  
- **Aid in the healing of minor wounds**.  
- **Mild inflammation of the oral mucosa**, using diluted preparations as a mouth rinse or gargle.  

All indications are **topical/oromucosal**; there is **no authorised internal systemic indication** in the EU monograph. Oral use should be treated as **folk / off‑label** and clearly flagged as such.  

**Encoding suggestions**  

- `regulatory_status.eu_weu`: `none`  
- `regulatory_status.eu_tu_indications`:  
  - `"minor_inflammatory_conditions_of_skin_e_g_sunburn_small_wounds"`  
  - `"aid_in_healing_of_minor_wounds"`  
  - `"mild_inflammation_of_oral_mucosa_mouth_rinse_or_gargle"`  
- `regulatory_status.off_label_or_folk_uses`:  
  - `"internal_use_for_gi_spasm_or_menstrual_complaints_traditional_only_not_EU_authorised"`  

### 3. Posology ranges (adult, topical/oromucosal)

> EMA/HMPC expresses posology mostly as **percentage of herbal substance in semi‑solid or liquid preparations**, not as mg/kg. Values below reflect typical ranges seen in monograph‑aligned products; always cross‑check against specific SmPC.  

**Topical semi‑solid preparations (creams/ointments/gels)**  

- Ointments/creams often contain roughly **2–5% dried calendula flower** (or an equivalent amount of tincture/extract) applied **2–4 times daily** to affected areas.  

**Liquid preparations for compresses / rinses**  

- Diluted tinctures or infusions comparable to **1–2 g dried flowers in ~150 mL hot water**, used externally (compresses, rinses) **several times daily**.  
- For mouth rinses/gargles: a dilute aqueous preparation used **2–4 times daily**, with instructions not to swallow.  

**Encoding suggestions**  

- `posology.adult.topical.semisolid_herbal_percent`: `2–5`  
- `posology.adult.topical.applications_per_day`: `2–4`  
- `posology.adult.oral_mucosa.rinse_herbal_equivalent_g_per_150ml`: `≈1–2`  
- `posology.adult.oral_mucosa.rinse_frequency_per_day`: `2–4`  
- `posology.treatment_duration_notes`: `"If symptoms worsen or do not improve within about 1 week, or if signs of infection appear, seek medical advice."`  

### 4. Pharmacopoeial identity & purity — key tests

- **Identity**  
  - *Macroscopic*: orange to yellow ligulate florets or whole flower heads of *Calendula officinalis*.  
  - *Microscopic*: characteristic trichomes, resin passages, and pollen morphology.  
  - TLC fingerprint demonstrating flavonoids and triterpenoid saponins typical of calendula.  

- **Assay / marker content**  
  - Monographs generally require a **minimum content of total flavonoids or triterpenoid saponins**, often expressed as hyperoside or other reference standards.  
  - Encoding suggestion:  
    - `identity_purity.assay.marker_type`: `"total_flavonoids_and/or_triterpenoid_saponins"`  
    - `identity_purity.assay.minimum_spec_reference`: `"per Ph. Eur./WHO; numeric value product-specific"`  

- **Purity**  
  - Limits for foreign matter (e.g., other Asteraceae florets), ash values, moisture, and extractable matter.  
  - Contaminant tests for heavy metals, pesticide residues, aflatoxins and microbial contamination, especially for semi‑solid products used on broken skin.  

### 5. GACP / GMP focus points

- **Species purity**: avoid substitution with other ornamental Calendula species or unrelated Asteraceae.  
- Ensure **low bioburden** and absence of fungal contamination, as calendula is often used on **broken or irritated skin**.  
- Where tinctures are used, validate **residual solvent limits** and content of key triterpenoids/flavonoids.  
- For oromucosal products, ensure **taste, excipients, and preservatives** are appropriate for repeated mouth exposure, with attention to allergenicity.  

---

## Integration notes for Batch 6

For each herb in this batch, you now have:  

1. A **stable `herb_key` and `linked_core_monograph_slug`**, which you can use to join this regulatory/QC layer to your existing clinical monographs.  
2. **Regulatory status fields** that make it clear **what is actually authorised (TU)**, what lacks WEU, and which uses remain **adjunctive or research‑level**.  
3. **Posology structures** that you can safely populate in agents without fabricating numbers; where data are not encoded here (Centella, Schisandra dose ranges), deliberately leave them `null` or refer to your core monographs.  
4. **Identity/purity & GACP/GMP hooks** that let a “manufacturing / safety” agent reason about assay requirements, contaminants, and sourcing quality without needing to see the full pharmacopoeial text.  

You can now ingest this file as another markdown document in your vector store (e.g., tagged `layer:regulatory_qc`, `batch:6`), and wire your router so that:  

- Clinical questions hit the **core monographs**,  
- While any question about **regulation, dosing windows, quality standards, contaminants, or manufacturing** preferentially pulls from this regulatory/QC layer.


