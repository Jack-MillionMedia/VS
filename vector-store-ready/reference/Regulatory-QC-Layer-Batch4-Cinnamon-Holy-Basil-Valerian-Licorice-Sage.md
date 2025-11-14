---
title: "Regulatory & Quality Control Layer — Batch 4 (Cinnamon, Holy Basil, Valerian, Licorice, Sage)"
category: "Regulatory & Quality Control"
tags: ["regulatory", "quality_control", "batch4", "cinnamon", "holy_basil", "valerian", "licorice", "sage"]
date: "2025-11-14"
source: "WHO monographs; EMA/HMPC; ESCOP; pharmacopoeias; project regulatory batch 4"
---

# Regulatory & Quality Control Layer — Batch 4  
*Cinnamon · Holy Basil · Valerian · Licorice · Sage*  

> **Scope.** This layer encodes only information that can be traced to WHO *Monographs on Selected Medicinal Plants*, EMA/HMPC EU herbal monographs, ESCOP/Commission E, and major pharmacopoeias (Ph. Eur., USP/USP–NF, USP Herbal Medicines Compendium, and aligned national monographs). Use it as a regulatory + QC overlay on top of your existing clinical monographs, not as a standalone prescribing guide.

---

## Shared WHO / Pharmacopoeial QC Baseline (applies to all herbs unless overridden)

- **Identity (macro/micro + chromatography)**  
  - Macroscopic & microscopic description of the crude drug (organoleptic characters, diagnostic tissues).  
  - Thin-layer chromatography (TLC) and, for some, HPLC for marker compounds (e.g., essential-oil fingerprints, glycosides, phenolic markers).  
  - Pharmacopoeial acceptance criteria for foreign organic matter (typically ≤1–5% depending on monograph) and absence of known toxic adulterants.  

- **Purity & contaminants**  
  - **Total ash, acid‑insoluble ash, extractives**: numeric limits given in WHO or pharmacopoeial monographs for each crude drug (used to detect exhaustion/adulteration).  
  - **Microbial limits (WHO herbal baseline)** for preparations intended for internal use:  
    - Aerobic bacteria ≤10⁵ CFU/g or ml; fungi ≤10⁴ CFU/g or ml; enterobacteria and certain Gram‑negative bacteria ≤10³ CFU/g or ml; *E. coli* absent in 1 g or 1 ml.  
  - **Pesticides & heavy metals:** aldrin + dieldrin ≤0.05 mg/kg (typical WHO default for crude drugs) and lead/cadmium not more than 10 and 0.3 mg/kg respectively in finished products, unless stricter national limits apply.  

- **GACP / GMP expectations (generic)**  
  - Cultivation/collection under GACP (botanical identity, voucher specimens, traceability, controlled use of agrochemicals).  
  - Post‑harvest handling to prevent microbial growth and mycotoxins (rapid drying, protected storage, validated shelf life).  
  - GMP manufacture with validated processes, specifications for each starting material, and release testing against pharmacopoeial monographs.

Use the herb‑specific sections below as **differential overlays**: only what is specific enough to matter for that herb is restated.

---

## 4.1 Cinnamon – *Cinnamomum verum* J. Presl, cortex  

### 4.1.1 Linkage metadata  

- `herb_key`: `cinnamon_cortex`
- `linked_core_monograph`: *Cinnamon – Clinical Monograph* (map to your file name/ID)
- `reg_quality_layer_version`: `1.0`  

---

### 4.1.2 Regulatory status & indication framing  

**Regulatory classification**  

- **WHO** – Included in *WHO Monographs on Selected Medicinal Plants* as *Cortex Cinnamomi* (covering *C. verum* and *C. cassia*).  
- **EMA/HMPC (EU)** – EU herbal monograph on *Cinnamomum verum J. Presl, cortex* as a **traditional herbal medicinal product (THMP)** for oral use.  
- **ESCOP / Commission E** – Describes cinnamon bark as a carminative and spasmolytic for flatulent dyspepsia and GI spasm (no well‑established use; traditional evidence only).  
- **USP / HMC / USP–NF** – Monographs exist for cinnamon bark and its preparations (e.g., cassia oil) specifying identity, assay for marker compounds, and impurity limits; use these as primary QC references for US‑marketed products (consult current USP/HMC text for exact tests and limits).  

**Indication categories**  

- **Traditional‑use (EU THMP)** – Symptomatic treatment of mild, spasmodic gastrointestinal complaints such as bloating and flatulence; generally for adults and older adolescents.  
- **WHO/ESCOP traditional profile** – Carminative for flatulent dyspepsia, sensation of fullness, and as a flavouring adjuvant to improve palatability of other agents.  
- **Well‑established use** – None recognized by EMA; all indications are traditional‑use.  

---

### 4.1.3 Posology ranges (regulatory‑anchored)  

*All doses refer to adults unless otherwise stated and come from EMA/ESCOP/WHO text; titrate actual products according to their standardized extract content.*  

- **Comminuted bark (herbal tea / decoction)**  
  - 1–4 g of comminuted cortex in ~150 ml boiling water, up to 3 times daily between meals for GI complaints (EMA & other monographs).  
- **Liquid / dry extracts**  
  - EU & national monographs allow preparations (tinctures, dry extracts) titrated to equivalent daily doses in the same range as the crude drug (roughly 2–4 g/day bark equivalent) for carminative use.  
- **Duration of use**  
  - Short‑term use for transient dyspeptic symptoms; if symptoms persist beyond ~2 weeks or worsen, EMA advises medical evaluation (general HMPC rule applied in cinnamon assessment).  

Children’s dosing and long‑term use should follow national monograph restrictions; EMA monograph focuses on adults.

---

### 4.1.4 Identity & purity tests (regulatory minimum)  

**Pharmacopoeial markers & ID**  

- **Botanical identity** – Dried inner bark of *Cinnamomum verum* (or specified *Cinnamomum* spp.), free from excessive outer cork; diagnostic cortex anatomy under microscopy as per WHO monograph.  
- **Chromatographic ID** – TLC or HPLC showing characteristic cinnamaldehyde and related phenylpropanoids (often via essential‑oil fraction fingerprint). EMA relies on Ph. Eur. cinnamon bark monograph for these ID tests.  

**Purity & assay examples**  

- **Foreign organic matter** – Typically ≤1–2% non‑bark material; WHO sets ≤2% for *C. verum* cortex.  
- **Ash & extractives (WHO)** –  
  - *C. verum* total ash not more than ~6%; acid‑insoluble ash not more than ~4%; values used to detect mineral adulteration.  
- **Microbiology & pesticides** – As per shared WHO baseline; Cortex Cinnamomi explicitly included with the generic limits cited above.  
- **Assay (where available)** – Some pharmacopoeias set minimum essential‑oil content and limits for cinnamaldehyde or related markers; USP and Ph. Eur. monographs should be used for numeric targets.  

---

### 4.1.5 GACP / GMP notes (cinnamon‑specific)  

- **Species & plant part control** – Clear differentiation between *C. verum* (“true” cinnamon) and *C. cassia*/*C. aromaticum* is required; monographs specify cortex thickness, colour and odour to avoid substitution/adulteration.  
- **Harvest & processing** – Young shoots harvested, outer bark removed, inner bark dried quickly in shade to preserve volatile constituents and avoid mould growth (WHO).  
- **Storage** – Protect from light, moisture and high temperature to preserve essential oil; monitor for insects and mould; use containers with low permeability to volatiles.  
- **Manufacturing** – For standardized extracts, validate extraction solvent, drug‑extract ratio, and marker assay (e.g., cinnamaldehyde content); set specification ranges anchored to Ph. Eur./USP limits.  

---

## 4.2 Holy Basil – *Ocimum sanctum* / *O. tenuiflorum*, leaf  

### 4.2.1 Linkage metadata  

- `herb_key`: `holy_basil_leaf`
- `linked_core_monograph`: *Holy Basil – Clinical Monograph*
- `reg_quality_layer_version`: `1.0`  

---

### 4.2.2 Regulatory status & indication framing  

**Regulatory classification**  

- **WHO** – Holy basil leaf is described in *WHO Monographs on Selected Medicinal Plants* under *Folium Ocimi Sancti* (traditional uses, basic identity and purity requirements).  
- **EMA/HMPC (EU)** – No current EU herbal monograph; not authorized as a THMP by EMA as of the latest searches (regulation is via national frameworks where applicable).  
- **ESCOP / Commission E** – No dedicated European monograph; use WHO and national monographs as the core reference.  
- **USP / HMC** – Holy basil is discussed in USP herbal references; a full HMC monograph is emerging but dosing/assay details should be taken from the most recent USP/HMC edition rather than inferred.  

**Indication categories** (tradition‑anchored, not EMA‑THMP)  

- **Traditional use (Ayurvedic & national monographs)** –  
  - As an adaptogen and “rasayana” for stress, supporting cognitive and physical performance.  
  - Adjuvant in management of colds, cough, and mild respiratory catarrh.  
  - Digestive support (mild dyspeptic complaints, appetite).  
- **Well‑established use** – None in EMA/ESCOP sense. All uses are traditional.  

In your KB, encode Holy Basil indications as **traditional** and clearly separate them from EMA‑defined THMP claims.

---

### 4.2.3 Posology ranges (regulatory‑anchored where available)  

Because EMA has no monograph, use **WHO and robust national monographs** (e.g., Health Canada NHP Holy Basil) to define regulatory‑style ranges:  

- **Dried leaf (oral)**  
  - Common national‑monograph adult range: ~2–3 g/day of dried leaf, divided, for stress and mild digestive complaints (typical Ayurvedic and NHP guidance).  
- **Fluid / dry extracts**  
  - Extracts standardized to key phenolic/terpenoid markers (e.g., eugenol, rosmarinic acid or total phenolics) with daily doses corresponding roughly to 2–3 g crude leaf equivalent; product‑specific validated ranges per dossier.  
- **Duration of use**  
  - Long‑term use (weeks to months) is common in traditional practice; however, national monographs typically recommend periodic clinical review (e.g., at 8–12 weeks) for products with modern health claims.  

Children’s dosing is jurisdiction‑specific; many regulators restrict Holy Basil products to adults/adolescents pending more safety data.

---

### 4.2.4 Identity & purity tests (regulatory minimum)  

- **Identity**  
  - Whole or cut dried leaves of *O. sanctum*/*O. tenuiflorum*; authenticated by macro/micro characters (leaf shape, glandular trichomes, stomatal pattern) and TLC essential‑oil profile.  
  - Distinguish from other *Ocimum* spp. (e.g., *O. basilicum*), often by TLC or GC fingerprint of eugenol and other essential‑oil components.  
- **Purity**  
  - Foreign matter limits (typically ≤2–5% per WHO/national monographs).  
  - Standard WHO pesticide, heavy‑metal and microbial limits as per shared baseline.  
  - For Holy Basil oil preparations, monographs and national standards may set minimum essential‑oil content and limits for specific constituents (e.g., eugenol); use the actual monograph values in your spec table.  

---

### 4.2.5 GACP / GMP notes (holy‑basil‑specific)  

- **Chemotype control** – Essential‑oil composition varies with chemotype (eugenol‑rich vs. methyl eugenol vs. other phenylpropanoids). Select cultivars with documented safety (e.g., limited methyl eugenol content) and lock them in via contracts and specifications.  
- **Cultivation** – Control agrochemical inputs; holy basil is often grown in smallholder systems where pesticide data may be sparse—GACP documentation and residue monitoring are critical.  
- **Post‑harvest** – Rapid drying at low temperature to preserve volatile and phenolic constituents; protect from sunlight and excessive heat to prevent oil loss and oxidation.  
- **Manufacturing** – For standardized extracts, specify marker ranges (e.g., total phenolics, eugenol, rosmarinic acid) and validate that every batch falls within established limits derived from clinical/traditional dossiers.  

---

## 4.3 Valerian – *Valeriana officinalis* L., radix  

### 4.3.1 Linkage metadata  

- `herb_key`: `valerian_root`
- `linked_core_monograph`: *Valerian – Clinical Monograph*
- `reg_quality_layer_version`: `1.0`  

---

### 4.3.2 Regulatory status & indication framing  

**Regulatory classification**  

- **WHO** – *Radix Valerianae* included in WHO monographs with indications for nervous tension and sleep disturbances and detailed quality tests.  
- **EMA/HMPC (EU)** – **European Union herbal monograph on *Valeriana officinalis* L., radix** with:  
  - **Well‑established use (WEU)**: certain dry extracts for relief of mild nervous tension and sleep disorders.  
  - **Traditional‑use (THMP)**: comminuted root and some extracts where WEU criteria are not met.  
- **ESCOP / Commission E** – Monographs recognize valerian root for nervous tension, restlessness and insomnia; provide similar indications to EMA and WHO.  
- **USP / HMC / USP–NF** – Monograph(s) for valerian root and extracts specify identity, minimum levels of sesquiterpenic acids (valerenic‑acid derivatives in some systems), and impurity limits; use USP for US‑market QC.  

**Indication categories**  

- **Well‑established use (EU WEU)** – Relief of mild nervous tension and sleep disorders using specified ethanol/water extracts with documented clinical data.  
- **Traditional‑use (EU THMP)** – Similar indications but for comminuted root and other extracts supported primarily by long‑standing use.  
- **WHO/ESCOP** – Nervous agitation, difficulty falling asleep, and functional GI complaints of nervous origin (e.g., “nervous stomach”).  

---

### 4.3.3 Posology ranges (regulatory‑anchored)  

*Ranges below are synthesized from EMA/ESCOP/WHO; always align specific products with their monograph category (WEU vs TU).*  

- **Dried root (comminuted, tea/decoction)**  
  - Typical adult single dose: ~2–3 g in 150 ml boiling water as infusion/decoction, 1–3 times daily, including 30–60 minutes before bedtime for sleep support (WHO/ESCOP).  
- **Dry extracts (WEU/THMP)**  
  - EMA WEU preparations: ethanol or ethanol–water dry extracts with daily doses in the approximate range of **400–900 mg** extract for insomnia, taken in 1 dose 30–60 minutes before bedtime (often with an additional earlier dose).  
  - For nervous tension, lower divided doses through the day are used (product‑specific, but typically equivalent to 2–3 g dried root daily).  
- **Duration of use**  
  - EMA generally allows use for up to 2–4 weeks before requiring medical reassessment if symptoms persist or worsen.  

Paediatric dosing and bath preparations (for some national monographs) are regulated separately and should not be inferred without consulting the specific monograph.

---

### 4.3.4 Identity & purity tests (regulatory minimum)  

- **Identity**  
  - Dried underground parts (rhizomes, roots, stolons) of *V. officinalis* with characteristic odour, macro/micro characters and TLC profile for valerenic acids and other sesquiterpenes (Ph. Eur., WHO).  
- **Purity**  
  - Foreign matter – usually ≤5% (e.g., stem bases and other extraneous material).  
  - Ash/extractives – WHO/Ph. Eur. set maxima for total ash and acid‑insoluble ash and minima for dilute ethanol‑soluble extractives to detect adulteration/exhaustion.  
  - Pesticides, heavy metals and microbiological quality – as per shared WHO baseline for internal preparations.  
- **Assay & markers**  
  - Some pharmacopoeias require TLC/HPLC for valerenic‑acid derivatives and/or valepotriates (even if not used as strict assay markers, they are used for identity and consistency).  
  - USP/Ph. Eur. monographs may specify minimum percentages or relative peak‑area limits for these compounds; these should be used as numeric targets in your QC spec sheet.  

---

### 4.3.5 GACP / GMP notes (valerian‑specific)  

- **Species & plant part** – Ensure use of *V. officinalis* L. (or defined subspecies) and correct underground parts; exclude aerial parts and other *Valeriana* spp. unless specifically permitted.  
- **Harvest timing** – Root harvested in autumn of the second or third year when valerenic‑acid content is highest; document harvest year and growth stage.  
- **Drying & storage** – Roots dried at controlled temperatures to prevent loss/degradation of volatile constituents; stored in odour‑tight containers away from light and moisture.  
- **Manufacturing** – Extraction and drying parameters validated to maintain consistent levels of sesquiterpenic acids; monitor for microbial contamination and aflatoxins, particularly in poorly dried raw material.  

---

## 4.4 Licorice – *Glycyrrhiza glabra* L. / *G. inflata* / *G. uralensis*, radix  

### 4.4.1 Linkage metadata  

- `herb_key`: `licorice_root`
- `linked_core_monograph`: *Licorice – Clinical Monograph*
- `reg_quality_layer_version`: `1.0`  

---

### 4.4.2 Regulatory status & indication framing  

**Regulatory classification**  

- **WHO** – *Radix Glycyrrhizae* (licorice root) monograph with indications for coughs, gastric irritation and as a flavouring/excipient, including detailed purity limits and microbiological criteria.  
- **EMA/HMPC (EU)** – **Community herbal monograph on *Glycyrrhiza glabra* L. and/or *G. inflata* and/or *G. uralensis*, radix** as a **traditional herbal medicinal product** for:  
  - relief of digestive symptoms including burning and dyspepsia;  
  - expectorant for cough associated with cold.  
- **ESCOP / Commission E** – Similar indications (demulcent for gastritis/ulcer‑like symptoms, catarrh of upper respiratory tract, cough).  
- **USP / HMC / USP–NF** – Monographs for licorice root and extracts specify minimum glycyrrhizic acid content and extractives, identity, limits on contaminants, and in some cases limits on glycyrrhizin exposure per dose.  

**Indication categories**  

- **Traditional‑use (EU THMP)** –  
  - **Indication 1:** Relief of digestive symptoms including burning sensation and dyspepsia.  
  - **Indication 2:** Expectorant in cough associated with cold.  
- **Well‑established use** – EMA treats licorice as traditional‑use; WEU category is not applied in the HMPC monograph.  
- **WHO/ESCOP** – Adds use as demulcent in inflammatory conditions of the upper GI tract (e.g., gastritis) and as adjunct in minor inflammations of the oral mucosa.  

---

### 4.4.3 Posology ranges (regulatory‑anchored)  

*Based primarily on EMA community monograph and WHO/national monographs.*  

- **Comminuted root (herbal tea/decoction)**  
  - **Digestive symptoms (Indication 1):**  
    - 1.5–2 g comminuted root in 150 ml boiling water as infusion or decoction, **2–4 times daily**, one cup after meals.  
  - **Expectorant (Indication 2):**  
    - 1.5 g comminuted root in 150 ml boiling water as infusion or decoction, **2 times daily**.  
- **Soft extracts (aqueous)**  
  - **Indication 1:** Soft extract (DER 1:0.4–0.5) – 32 mg, 2–3 times daily (not more than 160 mg/day of this extract).  
  - **Indication 2:** Soft extract (DER 3:1) – 1.2–1.5 g, 3–4 times daily.  
- **Duration of use (EMA)**  
  - Digestive symptoms: not more than **4 weeks** continuous use.  
  - Cough: if symptoms persist for more than 1 week during use, medical evaluation is required.  

In children and adolescents, EMA does **not** recommend use because of insufficient data; national monographs may have stricter limits or require deglycyrrhizinated formulations.

---

### 4.4.4 Identity & purity tests (regulatory minimum)  

- **Identity**  
  - Roots and stolons of *G. glabra*, *G. inflata* or *G. uralensis* with correct macro/micro features; TLC showing glycyrrhizin and characteristic flavonoids (e.g., liquiritin).  
- **Assay / markers**  
  - Pharmacopoeial licorice root typically must contain **not less than ~4.0% glycyrrhizic (glycyrrhizinic) acid** and ≥20% water‑soluble extractive.  
  - Extracts (e.g., Glycyrrhiza Extract in JP, USP) have higher minimum glycyrrhizic‑acid content (e.g., ≥4.5% in some monographs).  
- **Purity**  
  - Foreign matter limits (typically ≤5% other roots, stones, etc.).  
  - Microbial limits and pesticide/heavy‑metal limits as per WHO baseline.  
- **Exposure control**  
  - Safety evaluations (e.g., SCF/JECFA) highlight that **regular intake of glycyrrhizic acid above ~100 mg/day** can provoke pseudo‑hyperaldosteronism in susceptible adults; many regulators therefore restrict total glycyrrhizin exposure per day for OTC products.  

---

### 4.4.5 GACP / GMP notes (licorice‑specific)  

- **Species selection** – Document whether *G. glabra*, *G. inflata* or *G. uralensis* is used; maintain consistent species or defined mixtures, as glycyrrhizin and flavonoid profiles differ.  
- **Harvest & processing** – Roots typically harvested from 3–4‑year‑old plants to ensure adequate glycyrrhizin content; dried thoroughly to avoid mould.  
- **Assay‑driven process control** – Each batch of root and extract should be assayed for glycyrrhizic acid; set internal limits both for **minimum therapeutic content** (per pharmacopeia) and **maximum daily intake** (per safety guidance).  
- **Risk management** – Include strong label warnings for patients with hypertension, renal or cardiovascular disease and for concomitant use with diuretics, cardiac glycosides or corticosteroids, as specified by EMA.  

---

## 4.5 Sage – *Salvia officinalis* L., folium  

### 4.5.1 Linkage metadata  

- `herb_key`: `sage_leaf`
- `linked_core_monograph`: *Sage – Clinical Monograph*
- `reg_quality_layer_version`: `1.0`  

---

### 4.5.2 Regulatory status & indication framing  

**Regulatory classification**  

- **WHO / Commission E / ESCOP** – Sage leaf accepted for dyspeptic complaints, excessive sweating, and inflammations of the mouth and throat.  
- **EMA/HMPC (EU)** – **European Union herbal monograph on *Salvia officinalis* L., folium** as a **traditional herbal medicinal product**, with indications:  
  - mild dyspeptic complaints such as heartburn and bloating;  
  - excessive sweating;  
  - inflammations in the mouth or throat;  
  - minor skin inflammations (topical).  
- **USP / HMC / USP–NF** – Sage leaf/oil monographs set essential‑oil content and other quality parameters; use these for products targeting the US market.  

**Indication categories**  

- **Traditional‑use (EU THMP)** – As above; all EMA indications are traditional‑use based on long‑standing experience.  
- **Well‑established use** – None recognized by EMA; all use is traditional.  

---

### 4.5.3 Posology ranges (regulatory‑anchored)  

*Key adult ranges from EMA monograph; align to your dosage form.*  

- **Comminuted leaf (herbal tea)**  
  - **Oral (dyspepsia, sweating):** 1–2 g comminuted leaf in 150 ml boiling water, 2–3 times daily.  
- **Mouth/throat preparations**  
  - Gargle/mouthwash prepared from sage tea or extracts, usually several times daily, according to product‑specific instructions derived from the EMA/Commission E text.  
- **Topical use (minor skin inflammations)**  
  - Diluted preparations of sage extracts or essential oil‑containing products applied a few times daily to affected skin; EMA monograph provides ranges for ethanol extracts used cutaneously.  
- **Duration of use**  
  - Gastric complaints persisting >2 weeks, or oral/skin lesions not improving within ~1 week, require medical evaluation per EMA standard wording.  

Children’s dosing is limited or not recommended in several jurisdictions, especially for internal use, because of thujone‑containing essential oil. Check national monographs for age cut‑offs.

---

### 4.5.4 Identity & purity tests (regulatory minimum)  

- **Identity**  
  - Whole or cut leaves of *S. officinalis* with characteristic odour and taste; microscopically, diagnostic glandular hairs and leaf anatomy.  
  - TLC/GC of essential oil, with characteristic composition including thujone, cineole, camphor and related monoterpenes; EMA monograph points to Ph. Eur. *Salviae folium* standard.  
- **Assay / markers**  
  - Ph. Eur./Commission E require a **minimum essential‑oil content**, e.g., not less than about 12 ml/kg for whole drug and 10 ml/kg for cut drug.  
- **Purity**  
  - Limits for foreign matter, total ash and acid‑insoluble ash as per Ph. Eur./WHO.  
  - Microbial, pesticide and heavy‑metal limits as per shared WHO baseline.  
  - Some monographs set specific limits for thujone content in sage essential oil preparations because of neurotoxicity at high doses; align finished‑product specs to these regulatory limits.  

---

### 4.5.5 GACP / GMP notes (sage‑specific)  

- **Chemotype & thujone control** – Select cultivars and growing conditions resulting in acceptable thujone levels; quantify thujone in essential oil and finished products, and set internal limits aligned with EMA/Ph. Eur. safety guidance.  
- **Cultivation** – Avoid contamination with other *Salvia* species or aromatic shrubs; maintain clean seed/propagation material with documented identity.  
- **Drying & storage** – Dry gently (not overheated) to preserve essential oil content; store in well‑closed, light‑protected containers to prevent volatilization and oxidation of oil components.  
- **Manufacturing** – Validate extraction and concentration methods for essential‑oil‑containing preparations; monitor batch‑to‑batch essential‑oil content and composition, and apply appropriate safety margins for internal products, especially in populations at risk for seizures or pregnancy (where concentrated alcoholic extracts and pure essential oil are contraindicated).  

---

*End of Batch 4 – Cinnamon, Holy Basil, Valerian, Licorice, Sage*  


