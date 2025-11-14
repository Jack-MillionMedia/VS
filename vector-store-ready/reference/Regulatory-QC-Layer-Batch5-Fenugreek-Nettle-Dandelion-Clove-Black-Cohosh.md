---
title: "Regulatory & Quality Control Layer — Batch 5 (Fenugreek, Nettle, Dandelion, Clove, Black Cohosh)"
category: "Regulatory & Quality Control"
tags: ["regulatory", "quality_control", "batch5", "fenugreek", "nettle", "dandelion", "clove", "black_cohosh"]
date: "2025-11-14"
source: "WHO monographs; EMA/HMPC; ESCOP; pharmacopoeias; project regulatory batch 5"
---

# Regulatory & Quality Control Layer — Batch 5  
*Fenugreek · Nettle · Dandelion · Clove · Black Cohosh*  

> Scope: This layer encodes high‑level regulatory and quality‑control information from HMPC/EMA EU herbal monographs, ESCOP monographs, pharmacopoeial standards (e.g., Ph. Eur.), and where relevant major national monographs (e.g., Health Canada) so it can be linked to your existing clinical/PK/pharmacology monographs.  
> It is **not** a prescribing guide and should always be interpreted in the context of the underlying official monographs and product‑specific SmPCs.

---

## Fenugreek (Trigonella foenum-graecum L., semen) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `fenugreek`
- **latin_binomial:** *Trigonella foenum‑graecum* L.  
- **primary_part(s):** seeds (*Trigonellae foenugraeci semen*)  
- **linked_core_monograph_slug:** `fenugreek_trigonella_foenum_graecum`
- **primary_regulatory_monographs (non‑exhaustive):**  
  - EU HMPC: *European Union herbal monograph on Trigonella foenum‑graecum L., semen* (traditional use)  
  - ESCOP: Fenugreek seed monograph  
  - Commission E: Fenugreek seed internal/external use  
  - Ph. Eur.: *Trigonellae foenugraeci semen* (identity & purity only; no indications)

Use these strings (or stable variants) as `regulatory_source` tags in your vector store.

---

### 2. Regulatory status & indication framing

**EU HMPC (traditional use only)**  

- **Regulatory category:** Traditional herbal medicinal product (TU); HMPC explicitly concludes that criteria for a **well‑established use (WEU)** indication are **not** fulfilled.  
- **Recognised TU indications (EU level, oral and external):**  
  - Internal: **Traditional herbal medicinal product for loss of appetite.**  
  - External: **Traditional herbal medicinal product for minor skin inflammations** (e.g., poultices/cataplasms applied to localized inflammatory skin conditions).  

**ESCOP & other expert monographs (practice‑level context, not EU claims):**  

- ESCOP describes internal use as **supportive** in:  
  - Mild dyspeptic complaints and loss of appetite.  
  - Dietary management of **mild hypercholesterolaemia** and **type 2 diabetes** (adjunctive to diet and standard care).  
- External use for: **boils, ulcers, eczema and other localized inflammatory skin conditions**, typically as warm poultices.  

**How to encode in your KB**  

- `reg_status.eu`: `"TU_only"`  
- `eu_indications_primary`:  
  - `"loss_of_appetite (oral)"`  
  - `"minor_skin_inflammations (topical poultice)"`  
- `escop_additional_uses` (flag as "supportive / non‑EU‑claim"):  
  - `"adjunct_in_mild_hypercholesterolaemia"`  
  - `"adjunct_in_type2_diabetes_dietary_support"`  
  - `"topical_for_boils_ulcers_eczema"`  

---

### 3. Posology ranges (regulatory / monograph‑based)

> Always map **preparation‑specific** posology in your core clinical monographs. The ranges below are **typical monograph‑level windows**, not product doses.

**Oral (seeds)**  

- ESCOP/European expert sources report: **approx. 1–6 g whole or coarsely powdered seeds per day**, divided, taken with liquid.  
- HMPC uses similar ranges in TU monograph (seeds as comminuted herbal substance, dry preparations, and other oral dosage forms); details differ by DER and solvent and should be taken from the specific product/SmPC.

**Topical poultice**  

- Traditional preparations: ~**50 g powdered seeds** boiled briefly in ~250 mL water to a soft paste, applied warm as a poultice several times daily to the affected area.  
- These preparations are generally treated as **traditional external pharmaceutical forms**; detailed instructions are product‑specific.

**Encoding suggestions**  

- `posology.adult.oral.dried_seed_g_per_day`: `1–6`  
- `posology.adult.topical.poultice_powder_g_per_batch`: `≈50`  
- Add per‑product fields in core monographs for DER‑standardised dry extracts or specialised preparations (e.g., proprietary fenugreek seed extracts).  

---

### 4. Pharmacopoeial identity & purity tests (high‑level)

**Ph. Eur. “Trigonellae foenugraeci semen”** (quality framework):  

- **Identity tests:**  
  - Macroscopic and microscopic description of seeds (size, shape, hilum, endosperm; characteristic yellow‑brown colour and odour).  
  - **Thin‑layer chromatography (TLC)** for characteristic constituents such as **trigonelline** and saponins (and/or comparison with reference standard).  
- **Purity tests (examples):**  
  - Limits on **foreign matter**, **loss on drying**, **total ash**.  
  - Microbial quality per Ph. Eur. general chapters for herbal drugs.  
  - Limits for **pesticide residues**, **heavy metals**, and **aflatoxins**, by cross‑reference to general monographs.  
- **Assay / performance tests:**  
  - Where specified, swelling or other physical parameters may be used to reflect mucilage‑rich nature; some standards include minimum **swelling index** or general “extractable matter” tests.  

**Encoding suggestions**  

- `qc.pharmacopeial_monographs`: `["Ph. Eur. Trigonellae foenugraeci semen"]`  
- `qc.identity.primary_markers`: `["trigonelline (TLC)", "steroidal_saponins", "macroscopic/microscopic_seed_profile"]`  
- `qc.key_physical_tests`: `["swelling_index_or_extractive", "loss_on_drying", "total_ash"]`  
- `qc.contaminant_panels`: `["microbial_limits", "pesticide_residues", "heavy_metals", "aflatoxins"]`  

---

### 5. GACP / GMP & manufacturing notes

- **Botanical identity:** Cultivate/collect correctly identified *T. foenum‑graecum*, typically **ripe, dried seeds**; avoid admixture of other Fabaceae seeds.  
- **Agronomy / collection (GACP):**  
  - Controlled use of agrochemicals compatible with Ph. Eur./USP pesticide limits.  
  - Proper drying to protect mucilage and saponin profile (avoid excessive heat that might degrade lipids and generate rancidity).  
- **Processing:**  
  - Cleaning and sieving to remove stones, dust, and other seeds.  
  - Milling under controlled conditions to avoid overheating and clumping of mucilage.  
- **GMP‑level concerns:**  
  - Allergenicity (cross‑reactivity with legumes such as peanut and chickpea has been reported); manufacturers often include **allergy warnings**.  
  - Avoid contamination with peanut or other allergenic seeds during processing.  
  - Standardisation of extracts (if used) to a defined range of **saponins** and/or other markers with validated analytical methods.  

Use this layer to enforce: “Only ingestible products with Ph. Eur./USP‑compliant seed material and monograph‑consistent TU indications should be exposed as ‘regulatory‑aligned’ fenugreek in your agent.”

---

## Nettle (Urtica dioica L. / Urtica urens L.) — Regulatory & QC Profile

> Nettle has multiple EU monographs (herb, leaf, root) with **different indications and posology**. This layer focuses on **herb/leaf and root** separately so you can route correctly from your core monographs.

### 1. Linkage metadata

- **herb_key:** `nettle`
- **latin_binomials:**  
  - *Urtica dioica* L.  
  - *Urtica urens* L.  
- **primary_parts:**  
  - Herb/leaf (*Urticae herba*, *Urticae folium*).  
  - Root (*Urticae radix*).  
- **linked_core_monograph_slugs:**  
  - `nettle_herb_urtica_dioica_urens`  
  - `nettle_root_urtica_dioica_urens`  
- **primary_regulatory_monographs:**  
  - EU HMPC: *European Union herbal monograph on Urtica dioica L.; Urtica urens L., herba* (TU; 2025 revision).  
  - EU HMPC: *…folium* (TU; leaf).  
  - EU HMPC: *…radix* (nettle root; WEU for LUTS in BPH).  
  - ESCOP monographs on nettle herb/leaf and root.  
  - Ph. Eur. monographs for herb/leaf/root where available (identity & purity).  

---

### 2. Regulatory status & indication framing

#### 2.1 Nettle herb/leaf (Urticae herba / folium)

**EU HMPC (herb/leaf, TU)**  

- **Regulatory category:** Traditional herbal medicinal product (TU).  
- **Typical TU indications (herb/leaf):**  
  - Increase urine output to **flush the urinary tract** as an adjuvant in **minor urinary complaints** (e.g., burning/irritative symptoms, in absence of serious disease).  
  - Relief of **minor articular pain** (herb) and supportive use in **rheumatic complaints**.  
  - Older monographs also reference **seborrhoeic skin conditions** as topical TU.  

**Encoding for herb/leaf**  

- `reg_status.eu.herb_leaf`: `"TU_only"`  
- `eu_indications_primary.herb_leaf`:  
  - `"urinary_tract_flushing_in_minor_urinary_complaints (oral)"`  
  - `"minor_articular_pain_rheumatic_complaints (oral)"`  

#### 2.2 Nettle root (Urticae radix)

**EU HMPC (root, WEU)**  

- **Regulatory category:** **Well‑established use (WEU)** for specific root extracts; TU category as fallback for other preparations.  
- **WEU indication (root):**  
  - **Relief of lower urinary tract symptoms (LUTS) related to benign prostatic hyperplasia (BPH)** after serious conditions have been excluded by a physician.  
- **Important framing:**  
  - Symptomatic treatment only; **no evidence of reduction in prostate size** or disease progression.  
  - For men only; **not for women or children**.  

**Encoding for root**  

- `reg_status.eu.root`: `"WEU_and_TU"`  
- `eu_indications_primary.root`:  
  - `"LUTS_related_to_BPH (adult_men_only)"`  

---

### 3. Posology ranges (regulatory / monograph‑based)

#### 3.1 Herb/leaf (TU)

**Comminuted herb as tea** (HMPC, TU):  

- **Single dose (SD):** ~**1.5 g** comminuted herbal substance in 150 mL boiling water as infusion.  
- **Daily dose (DD):** approx. **4.5–6 g** herb per day in divided doses.  

**Other preparations (expressed juice, liquid extracts, tincture, dry extracts)**  

- HMPC monograph specifies daily doses for several preparations (fresh expressed juice, liquid extracts, tincture, dry extracts). Typical adult ranges:  
  - **Expressed juice:** ~7.5–15 mL/day.  
  - **Liquid extract (1:1, ethanol 25%):** ~6–12 mL/day.  
  - **Tincture (1:5, ethanol 45%):** up to ~18 mL/day.  
  - **Dry extract (5–10:1, aqueous):** ~1.2–1.35 g/day.  

> Exact numbers depend on the specific DER and must be taken from the product label/SmPC.

#### 3.2 Root (WEU) — LUTS/BPH

**Comminuted root as tea**  

- **SD:** around **2 g** comminuted root in 150 mL water, 2–3 times daily.  

**Standardised dry extracts (examples from HMPC monograph)**  

- Dry extracts in DER ranges such as **7–14:1 (methanol 20%)**, **5.4–8.3:1 (ethanol 20%)**, **12–16:1 (ethanol 70%)**, etc., with typical daily doses in the **300–720 mg/day** window depending on preparation and dosing schedule.  

**Encoding suggestions**  

- `posology.adult.herb_leaf.tea_herb_g_per_day`: `4.5–6`  
- `posology.adult.root.extract_mg_per_day`: `≈300–720` (flagged as range; product‑specific values go to core monograph)  
- `posology.special_notes`: `"ensure adequate fluid intake for urinary_flushing_indications; monitor LUTS and refer if symptoms worsen"`  

---

### 4. Pharmacopoeial identity & purity tests (high‑level)

**Herb/leaf/root quality frameworks (Ph. Eur.)**  

- **Identity:**  
  - Macroscopic and microscopic description of aerial parts or root (leaf morphology, stinging hairs, root structure).  
  - TLC fingerprints for **flavonoids**, **phenolic acids**, and other characteristic constituents depending on plant part.  
- **Purity:**  
  - Limits for foreign matter, loss on drying, total ash, acid‑insoluble ash.  
  - Microbiological quality and contamination limits (pesticides, heavy metals, aflatoxins) per Ph. Eur. general monographs.  
- **Assay:**  
  - Some monographs specify minimum content of certain extractives or marker compounds; others rely on chromatographic fingerprints plus general extractable matter tests.  

**Encoding suggestions**  

- `qc.pharmacopeial_monographs`:  
  - `["Ph. Eur. Urticae herba", "Ph. Eur. Urticae folium", "Ph. Eur. Urticae radix"]` (where applicable)  
- `qc.identity.primary_markers.herb_leaf`: `["flavonoid_profile (e.g., quercetin_glycosides)", "stinging_hairs", "macroscopic_leaf/herb"]`  
- `qc.identity.primary_markers.root`: `["lignans/sterols_profile", "macroscopic_root"]`  
- `qc.contaminant_panels`: `["microbial_limits", "pesticide_residues", "heavy_metals", "aflatoxins"]`  

---

### 5. GACP / GMP & manufacturing notes

- **Herb/leaf:** harvest above‑ground parts during vegetative growth before flowering, avoiding excessive mechanical damage that destroys stinging hairs (they are part of identity profile).  
- **Root:** harvest in autumn or early spring from mature plants; wash, slice if necessary, and dry at temperatures preserving phytosterol/lignan profile.  
- **GACP:** ensure collection sites are free from heavy metal and nitrate contamination (nettles are nitrophilous and can accumulate contaminants).  
- **Processing:** cleaning, controlled drying, and milling; segregate herb vs root materials with clear traceability.  
- **GMP:**  
  - Validate extraction processes for root extracts used in BPH indications (consistent DER and solvent).  
  - For LUTS/BPH products, robust stability data and content uniformity for the active extract are essential.  

Use this layer in your agent to ensure **clear separation** between TU indications (herb/leaf) and **WEU LUTS/BPH** use (root), with part‑specific QC expectations.

---

## Dandelion (Taraxacum officinale Weber ex Wigg.) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `dandelion`
- **latin_binomial:** *Taraxacum officinale* Weber ex Wigg.  
- **primary_parts:**  
  - Root (*Taraxaci radix*).  
  - Root with herb (*Taraxaci radix cum herba*).  
  - Leaf (*Taraxaci folium*).  
- **linked_core_monograph_slugs:**  
  - `dandelion_root_taraxacum_officinale`  
  - `dandelion_root_plus_herb_taraxacum_officinale`  
  - `dandelion_leaf_taraxacum_officinale`  
- **primary_regulatory_monographs:**  
  - EU HMPC: *Community/EU herbal monograph on Taraxacum officinale Weber ex Wigg., radix cum herba* (TU).  
  - EU HMPC: *…folium* (leaf).  
  - EU HMPC: *Taraxaci officinalis radix* (root; TU monograph for root alone).  
  - WHO and national (e.g., Health Canada) monographs referencing EMA TU indications (diuretic, digestive).  
  - Ph. Eur. monographs for Taraxacum root/leaf where applicable.  

---

### 2. Regulatory status & indication framing

**EU HMPC (radix / radix cum herba / folium)**  

- **Regulatory category:** Traditional herbal medicinal products (TU).  
- **Key TU indications (summarised across parts):**  
  - **Increase urine output** to promote **flushing of the urinary tract**, as an adjuvant in **minor urinary complaints**.  
  - Relief of symptoms related to **mild digestive disorders** (e.g., feeling of fullness, slow digestion).  
  - Traditional use as **digestive aid and appetite stimulant**.  
- Monographs emphasise that use is based on **long‑standing tradition**, not modern RCT‑level evidence.  

**Encoding suggestions**  

- `reg_status.eu`: `"TU_only (all_parts)"`  
- `eu_indications_primary`:  
  - `"urinary_tract_flushing_in_minor_urinary_complaints"`  
  - `"relief_of_mild_dyspeptic_complaints"`  
  - `"stimulation_of_appetite (traditional)"`  

---

### 3. Posology ranges (regulatory / monograph‑based)

> Exact dosing varies by plant part and dosage form. Below are **typical TU‑level ranges** used by EMA/major national monographs; your core monographs should store formulation‑specific numbers.

- **Dried root or root with herb (comminuted, as tea/decoction):** daily dose generally in the **gram‑scale range**, divided into 2–3 doses (e.g., tea prepared with several grams of drug per day).  
- **Leaf (folium):** similar daily drug quantities, again in multiple divided doses, primarily for diuretic/urinary‑flushing indications.  
- **Standardised preparations (extracts):** monographs specify posology for specific DERs and solvents; these should be mapped **at the product‑level** in your core monographs, not generalised.  

**Encoding suggestions**  

- `posology.adult.oral.radix_cum_herba_dried_g_per_day`: `"few-gram_range (per EMA TU monograph; see product SmPC)"`  
- `posology.adult.oral.folium_dried_g_per_day`: `"few-gram_range (per EMA TU monograph; see product SmPC)"`  
- Add concrete numbers only when they come from a specific monograph you’ve parsed into your core dataset.  

---

### 4. Pharmacopoeial identity & purity tests (high‑level)

**Typical Ph. Eur. requirements (root/leaf):**  

- **Identity:**  
  - Macroscopy and microscopy for root and leaf (taproot morphology; milky latex; leaf shape/dentition).  
  - TLC fingerprint for **sesquiterpene lactones**, phenolic acids (e.g., caffeoyltartaric derivatives), and/or flavonoids.  
- **Purity:**  
  - Limits for foreign matter (especially other Asteraceae species), loss on drying, total ash, acid‑insoluble ash.  
  - Limits for **pesticide residues**, **heavy metals** and **aflatoxins** via general monographs.  
- **Assay:**  
  - Some standards specify a minimum level of **extractable matter** and occasionally compositional guidance for characteristic constituents (e.g., hydroxycinnamic acids).  

**Encoding suggestions**  

- `qc.pharmacopeial_monographs`: `["Ph. Eur. Taraxaci radix", "Ph. Eur. Taraxaci folium"]` (as applicable)  
- `qc.identity.primary_markers`: `["macroscopic_root/leaf_profile", "TLC_sesquiterpene_lactones", "TLC_caffeoyltartaric_acids"]`  
- `qc.note.cross_reactivity`: `"check hypersensitivity to other Asteraceae (Compositae) species"`  

---

### 5. GACP / GMP & manufacturing notes

- **GACP:**  
  - Ensure correct identification of *T. officinale* in complex genus; avoid misidentification with related species.  
  - Avoid collection from polluted sites (roadsides, industrial ground) due to heavy metal and other contamination.  
- **Processing:**  
  - Root: harvest in early spring or autumn; wash, cut and dry under controlled temperature.  
  - Leaf: harvest healthy leaves; dry rapidly in thin layers to preserve colour and phenolic profile.  
- **GMP:**  
  - Clear segregation and labelling of **root**, **root+herb**, and **leaf** based preparations since indications may differ slightly.  
  - Bioburden control and stability data for extracts and finished products.  

Use this layer to **gate diuretic and digestive claims** for dandelion to TU‑consistent contexts and to enforce Asteraceae allergy warnings and contamination checks.

---

## Clove (Syzygium aromaticum (L.) Merr. & L.M.Perry) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `clove`
- **latin_binomial:** *Syzygium aromaticum* (L.) Merr. & L.M.Perry  
- **primary_parts:**  
  - Dried flower buds (*Caryophylli flos*).  
  - Essential oil (*Syzygii aromatici aetheroleum* / clove oil).  
- **linked_core_monograph_slugs:**  
  - `clove_flower_bud_syzygium_aromaticum`  
  - `clove_oil_syzygium_aromaticum`  
- **primary_regulatory_monographs:**  
  - EU HMPC: *European Union herbal monograph on Syzygium aromaticum aetheroleum/Caryophylli flos* (TU).  
  - ESCOP monograph on clove/clove oil (mainly dental uses).  
  - Pharmacopoeial standards: Ph. Eur. *Caryophylli flos* and *Caryophylli aetheroleum* (identity & purity).  

---

### 2. Regulatory status & indication framing

**EU HMPC (essential oil; TU)**  

- **Regulatory category:** Traditional herbal medicinal product (TU).  
- **Recognised TU indication (essential oil/topical oral use):**  
  - **Temporary relief of toothache due to dental caries**, typically via topical application in the mouth (e.g., mouthwash, cotton pledget).  
- Internal systemic use is **not** part of EU HMPC medicinal indications.  

**ESCOP / other expert sources**  

- Broadly aligned with EU HMPC: clove oil mainly as **topical dental analgesic**; sometimes as adjunct in **oral antiseptic mouth rinses**.  

**Encoding suggestions**  

- `reg_status.eu`: `"TU_only (clove_oil)"`  
- `eu_indications_primary`:  
  - `"temporary_relief_of_toothache_due_to_dental_caries (topical_in_mouth)"`  
- Flag any systemic/internally ingested clove oil products in your KB as **“off‑label / non‑regulatory‑aligned”**.  

---

### 3. Posology ranges (regulatory / monograph‑based)

> EMA/HMPC provides detailed posology for authorised preparations; here you encode the **typical ranges**, and keep exact figures in formulation‑specific monograph entries.

- **Mouthwashes/gargles:** solutions corresponding to approximately **1–5% clove essential oil**, used a few times daily for short periods for dental pain.  
- **Direct application:** small quantities of clove oil (often on a cotton pellet) applied to the painful tooth area **short‑term only**; EMA emphasises that such use is time‑limited and that dental evaluation is required.  

**Encoding suggestions**  

- `posology.adult.topical_oral.mouthwash_clove_oil_percent`: `1–5`  
- `posology.adult.topical_oral.max_duration_days`: `"short_term_only; refer_to_dentist_if_pain_persists"`  

---

### 4. Pharmacopoeial identity & purity tests (high‑level)

**Flower buds (Caryophylli flos)**  

- **Identity:**  
  - Macroscopy/microscopy of dried flower buds.  
  - TLC / GC fingerprints showing **eugenol** and related phenylpropanoids.  
- **Purity & assay:**  
  - Limits on foreign matter, loss on drying, ash values.  
  - **Essential oil content** not less than a specified percentage by distillation.  
  - Contaminant limits as per Ph. Eur. (pesticides, heavy metals, aflatoxins).  

**Essential oil (Caryophylli aetheroleum)**  

- **Identity / composition:**  
  - GC profile with **eugenol** as the principal component within defined ranges; also eugenyl acetate and β‑caryophyllene.  
- **Purity:**  
  - Limits on non‑volatile residue, refractive index, relative density, and other physical parameters.  
  - Contaminant tests including peroxides/oxidation state where specified.  

**Encoding suggestions**  

- `qc.pharmacopeial_monographs`: `["Ph. Eur. Caryophylli flos", "Ph. Eur. Caryophylli aetheroleum"]`  
- `qc.identity.primary_markers`: `["eugenol (GC/TLC)", "budding_flower_morphology"]`  
- `qc.assay.requirement`: `"minimum_essential_oil_content_for_flower_buds; defined_eugenol_range_for_oil"`  

---

### 5. GACP / GMP & manufacturing notes

- **GACP:**  
  - Correct harvesting of unopened flower buds from *S. aromaticum* trees; careful drying to preserve oil content.  
- **Processing:**  
  - Proper storage in well‑closed containers protected from light and heat to prevent oxidation and loss of essential oil.  
- **GMP:**  
  - Oxidised clove oil is more irritant; manufacturers should monitor **peroxide value/oxidation** and set appropriate shelf‑life.  
  - Because essential oils are concentrated, dosing devices and clear labeling (especially around **short‑term use** and **avoidance in young children**) are important.  

This layer should cause your agent to **restrict clove to topical dental uses** when answering from a “regulatory‑aligned” standpoint and to emphasise limited duration and need for dental assessment.

---

## Black Cohosh (Actaea racemosa L., syn. Cimicifuga racemosa) — Regulatory & QC Profile

### 1. Linkage metadata

- **herb_key:** `black_cohosh`
- **latin_binomial:** *Actaea racemosa* L. (syn. *Cimicifuga racemosa* (L.) Nutt.)  
- **primary_part:** rhizome with root (*Cimicifugae/Actaeae rhizoma*).  
- **linked_core_monograph_slug:** `black_cohosh_actaea_racemosa_rhizome`  
- **primary_regulatory_monographs:**  
  - EU HMPC: *European Union herbal monograph on Cimicifuga racemosa rhizoma* (WEU + TU, menopausal symptoms).  
  - National monographs (e.g., Health Canada NHP, German Commission E) aligned around menopausal complaints.  
  - Pharmacopoeial standards: Ph. Eur./USP‑type monographs on black cohosh rhizome/root (identity & purity).  

---

### 2. Regulatory status & indication framing

**EU HMPC**  

- **Regulatory category:**  
  - **Well‑established use (WEU)** for certain standardised dry extracts with defined DER and solvents.  
  - **Traditional use (TU)** for other preparations with sufficient historic use but less robust data.  
- **WEU/TU indication (core concept):**  
  - **Relief of menopausal (climacteric) complaints**, particularly **hot flushes and excessive sweating**, in women where serious conditions have been excluded.  
- Not indicated for **vaginal bleeding of unknown cause**, and not a hormone replacement therapy; monographs emphasise symptom relief only.  

**Encoding suggestions**  

- `reg_status.eu`: `"WEU_for_specific_extracts; TU_for_other_preparations"`  
- `eu_indications_primary`:  
  - `"relief_of_menopausal_climacteric_complaints (e.g., hot_flushes_sweating)"`  
- Add constraints:  
  - `population`: `"adult_women_only"`  
  - `not_for`: `["pregnancy", "lactation", "children"]`  

---

### 3. Posology ranges (regulatory / monograph‑based)

> Black cohosh is almost always used as a **standardised extract**; posology is tightly tied to specific DER/solvent preparations. Only high‑level ranges are encoded here; **exact dosing must come from the product‑specific monograph**.

- **Typical HMPC‑aligned ranges (from WEU extracts and national monographs):**  
  - Standardised dry extracts used for menopausal symptoms are usually dosed in the approximate range of **tens of milligrams of extract per day** (e.g., around 40 mg/day for some isopropanolic extracts, often as 20 mg twice daily).  
- Duration of use is often limited in monographs (e.g., up to several months) with recommendation to seek medical evaluation if symptoms persist or worsen.

**Encoding suggestions**  

- `posology.adult.oral.standardised_extract_mg_per_day`: `"approx_40–60 (product_specific; confirm from SmPC)"`  
- `posology.duration_limit_months`: `"per_monograph (often ≤6 months without reevaluation)"`  

> In your KB you should **replace this approximate range with precise values for each extract** once you have parsed the underlying WEU monographs and product data.

---

### 4. Pharmacopoeial identity & purity tests (high‑level)

**Rhizome/root monographs (Ph. Eur./USP)** typically include:  

- **Identity:**  
  - Macroscopic identification of rhizome and roots; characteristic appearance and odour.  
  - Microscopic features (cortex, vascular structure) and TLC fingerprints for **triterpene glycosides** (e.g., actein, 27‑deoxyactein and related compounds).  
- **Purity:**  
  - Limits for foreign matter, loss on drying, total ash, acid‑insoluble ash.  
  - Limits for pesticide residues, heavy metals, and aflatoxins per general monographs.  
- **Assay:**  
  - Minimum content of total **triterpene glycosides** (expressed as a marker such as 27‑deoxyactein) and/or other defined markers, depending on the pharmacopoeia.  

**Encoding suggestions**  

- `qc.pharmacopeial_monographs`: `["Ph. Eur. Cimicifugae/Actaeae rhizoma", "USP Black Cohosh"]` (where present)  
- `qc.identity.primary_markers`: `["triterpene_glycosides_profile (e.g., actein, 27-deoxyactein)", "macroscopic_rhizome_features"]`  
- `qc.assay.requirement`: `"minimum_triterpene_glycoside_content_per_monograph"`  

---

### 5. GACP / GMP & safety‑critical notes

- **GACP:**  
  - Correct botanical identification is critical; confusion with other Actaea species must be avoided.  
- **Processing:**  
  - Controlled drying and storage to preserve triterpene glycosides; avoid mould and microbial contamination.  
- **GMP & safety:**  
  - Regulatory agencies have highlighted **rare cases of hepatotoxicity** associated with black cohosh products; labels often recommend stopping use and seeking medical help if symptoms of liver injury occur (e.g., jaundice, dark urine, abdominal pain).  
  - Manufacturers should implement **strict traceability**, avoid adulteration, and perform robust quality testing.  
  - Products should carry clear warnings for women with **existing liver disease** and for those taking potentially hepatotoxic medicines.  

In your agent, this layer should ensure that black cohosh is surfaced **only for menopausal symptom relief**, under clear restrictions (adult women only, not in pregnancy/lactation, attention to liver safety), and only when products meet triterpene‑glycoside and general QC standards.

---

## How to use this batch in your RAG / vector store

- Treat each herb section as a **regulatory overlay** on top of your existing clinical monograph.  
- Key fields to index as structured tags / embeddings:  
  - `reg_status.*`, `eu_indications_primary`, `escop_additional_uses`, `posology.*`, `qc.*`, `population_constraints`, `safety_critical_notes`.  
- When answering user questions, your agent can:  
  1. Pull **clinical/pharmacology** detail from your core monographs.  
  2. Overlay this **regulatory/QC layer** to:  
     - Gate which indications are labeled as “regulatory‑aligned”.  
     - Constrain dose suggestions to **monograph‑consistent windows**.  
     - Surface QC expectations (identity, purity, contaminants) automatically in professional‑facing answers.  


