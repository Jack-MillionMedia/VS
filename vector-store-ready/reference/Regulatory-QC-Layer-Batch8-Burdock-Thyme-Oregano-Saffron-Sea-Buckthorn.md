---
title: "Regulatory & Quality Control Layer — Batch 8 (Burdock Root, Thyme, Oregano, Saffron, Sea Buckthorn)"
category: "Regulatory & Quality Control"
tags: ["regulatory", "quality_control", "batch8", "burdock", "thyme", "oregano", "saffron", "sea_buckthorn"]
date: "2025-11-14"
source: "WHO monographs; EMA/HMPC; ESCOP; pharmacopoeias; project regulatory batch 8"
---

# Regulatory & Quality Control Layer — Batch 8  
*(Burdock Root, Thyme, Oregano, Saffron, Sea Buckthorn)*  

> NOTE  
> - This layer is designed to sit **on top of your existing clinical monographs**.  
> - Focus is on: indications (traditional vs well‑established), high‑level posology ranges, identity/purity tests, and GACP/GMP anchors.  
> - Where granular regulatory text or exact numeric dose ranges could not be confirmed with high confidence, the fields are left qualitative or flagged as “consult monograph” rather than guessed.  
> - Always defer to the **original WHO / EMA‑HMPC / ESCOP / USP / national pharmacopoeia** texts and current product SmPCs when building anything dose‑ or label‑critical.  

---

## 1. Burdock Root (Arctium lappa L.) — *Arctii radix*  

```yaml
regulatory_layer:
  herb_key: "burdock_root"
  link_to_core_monograph: "burdock_root_core"
  taxon:
    latin_binomial: "Arctium lappa L."
    drug_name: "Arctii radix"
    plant_part: "Dried roots"
  primary_regulatory_sources:
    who_selected_medicinal_plants:
      present: false
      note: "No dedicated WHO 'Selected Medicinal Plants' monograph for Arctii radix was confidently identified; check WHO indexes if needed."
    ema_hmpc:
      eu_herbal_monograph: true
      monograph_title: "Community herbal monograph on Arctii radix"
      regulatory_classification:
        registration_route: "Traditional herbal medicinal product (THMP)"
        well_established_use: false
    escop:
      monograph_available: true
      scope: "Traditional uses in dermatologic, urinary and digestive domains."
    usp_herbal_medicines_compendium:
      mapped_status: "not_mapped_in_this_layer"
      note: "HMC status not exhaustively checked; verify against current HMC index."
indications:
  well_established_use:
    status: "none_captured"
    note: "Burdock root is handled as a traditional-use herbal drug in HMPC; no well-established (WEU) indication is encoded here."
  traditional_use:
    - authority: "EMA/HMPC & ESCOP (THMP)"
      indication_id: "burdock_dermatologic"
      body_system: "Dermatologic"
      summary: >
        Traditional use as an adjunct for minor seborrhoeic skin conditions and other superficial skin eruptions.
      evidence_class: "traditional_use_only"
    - authority: "EMA/HMPC & ESCOP (THMP)"
      indication_id: "burdock_urinary"
      body_system: "Urinary"
      summary: >
        Traditional herbal medicinal product to support increased urine output and flushing of the urinary tract
        in minor urinary complaints.
      evidence_class: "traditional_use_only"
    - authority: "ESCOP / traditional European use"
      indication_id: "burdock_digestive_appetite"
      body_system: "Digestive"
      summary: >
        Bitter tonic in temporary loss of appetite and mild digestive disturbances.
      evidence_class: "traditional_use_only"
indication_meta:
  duration_limits:
    general_rule: "Short-term use only unless otherwise directed by a qualified clinician."
    urinary: "Up to 2 weeks; seek medical advice if symptoms persist or worsen."
    appetite_digestive: "Usually limited to 2 weeks; investigate underlying cause if persistent."
  paediatrics:
    status: "not_recommended_below_18_in_this_layer"
    note: "Paediatric use not encoded; defer to national HMPC implementation / SmPCs."
posology:
  adult_oral:
    native_drug_equivalent_g_per_day:
      qualitative_range: "low, multi-gram range (approx. 2–6 g/day), divided doses"
      note: >
        Exact numeric daily doses depend on national product monographs and should be taken directly from the
        HMPC/ESCOP documents or the specific product SmPC. This layer stores only a qualitative 'multi-gram' range.
    common_preparations:
      - "Comminuted root as infusion or decoction"
      - "Liquid extracts (ethanolic / hydroethanolic) standardized back to a defined g-equivalent of root"
    timing: "Traditionally taken before meals for appetite/digestive indications; with adequate fluids for urinary flushing."
  cutaneous_use:
    typical_forms:
      - "Decoction or aqueous preparations of Arctii radix for washes or compresses"
      - "Semi-solid preparations (creams/ointments) containing Arctii radix extracts"
    note: >
      Exact concentration ranges and application frequency are product-specific and should follow national monographs and SmPCs.
identity_and_purity_qc:
  crude_drug_definition: >
    Whole or cut, dried roots of Arctium lappa L. (and/or closely related Arctium spp. where permitted by the
    pharmacopoeia), complying with the relevant Arctii radix monograph.
  key_identity_tests:
    macroscopic:
      - "Brown to greyish-brown outer surface; internally whitish to yellowish, starchy fracture."
      - "Distinctive odour; taste slightly sweet then faintly bitter."
    microscopic:
      - "Cork with brownish walls and tangentially elongated cells."
      - "Parenchyma containing inulin inclusions."
      - "Occasional secretory canals and vascular bundles in radial arrangement."
    chromatographic:
      - "TLC fingerprint vs authenticated Arctii radix reference extract (phenolic / lignan pattern)."
  purity_limits_and_assays:
    - "Loss on drying / water content within pharmacopoeial limits."
    - "Total ash and acid-insoluble ash within limits."
    - "Extractable matter in ethanol and/or water as specified."
    - "Foreign matter below specified % w/w."
    - "Complies with general limits for heavy metals, pesticide residues, aflatoxins and microbiological quality."
gacp_gmp_anchors:
  cultivation_and_collection:
    - "Use authenticated Arctium lappa seed/propagating material; document source and voucher specimens."
    - "Prefer clean soils with low risk of heavy-metal contamination; avoid roadside and industrially impacted areas."
    - "Harvest roots from first-year plants (pre-flowering) when inulin content and root quality are optimal."
  post_harvest_and_storage:
    - "Wash, slice and dry roots promptly at controlled temperatures to prevent mould growth."
    - "Store dried root in well-closed containers protected from moisture and light; monitor for microbial load."
  manufacturing_controls:
    - "Full GMP for all extract manufacturing; carry identity testing at raw material intake and intermediate stages."
    - "Validate cleaning procedures to control cross-contamination with other Asteraceae drugs."
linking_notes:
  - "Use herb_key `burdock_root` to join this regulatory layer to the core Arctium lappa monograph."
  - "Indication IDs (e.g., `burdock_dermatologic`) can be used as stable tags in your retrieval layer."
```

---

## 2. Thyme (Thymus vulgaris / Thymus zygis; Thymi herba)  

```yaml
regulatory_layer:
  herb_key: "thyme_herb"
  link_to_core_monograph: "thyme_core"
  taxon:
    latin_binomials:
      - "Thymus vulgaris L."
      - "Thymus zygis L."
    drug_name: "Thymi herba / Herba Thymi"
    plant_part: "Dried flowering aerial parts"
  primary_regulatory_sources:
    who_selected_medicinal_plants:
      present: true
      note: "WHO monograph on Herba Thymi describes traditional uses and quality requirements."
    ema_hmpc:
      eu_herbal_monograph: true
      monograph_title: "Community herbal monograph on Thymus vulgaris L. and Thymus zygis L., herba"
      regulatory_classification:
        registration_route: "Traditional herbal medicinal product (THMP)"
        well_established_use: false
        note: "Indications are based on traditional use; evidence not sufficient for WEU classification."
    escop:
      monograph_available: true
      scope: "Respiratory and mild gastrointestinal indications."
    usp_herbal_medicines_compendium:
      mapped_status: "not_mapped_in_this_layer"
indications:
  well_established_use:
    status: "none_captured"
    note: "Plain thyme herb is handled as traditional-use; WEU status applies more to certain combinations (e.g. thyme + primula)."
  traditional_use:
    - authority: "EMA/HMPC (THMP)"
      indication_id: "thyme_cough_expectorant"
      body_system: "Respiratory"
      summary: >
        Expectorant in cough associated with colds and for symptomatic relief of mild bronchial catarrh.
      evidence_class: "traditional_use_only"
    - authority: "ESCOP / Commission E"
      indication_id: "thyme_gi_spasm"
      body_system: "Digestive"
      summary: >
        Symptomatic treatment of mild spasmodic complaints of the upper gastrointestinal tract, such as dyspepsia
        with bloating and flatulence.
      evidence_class: "traditional_use_only"
indication_meta:
  duration_limits:
    respiratory: "Use for acute, self-limiting upper respiratory infections; if symptoms persist >1 week, worsen or are accompanied by high fever, consult a physician."
    gi_spasm: "Short-term use during symptomatic episodes; persistent symptoms warrant medical evaluation."
  paediatrics:
    note: >
      Age restrictions vary by dosage form. Generally, thyme teas/syrups are not recommended under 4 years, and
      alcoholic preparations are avoided in young children. Always follow national monographs/SmPCs.
posology:
  adult_oral:
    herbal_tea:
      native_drug_g_per_cup: "approx. 1–2 g dried herb per 150 ml boiling water"
      cups_per_day: "3–4"
      comments: >
        Used warm as an expectorant infusion. This corresponds to a typical daily range of ~3–8 g dried herb.
    liquid_preparations:
      examples:
        - "Thyme herb fluid extract / tincture standardized back to a defined g-equivalent of herb."
      note: "Exact mg/ml and dose frequency must be taken from the specific national monograph or SmPC."
  inhalation:
    forms:
      - "Hot water inhalation with thyme herb or volatile oil, used for short-term symptom relief in colds."
    warning: "Risk of scalding; not recommended in small children."
  paediatric_dosing:
    status: "not numerically encoded in this layer"
    note: "Age- and product-specific; always follow HMPC monograph and SmPC for paediatric dosing."
identity_and_purity_qc:
  crude_drug_definition: >
    Whole or cut, dried flowering aerial parts of Thymus vulgaris L. and/or Thymus zygis L. (Lamiaceae),
    complying with official pharmacopoeial monographs (e.g., Ph. Eur. Thymi herba).
  key_identity_tests:
    macroscopic:
      - "Small leaves with rolled margins, grey-green above and whitish below; small, pink to purple flowers."
      - "Intense aromatic odour; strongly aromatic taste."
    microscopic:
      - "Characteristic glandular trichomes containing essential oil."
      - "Diacytic stomata on both leaf surfaces."
    chromatographic:
      - "TLC or HPTLC fingerprint of essential oil constituents (e.g., thymol, carvacrol, p-cymene) compared to reference."
  assay_and_limits:
    essential_oil_content:
      description: "Minimum essential oil content defined in pharmacopoeial monograph for Thymi herba."
      note: "Exact % v/w threshold (e.g. ≥ a defined %) should be sourced from the current pharmacopoeia."
    purity:
      - "Foreign matter, total ash and acid-insoluble ash within specified limits."
      - "Limits for pesticides, heavy metals, aflatoxins and microbial contamination per general monographs."
gacp_gmp_anchors:
  cultivation_and_harvest:
    - "Use documented chemotypes (e.g. thymol-, carvacrol-dominant) and keep them segregated; label chemotype if clinically relevant."
    - "Harvest flowering tops during early full bloom on dry days to maximize essential oil content."
  drying_and_storage:
    - "Low-temperature drying with good air circulation to prevent loss of volatile oil."
    - "Protect from light, oxygen and moisture; avoid long storage leading to oxidative degradation of essential oil."
  manufacturing_controls:
    - "Batch-to-batch standardisation of essential oil profile within a defined chemotype range."
    - "Control for potential adulteration with other Lamiaceae herbs (e.g. Origanum spp.) via DNA and/or chromatographic profiling."
linking_notes:
  - "Use `thyme_cough_expectorant` and `thyme_gi_spasm` as indication tags in your retrieval system."
  - "Ensure your core monograph’s pharmacology and clinical sections cross-reference these indication classes."
```

---

## 3. Oregano (Origanum vulgare L.) — *Herba Origani*  

```yaml
regulatory_layer:
  herb_key: "oregano"
  link_to_core_monograph: "oregano_core"
  taxon:
    latin_binomial: "Origanum vulgare L."
    drug_name: "Herba Origani / Origani herba"
    plant_part: "Dried aerial parts harvested during flowering"
  primary_regulatory_sources:
    who_monographs_nis:
      present: true
      monograph_title: "Herba Origani (WHO monographs on medicinal plants commonly used in the Newly Independent States)"
      note: "Provides definition, traditional uses and quality specifications."
    who_selected_medicinal_plants:
      present: false
      note: "Herba Origani is covered in the WHO NIS monograph set rather than the core 'Selected Medicinal Plants' volumes."
    ema_hmpc:
      eu_herbal_monograph: false
      note: "No dedicated HMPC monograph for Origanum vulgare herb; oregano is generally treated as a traditional herbal / food plant."
    escop:
      monograph_available: "not_confirmed_in_this_layer"
      note: "ESCOP/other European sources describe oregano as a carminative, expectorant and spasmolytic herb."
    usp_herbal_medicines_compendium:
      mapped_status: "not_mapped_in_this_layer"
indications:
  well_established_use:
    status: "none_captured"
    note: "WHO NIS monograph describes only traditional uses; no WEU-type indication encoded."
  traditional_use:
    - authority: "WHO NIS Herba Origani monograph"
      indication_id: "oregano_cough_cold"
      body_system: "Respiratory"
      summary: >
        Used to treat cough, colds and bronchial catarrh, functioning as an expectorant and diaphoretic.
      evidence_class: "traditional_use_only"
    - authority: "WHO NIS Herba Origani monograph / traditional European practice"
      indication_id: "oregano_dyspepsia_bile"
      body_system: "Digestive"
      summary: >
        Used in bloating and dyspeptic discomfort; traditionally taken to stimulate bile secretion, appetite and digestion.
      evidence_class: "traditional_use_only"
    - authority: "WHO NIS Herba Origani monograph"
      indication_id: "oregano_sedative_antispasmodic"
      body_system: "Nervous / Digestive"
      summary: >
        Employed as a mild sedative and antispasmodic agent for nervous tension and associated GI spasm.
      evidence_class: "traditional_use_only"
    - authority: "Unani / traditional systems quoted in WHO NIS"
      indication_id: "oregano_emmenagogue"
      body_system: "Reproductive"
      summary: >
        Traditional use as an emmenagogue in certain systems of medicine, including for algomenorrhoea;
        not to be used during pregnancy.
      evidence_class: "traditional_use_only"
indication_meta:
  cautions:
    pregnancy: "Avoid internal medicinal doses because of reported emmenagogue activity."
    duration: "Short-term symptomatic use only; chronic respiratory or GI symptoms require medical evaluation."
posology:
  adult_oral:
    herbal_tea:
      qualitative_range_native_drug_g_per_day: "low multi-gram range (e.g. ~2–4 g/day), divided in 2–3 infusions"
      note: >
        Traditional preparations commonly mirror other carminative Lamiaceae (1–2 g herb per cup, several times daily),
        but exact posology should follow national pharmacopoeias or product SmPCs.
    liquid_preparations:
      note: "Essential-oil preparations (e.g. oregano oil) are not encoded in this layer; safety margins are narrow."
  paediatrics:
    status: "not_encoded"
    note: "No paediatric dosing defined; oregano is primarily treated as a culinary herb in children."
identity_and_purity_qc:
  crude_drug_definition: >
    Whole or cut, dried aerial parts of Origanum vulgare L. (Lamiaceae), collected during the flowering phase,
    meeting the definition in the WHO Herba Origani monograph and relevant pharmacopoeias.
  key_identity_tests:
    macroscopic:
      - "Leaves opposite, ovate, grey-green, with characteristic oregano odour."
      - "Flowers in terminal corymbs or panicles; purplish bracts."
    microscopic:
      - "Glandular trichomes containing essential oil on leaf and calyx surfaces."
    chromatographic:
      - "TLC essential-oil profile with carvacrol, thymol and related phenolics, compared to reference."
  purity:
    - "Foreign matter limits as specified in monograph (e.g., stems above a certain diameter)."
    - "Moisture, ash values within pharmacopoeial ranges."
    - "Control for adulteration with other Origanum species or unrelated aromatic herbs via macro-, micro- and chromatographic tests."
gacp_gmp_anchors:
  cultivation_and_collection:
    - "Maintain clear separation of Origanum vulgare from other Origanum taxa and chemotypes; misidentification is common."
    - "Harvest during full flowering to optimise essential oil yield and consistency."
  drying_and_storage:
    - "Dry quickly in thin layers with good ventilation; avoid direct sunlight to protect colour and volatile oil."
    - "Store in airtight containers, protected from light, at low humidity."
  manufacturing_controls:
    - "Implement identity checks for bulk oregano lots, especially when sourcing as a commodity spice (adulteration risk)."
    - "Monitor essential-oil content and profile for batch consistency where oregano is used as a medicinal drug rather than just as a spice."
linking_notes:
  - "Use indication tags (e.g., `oregano_cough_cold`, `oregano_dyspepsia_bile`) to keep respiratory vs GI traditional uses clearly separated in your agent."
  - "Flag pregnancy as a hard contraindication at the reasoning layer when emmenagogue properties are relevant."
```

---

## 4. Saffron (Crocus sativus L.) — *Stigma Croci*  

```yaml
regulatory_layer:
  herb_key: "saffron"
  link_to_core_monograph: "saffron_core"
  taxon:
    latin_binomial: "Crocus sativus L."
    drug_name: "Stigma Croci"
    plant_part: "Dried stigmas"
  primary_regulatory_sources:
    who_selected_medicinal_plants:
      present: true
      monograph_title: "Stigma Croci (WHO monographs on selected medicinal plants, Vol. 3)"
    ema_hmpc:
      eu_herbal_monograph: false
      note: "No HMPC herbal monograph; saffron is mainly regulated as a food/colouring and in specific national contexts."
    escop:
      monograph_available: "not_confirmed_in_this_layer"
    usp_herbal_medicines_compendium:
      mapped_status: "colour_additive / food context"
      note: "Saffron is primarily handled as a colour additive in US regulation."
indications:
  well_established_use:
    status: "none_captured"
    note: >
      The WHO monograph summarises traditional medicinal uses but does not translate them into an
      EMA-style well-established indication; saffron is not a standardised herbal medicinal product in most jurisdictions.
  traditional_use:
    - authority: "WHO Stigma Croci monograph & broader traditional literature"
      indication_id: "saffron_trad_menstrual"
      body_system: "Reproductive"
      summary: >
        Traditional use as an emmenagogue and for menstrual irregularities and dysmenorrhoea; not recommended in pregnancy.
      evidence_class: "traditional_use_only"
    - authority: "Traditional Mediterranean / Middle Eastern medicine"
      indication_id: "saffron_trad_digestive"
      body_system: "Digestive"
      summary: >
        Used in small doses as a stomachic and digestive aid, including for mild abdominal pains and dyspepsia.
      evidence_class: "traditional_use_only"
    - authority: "Persian / Greco-Arab medicine & later literature"
      indication_id: "saffron_trad_mood"
      body_system: "Nervous / Mental health"
      summary: >
        Traditional use as a tonic and for mood support (sadness, nervous tension); modern trials investigate these uses but are not encoded as regulatory indications here.
      evidence_class: "traditional_use_only"
indication_meta:
  regulatory_position:
    note: >
      Many modern 'saffron extract' products position these uses as dietary supplements; they are not generally authorised
      herbal medicinal product indications. Treat any medicinal claim as off-label unless backed by a specific national authorisation.
  duration_and_scope:
    - "Short-term use only in low doses for traditional indications."
    - "High-dose or long-term use should be supervised in research or specialist settings."
posology:
  food_vs_medicinal:
    culinary_use:
      note: "Culinary doses (pinch-level, tens of milligrams) are generally recognised as safe for the general population."
    medicinal_use:
      note: >
        The WHO monograph and later sources discuss dose ranges in the hundreds of milligrams per day, but given the
        narrow margin between therapeutic and adverse doses, this layer does NOT encode numeric posology. Always consult
        up-to-date monographs and product SmPCs when dosing saffron clinically.
  overdose_toxicity:
    warning: >
      High-dose saffron has been associated with uterine stimulation, possible abortifacient effects and other toxicities.
      Avoid building any automated dose suggestions for saffron based solely on this knowledge base.
identity_and_purity_qc:
  crude_drug_definition: "Dried stigmas of Crocus sativus L. (Iridaceae) complying with the WHO and pharmacopoeial monographs."
  key_identity_tests:
    macroscopic:
      - "Dark orange-red, trumpet-shaped stigmas with flared ends; absence of other floral parts."
    microscopic:
      - "Characteristic papillose epidermal cells and pigment distribution along stigma."
    chromatographic:
      - "HPLC or spectrophotometric assessment of crocin, picrocrocin and safranal profile."
  quality_markers:
    - "Colouring strength defined by absorbance at specified wavelengths (e.g. E1% 1cm values for crocin)."
    - "Limits for extraneous matter (styles, foreign plant parts, synthetic dyes)."
    - "Tests for authenticity vs common adulterants (e.g., turmeric, safflower, marigold, synthetic dyes)."
safety_and_contraindications:
  pregnancy:
    status: "contraindicated"
    rationale: "Stigma Croci may induce uterine contractions; high doses linked to abortifacient effects."
  bleeding_disorders:
    status: "contraindicated"
    rationale: "Saffron inhibits platelet aggregation; avoid in bleeding disorders or with anticoagulant/antiplatelet drugs."
  children_and_lactation:
    status: "limit_to_food_use"
    rationale: "Insufficient safety data; WHO restricts use to normal dietary amounts."
gacp_gmp_anchors:
  cultivation_and_harvest:
    - "Harvest stigmas manually at appropriate flowering stage; rapid drying is critical to preserve quality."
    - "Maintain strict traceability to avoid admixture with non-medicinal Crocus species."
  processing_and_storage:
    - "Dry at controlled temperatures to stabilise crocin and related constituents."
    - "Protect from light and moisture to prevent loss of colour and aroma."
  manufacturing_controls:
    - "Develop strong anti-adulteration programme (macro/micro analysis, HPLC fingerprints, and where needed DNA methods)."
    - "Implement potency and identity checks on every batch of saffron raw material and extract."
linking_notes:
  - "Treat saffron primarily as a 'high-alert' ingredient: the regulatory layer should bias your agents toward safety warnings rather than dose suggestions."
  - "Indication tags (`saffron_trad_menstrual`, `saffron_trad_mood`, etc.) should be treated as low-confidence, research/traditional context only."
```

---

## 5. Sea Buckthorn (Hippophae rhamnoides L.) — Sea buckthorn fruit/leaf  

```yaml
regulatory_layer:
  herb_key: "sea_buckthorn"
  link_to_core_monograph: "sea_buckthorn_core"
  taxon:
    latin_binomial: "Hippophae rhamnoides L."
    drug_names:
      - "Hippophae fructus (Sea buckthorn berry)"
      - "Hippophae folium (Sea buckthorn leaf)"
    plant_parts: "Fruits and leaves (most commonly), sometimes seed oil or pulp oil"
  primary_regulatory_sources:
    who_selected_medicinal_plants:
      present: true
      note: "WHO monographs on selected medicinal plants include Hippophae rhamnoides, with emphasis on quality and traditional uses."
    ema_hmpc:
      eu_herbal_assessment_report: true
      note: "HMPC assessment work has focused on Hippophae rhamnoides fruits; no widely used EU herbal monograph/indication is encoded here."
    escop:
      monograph_available: "not_confirmed_in_this_layer"
    usp_herbal_medicines_compendium:
      mapped_status: "not_mapped_in_this_layer"
indications:
  well_established_use:
    status: "none_captured"
    note: >
      Sea buckthorn is widely used as a nutritional and cosmetic ingredient; medicinal claims are typically formulated
      as food supplement functions rather than authorised herbal medicinal indications.
  traditional_use:
    - authority: "Traditional Tibetan / Chinese / Eurasian medicine (as summarised in secondary sources)"
      indication_id: "seabuckthorn_cough_phlegm"
      body_system: "Respiratory"
      summary: "Traditional use for cough with abundant phlegm and as a mild bronchodilator-type remedy."
      evidence_class: "traditional_use_only"
    - authority: "Traditional Eurasian medicine"
      indication_id: "seabuckthorn_digestive"
      body_system: "Digestive"
      summary: "Support for digestion, abdominal discomfort, and ulcers; typically via berry or berry oil preparations."
      evidence_class: "traditional_use_only"
    - authority: "Topical / mucosal traditional use"
      indication_id: "seabuckthorn_skin_mucosa"
      body_system: "Dermatologic / Mucosal"
      summary: "Topical use of oils for burns, wound healing, dry or irritated skin and mucous membranes."
      evidence_class: "traditional_use_only"
indication_meta:
  regulatory_position:
    - "In many jurisdictions sea buckthorn is primarily regulated as a food, nutraceutical or cosmetic ingredient."
    - "Any medicinal positioning requires scrutiny against local regulations and available clinical data."
posology:
  general_comment: >
    Dose ranges vary widely between fruit juice, seed oil, pulp oil, leaf tea and standardized extracts. Given this
    heterogeneity and the primarily food-level regulatory status, this layer does not encode numeric posology.
  implementation_note: >
    When building agents, treat sea buckthorn primarily as a supportive nutritional plant; defer all dosing to
    specific product labels or clinical trial protocols.
identity_and_purity_qc:
  crude_drug_definition: >
    Fruits (berries), leaves or expressed oils from Hippophae rhamnoides L., meeting the identity and purity
    criteria set out in WHO and relevant national monographs.
  key_identity_tests:
    fruits_and_juice:
      - "Morphology and colour of berries; seeds and pulp characteristics."
      - "Chromatographic fingerprints for key carotenoids (e.g., beta-carotene), tocopherols and other lipophilic markers."
    oils:
      - "Fatty acid profile (e.g., palmitoleic acid content for pulp oil; linoleic/alpha-linolenic ratios for seed oil)."
      - "Peroxide value, acid value and other rancidity indicators."
  purity:
    - "Pesticide residues, heavy metals and mycotoxins within general monograph limits."
    - "Microbiological quality appropriate to oral juice/oil products."
gacp_gmp_anchors:
  cultivation_and_harvest:
    - "Document subspecies and provenance; phytochemical profiles differ significantly between ecotypes."
    - "Harvest berries at defined ripeness for optimal carotenoid and vitamin content."
  processing:
    - "Minimise oxidation of oils and carotenoids via rapid processing and protection from air/light."
    - "Clarify juices properly to reduce microbial risk while preserving key nutrients."
  manufacturing_controls:
    - "Standardise preparations (juices, oils, extracts) to one or more marker compounds where a therapeutic narrative is claimed."
    - "Clearly distinguish between fruit and seed oil on labels; their fatty acid and bioactive profiles differ."
linking_notes:
  - "Treat sea buckthorn as 'nutritional support with traditional medicinal narratives', not as a first-line herbal medicine in your reasoning layer."
  - "Indication tags (`seabuckthorn_cough_phlegm`, `seabuckthorn_skin_mucosa`, etc.) are useful for clustering evidence but should not by themselves drive treatment recommendations."
```

---

### Integration Notes for Batch 8

- Each `herb_key` (e.g., `burdock_root`, `thyme_herb`, `oregano`, `saffron`, `sea_buckthorn`) should match or be mapped to the IDs you use in your **core monograph markdowns**.  
- The `indication_id` fields are deliberately short, stable strings you can:
  - expose as **retrieval tags** in your vector store, and  
  - reference in RAG prompts when constraining an agent to “regulatory-aligned indications only”.  
- Where this batch intentionally avoids numeric posology (especially for **saffron and sea buckthorn**), that is by design to prevent unsafe “hallucinated doses” in a safety‑critical zone.  
- If you later want a **dose-aware layer**, you should build a separate, tightly curated table sourced directly from SmPCs / original monographs and keep it logically distinct from this higher-level regulatory map.


