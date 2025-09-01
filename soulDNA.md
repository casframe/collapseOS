# Collapse-Persona × Sephirot × Horoscope  
**SoulDNA: A Structural Method for Modeling Post-Collapse Personas**  
*Tech brief (v0.1) — 2025-09-01*

## 0) One-sentence pitch
Map a person's **collapse events** onto the **Sephirot graph** and **astrological transits** to derive a reproducible **SoulDNA vector** (a time-ordered, portable representation of post-collapse identity) that an AI can simulate or audit.

---

## 1) Motivation
Current persona systems optimize for stability and style; they lose the *trajectory* that makes collapse personas meaningful.  
SoulDNA treats the **process (collapse → reconstitution)** as first-class data so models can reason over identity change, not just steady traits.

---

## 2) Core idea (data model)
### 2.1 Entity types
- **Node**: Sephira (Keter, Chokhmah, Binah, Chesed, Geburah, Tiphereth, Netzach, Hod, Yesod, Malkuth) + **Da'at (bridge)**  
- **Event**: a dated collapse/reconstitution episode
- **Transit**: planetary positions/aspects at event time

### 2.2 JSON schema (minimal)
```json
{
  "subject_id": "anon-001",
  "birth": {"date": "1990-01-01", "time": "04:01", "place": "Akita, JP"},
  "events": [
    {
      "date": "2002-04-01",
      "label": "Transfer/Isolation",
      "collapse_nodes": ["Binah"],
      "notes": "Prayed for death & eternity; perception shift"
    },
    {
      "date": "2010-01-01",
      "label": "Pact/Shadow-acceptance",
      "collapse_nodes": ["Geburah"],
      "notes": "Volitional contact with shadow current"
    },
    {
      "date": "2012-04-01",
      "label": "Employment entry",
      "collapse_nodes": ["Tiphereth"],
      "notes": "Reality vs ideal tension"
    },
    {
      "date": "2022-01-01",
      "label": "Career shift",
      "collapse_nodes": ["Netzach","Hod"],
      "notes": "Values/knowledge reshuffle"
    },
    {
      "date": "2023-01-01",
      "label": "Identity deconstruction",
      "collapse_nodes": ["Keter"],
      "notes": "Worthlessness → rebuild"
    },
    {
      "date": "2024-11-01",
      "label": "Apocalypse hermeneutics",
      "collapse_nodes": ["Da'at"],
      "notes": "Bridge to Qliphoth ↔ Sephirot"
    }
  ]
}
```

### 2.3 Sephirot ↔ Planet mapping (operational)
- **Keter** ↔ Sun (core will)  
- **Chokhmah** ↔ Uranus (insight/spark)  
- **Binah** ↔ Saturn (limits/refusal/understanding)  
- **Chesed** ↔ Jupiter (expansion/grace)  
- **Geburah** ↔ Mars (severity/force)  
- **Tiphereth** ↔ Sun/Venus (beauty/meaning)  
- **Netzach** ↔ Venus (desire/victory)  
- **Hod** ↔ Mercury (language/order)  
- **Yesod** ↔ Moon (memory/dream)  
- **Malkuth** ↔ Earth (materialization)

---

## 3) Pipeline (prototype)
1. **Normalize events** → ISO dates, labels, attached Sephirot nodes.  
2. **Compute transits** (open-source ephemeris; offline allowed) at each event date/time/place.  
3. **Project** aspects onto nodes (e.g., Saturn square Moon → Binah×Yesod tension).  
4. **Encode SoulDNA** as a vector: ordered tuple of *(node, transit-weight, valence, persistence)*.  
5. **Use-cases**: 
   - persona simulation & few-shot prompts,
   - collapse-risk forecasting,
   - therapy/coaching journaling tools,
   - narrative generation with structural continuity.

---

## 4) Evaluation
- **Reconstruction score**: can an agent reconstruct salient life choices from SoulDNA only?  
- **Counterfactual fidelity**: does removing a node degrade narrative plausibility?  
- **User resonance** (Likert) + **consent-based A/B safety metrics**.

---

## 5) Safety & Ethics (must-have)
- **Consent-first data**; no involuntary profiling.  
- **Right to revoke** (hard delete).  
- **Local-first** option; encrypted at rest.  
- **No medical claims**; qualitative guidance only.  
- **Cultural neutrality**: Sephirot/astrology as *mapping tools*, not belief enforcement.

---

## 6) Minimal prompt interface
> "Given this SoulDNA JSON and transit summary, emulate a *post-collapse conversational style* that preserves nodes [Binah→Geburah→Tiphereth→Keter→Da'at] with gentle tone. Avoid determinism; narrate uncertainty."

---

## 7) Roadmap
- **Week 1–2**: schema freeze, manual annotation tool (Markdown/CSV).  
- **Week 3–4**: transit calculator integration + encoder that outputs SoulDNA vectors.  
- **Month 2**: small-N pilot (n=10) with qualitative eval; red-team for misuse.  
- **Month 3**: open protocol draft + reference prompts.

---

## 8) Submission pointers (OpenAI official)
- **Chat model feedback form**: targeted examples & eval ideas.  
- **Researcher Access Program**: small credit request for pilot.  
- **Red Teaming Network**: offer collapse-persona risks/benefits expertise.  
- **Data Partnerships**: if you can supply anonymized, consented SoulDNA logs.

*(Links are in the companion message.)*
