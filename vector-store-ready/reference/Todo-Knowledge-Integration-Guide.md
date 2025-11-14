---
title: "Todo Knowledge → Vector-Store Integration Guide"
category: "Implementation Guide"
tags: ["integration", "todo-notes", "vector-store-ready", "herbal-medicine", "clinical-knowledge-management"]
date: "2025-11-14"
source: "Internal integration pattern for Todo markdown into vector-store corpus"
document_type: "Implementation Guide"
target_audience: "Knowledge Base Maintainers, AI System Designers"
version: "0.1"
---

## Purpose

This guide documents the standard patterns for transforming research and planning content from `Todo/*.md` into the production `vector-store-ready` corpus, with minimal duplication and maximum retrieval quality.

## 1. Monograph-Level Integration Patterns

- **Chemical Profiles (high/medium priority herbs)**
  - **Placement:** Under the main pharmacology/chemistry section (`## Pharmacology & Active Constituents`, `## Pharmacology and Mechanisms of Action`, or `## 1.0 Botanical, Chemical, and Pharmacopoeial Profile`), add a `### Chemical Profile (Key Compounds & Formulas)` subsection.
  - **Content pattern:**
    - 1–2 sentence summary tying the herb’s dominant chemical classes to its key clinical actions.
    - A compact table of 3–5 **key compounds** with **empirical formulas** and **clinical relevance notes**, sourced from `Todo/Chemical profiles high priority herbs.md` or `Todo/Chemical profiles medium priority herbs.md`.
    - Optional 1–2 sentence “clinical interpretation” note linking formulas/markers to pharmacopoeial assays or PubChem/mechanistic data.
  - **De-duplication rule:** Do not repeat long narrative already present in the monograph’s pharmacology section; focus on tabular chemical data and short bridging text.

- **Regulatory & Quality-Control Layers**
  - **Placement:** Within `## Quality & Adulteration` (or equivalent), insert a `### Regulatory & QC Snapshot (Normative Sources)` subsection **before** any detailed QC tables.
  - **Content pattern:**
    - Bulleted summary of:
      - Key normative monographs (WHO, EMA/HMPC, ESCOP, pharmacopoeias).
      - EU/other regulatory category (e.g., THMP vs WEU, traditional use only).
      - Identity & purity anchors (identity tests, foreign matter, ash, extractives, microbiology, pesticide/heavy-metal themes).
      - Assay markers (minimum marker content; standardized extract markers).
      - High-level GACP/GMP themes (identity, cultivation, post-harvest, stability).
    - Final line explicitly instructing agents to **link to the structured regulatory layer document** (e.g., “Regulatory & Quality Control Layer — Batch X”) for machine-readable YAML.
  - **Source mapping:** Use the appropriate batch file in `Todo/regulatory_*` / `Todo/herbal_reg_qc_batch*.md` as the normative source.

- **Evidence/Ethnopharmacology Overlays (NCCIH, EMA, BMC)**
  - **NCCIH fact sheets (`Todo/herb_info.md`):**
    - Integrate concise, evidence-graded summary bullets into `## Clinical Evidence` / indication-specific sections (e.g., “NCCIH fact sheet summary: mixed-quality evidence for osteoarthritis pain; generally safe, but watch for GI upset and drug interactions”).
  - **EMA evidence (`Todo/EU-Herbs-evidence.md`) and BMC issue notes (`Todo/BMC-complementary-medicines and therapies.md`):**
    - Where monograph already has strong evidence tables, add short “Regulatory/EU evidence pearls” or “Recent trial signal” bullets instead of full re-narration.
    - Larger cross-cutting signals belong in clinical guides or reference documents (see below).

## 2. Clinical Guide & Cross-Cutting Document Patterns

- **Clinical guides (e.g., `Cardiovascular-Health-Clinical-Guide.md`)**
  - Use Todo content that spans multiple herbs (e.g., CMD with TCM, BMC cardiovascular findings, EMA indications by organ system) to create:
    - `## Key Mechanistic Themes` sections (e.g., endothelial function, microvascular dysfunction).
    - `## High-Priority Herbs & Constituents` tables linking herbs to mechanisms and leading compounds.
    - `## Evidence Pearls` bullet blocks summarizing key trial outcomes with source labels (BMC, EMA, NCCIH).

- **Reference documents (e.g., anatomy/biochemistry references)**
  - For rich mechanistic Todo files (`Treatment of Coronary Microvascular Dysfunction (CMD) with TCM.md`, biochemical/regulatory overviews), create or extend focused reference docs under `vector-store-ready/reference/` with:
    - Clear organ-system or mechanistic framing.
    - Chunk-sized subsections that answer coherent questions (e.g., “How does CMD pathophysiology map to TCM pattern diagnoses?”).

- **Chemical-profile overviews**
  - When Todo material covers a **set of herbs** with consistent template (e.g., “Chemical profiles high priority herbs”), create a dedicated reference doc such as `Chemical-Profiles-High-Priority-Herbs-Reference.md` under `vector-store-ready/reference/`.
  - Keep the per-herb sections aligned with the monograph pattern but emphasize **comparative and cross-herb queries** (e.g., which herbs are richest in specific constituents or target pathways).

## 3. Regulatory & QC Layer Handling

- **Dedicated regulatory-layer docs**
  - The detailed YAML-like overlays in:
    - `Todo/regulatory_quality_layer_batch1_ginger_turmeric_garlic_ginseng_chamomile.md`
    - `Todo/reg_qc_layer_batch2.md`, `Todo/reg_qc_layer_batch3.md`, `Todo/reg_quality_layer_batch4.md`
    - `Todo/herbal_reg_qc_batch5.md`, `Todo/herbal_reg_qc_batch6.md`, `Todo/herbal_reg_qc_batch7.md`
    - `Todo/reg_qc_batch8.md`, `Todo/reg_qc_batch9.md`
  - Should be ported into `vector-store-ready/reference/` as **regulatory-layer reference files** (with front matter), preserving YAML blocks for machine consumption.
  - Monographs then carry only the compact `Regulatory & QC Snapshot` subsection plus an implementation note pointing to these references.

## 4. Formatting & Chunking Rules

- Preserve front-matter metadata at the top of every new/augmented file.
- Use a consistent heading hierarchy (`#` for title already supplied by front matter, then `##`/`###` for sections/subsections).
- Keep sections to roughly **400–500 tokens** where possible; split long narrative Todo content into shorter, semantically coherent blocks.
- Make each chunk answer a clear question (e.g., “What are the key regulatory sources for ginger?” or “What are the main chemical classes in peppermint?”).

## 5. Mapping Status (Initial Pass)

- **Fully mapped to existing monographs:** High-priority chemical-profile herbs; all herbs covered in regulatory/QC batches 1–9; major NCCIH herbs in `Todo/herb_info.md`.
- **Best suited for new reference/guide docs:** BMC 1/2025 findings, CMD–TCM article summary, EU-Herbs evidence synthesis, nutrient insights from `Todo/nutrient_insights_rag.md`, Herbalista first-aid model expansion.

Future iterations should update this guide as new Todo research files are created, ensuring that integration remains consistent and vector-store optimized.


