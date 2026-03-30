# Case Development Methodology

This document explains the **why and what** of the case study development process: the research model, source quality standards, writing sequence, and verification requirements. For step-by-step instructions with your specific AI tool, see your quickstart:

- **Cowork** → [QUICKSTART-CLAUDE-COWORK.md](QUICKSTART-CLAUDE-COWORK.md)
- **Claude Code** → [QUICKSTART-CLAUDE-CODE.md](QUICKSTART-CLAUDE-CODE.md)
- **VS Code + Copilot** → [QUICKSTART-COPILOT.md](QUICKSTART-COPILOT.md)

---

## The Process Model

Case study development is **iterative**, not linear. You'll cycle between gathering sources and writing as gaps are discovered. This is called a **research loop** — and it's normal, not a sign something went wrong.

```
┌─────────────────────────────────────────────────────────┐
│                                                         │
│  SETUP → SOURCES → ASSESS → WRITE ──┬── VERIFY → PUBLISH
│                ↑                     │                  │
│                └─── RESEARCH LOOP ←──┘                  │
│                  (gap found during writing)              │
└─────────────────────────────────────────────────────────┘
```

---

## Phase 1: Setup

Before writing begins, you configure the case study by recording a few key details: the company name, industry, digital transformation initiative, protagonist, and course context. This information is written to `case-config.yaml`, which AI tools use throughout the project to maintain consistency.

Your AI tool guides you through a short Q&A to fill in this configuration. You won't need to edit `case-config.yaml` by hand.

---

## Phase 2: Source Collection

### What Goes Where

Add research materials to the `sources/` folder, organized by type:

| Subfolder              | What Goes Here                                              |
| ---------------------- | ----------------------------------------------------------- |
| `sources/transcripts/` | Interview transcripts, podcast notes, conference talk notes |
| `sources/financial/`   | SEC filings, earnings reports, investor presentations       |
| `sources/news/`        | News articles, press releases, media profiles               |
| `sources/reports/`     | Industry reports, analyst research, market data             |

### What Makes a Strong Source

Good case study sources share a few characteristics. Look for:

- A **named protagonist** who made interesting decisions under uncertainty
- **Direct quotes** from interviews, podcasts, or conference talks
- **Concrete numbers** — revenue, investment amounts, headcount, timeline
- **Multiple perspectives** — executive, industry analyst, customer
- **Strategic tension** with no obvious "right answer"

Sources that only describe what happened without explaining the decision context are weaker. Sources that put words in a protagonist's mouth (paraphrase without attribution) introduce verification risk.

**Using Perplexity**: Use Perplexity in your browser to find executive interviews, financial data, news coverage, and analyst reports. Copy relevant content or save files, then bring them into your `sources/` folder. Perplexity is a separate research tool — use it alongside your AI case-writing tool, not instead of it.

### Source Quality Tiers

Once registered, each source is assigned a quality tier:

| Tier | Type | Examples |
| ---- | ---- | -------- |
| **T1** | Primary / direct attribution | Interview transcripts, executive quotes, SEC filings, earnings calls |
| **T2** | Secondary / reported | News articles, analyst reports, business press profiles |
| **T3** | Background / tertiary | Wikipedia, encyclopedia entries, general overviews |

A strong case study package relies primarily on T1 and T2 sources. Heavy reliance on T3 sources is a quality risk.

### Go / No-Go Gate

Before moving to writing, your AI tool evaluates source depth, breadth, and reliability:

- **GREEN** — Ready to write
- **YELLOW** — Can proceed with caution; specific gaps identified
- **RED** — More sources needed before writing

A YELLOW rating means you can start writing but should expect to loop back for more sources. A RED rating means writing now will produce a case with too many unverifiable claims to pass verification later. Address RED before proceeding.

---

## Phase 3: Writing

### Document Sequence

Create the three required documents **in this order**. Each builds on the previous ones — do not skip ahead.

> **Note**: The full starter kit supports a fourth document (Teaching Note). This assignment requires only three: Additional Sources, Main Case, and Technical Supplement. You do not need to produce the Teaching Note.

| Order | Document             | Prerequisites                  | Length            |
| ----- | -------------------- | ------------------------------ | ----------------- |
| 1     | Additional Sources   | Sources collected and assessed | 3,000–5,000 words |
| 2     | Main Case            | Additional Sources complete    | 1,500–3,000 words |
| 3     | Technical Supplement | Main Case complete             | 500–1,500 words   |

### What Each Document Contains

**Additional Sources** compiles your raw research into a structured reference: a bibliography with source quality annotations, key excerpts, a timeline of significant events, and any exhibits (financial tables, org charts, data visualizations). It is not a narrative — it is the foundation the Main Case is built on.

**Main Case** is a protagonist-centered narrative presenting a strategic decision under uncertainty. It opens with a moment of tension or decision (not a company history), introduces the protagonist and context, presents the challenge, and closes with the protagonist facing a choice. It does not resolve the dilemma — the analysis is left to the student reader.

**Technical Supplement** provides the industry economics, competitive landscape, and technology concepts a reader needs to engage analytically with the case. It is reference material, not narrative. It includes a glossary for technical terms.

### Research Loops

During writing you will often discover gaps: a missing competitor's revenue figure, an unverifiable claim, a date you can't confirm. When this happens:

1. **Pause writing** at the current section
2. **Find the source** — use Perplexity, check your materials, or search online
3. **Add the source** to the appropriate subfolder and register it
4. **Resume writing** from where you left off

Budget **2–4 research loops per document**. This is expected, not a problem.

### Verification Gates Between Documents

Before moving from one document to the next, check that no claims in the completed document are unverifiable. Your AI tool will identify quotes or statistics that cannot be traced back to a named source. Either find a source that confirms the claim or remove it. Do not carry unverified claims forward into the next document.

### Keeping Your AI Usage Log Current

`ai-usage-log.md` is a required, graded deliverable. Update it throughout each session — not just at the end. Capture the prompts you used, what the AI generated, and any corrections you made. Your AI tool can maintain this log automatically if you prompt it to do so periodically.

---

## Phase 4: Targeted Edits

After completing all three documents, review them together for consistency and precision:

- **Cross-document consistency**: Do the same numbers appear everywhere — same revenue figure in Main Case and Technical Supplement?
- **Quote accuracy**: Are all quotes exact and properly attributed to a named source and date?
- **Financial accuracy**: Do stated percentages, growth rates, and totals match the underlying numbers?
- **Narrative accuracy**: Does the case story faithfully represent what sources actually say, or has the AI embellished?

This phase is about precision, not rewriting. Major structural changes at this point are a signal that verification gates earlier in the process were not used.

---

## Phase 5: Verification

Run a full quality check before submitting. **This step is a graded component** — the assignment explicitly evaluates what errors you caught and corrected. Every correction should be documented in `ai-usage-log.md`.

The verification suite checks:

| Check | What It Does |
| ----- | ------------ |
| Quote traceability | Every quote traced back to a dated, named source |
| Data point attribution | Every number attributed to a specific document |
| Cross-document consistency | Same figures used throughout all three documents |
| Financial arithmetic | Stated percentages and totals verified against underlying data |
| Narrative accuracy | Case story consistent with what sources actually report |
| Source balance | Multiple perspectives represented; no single-source narrative |
| URL validity | All links in source registry resolve |

For every flag raised, either find a source that confirms the claim or remove the claim. Document all corrections in `ai-usage-log.md`. Rerun checks after corrections until the suite is clean.

---

## Phase 6: Publication

### Add AI Methodology Disclaimer

Before exporting, your documents must include a brief statement disclosing that AI tools were used in research and writing. Your AI tool can add this automatically before export.

### Export to PDF

Export your Main Case to PDF format and save it to the `exports/` folder. The PDF is one of your submission deliverables.

### Make Repository Public

Your GitHub repository must be public for submission:

1. Go to your repository on [github.com](https://github.com/)
2. Click **Settings → scroll to Danger Zone → Change visibility → Make public**

### Submit to Canvas

Per the assignment instructions, submit:

1. Your **two-page report** (PDF) — include the link to your public GitHub repository in this document
2. **PDF export** of your Main Case document

---

## Writing Standards

These standards apply regardless of which AI tool you use. AI generates drafts; you are responsible for meeting them.

**Attribution**: Every quote must be traceable to a named person, source, and date. "According to the company" is not sufficient attribution.

**Fabrication risk**: AI tools can generate plausible-sounding statistics, quotes, and facts that do not exist in your sources. Every factual claim must be verifiable against a source in your `sources/` folder. If you cannot verify it, remove it.

**Protagonist authenticity**: The case protagonist must be a real person who made real decisions. Do not have AI invent a composite protagonist or fictionalize decisions.

**Narrative stance**: HBS-style cases present a dilemma — they do not advocate for a solution. If your Main Case recommends a course of action, revise it.

**Voice consistency**: The case should read as a single authored document, not as a sequence of AI responses. Revise for voice consistency after drafting.

> **Public Policy Cases**: If your case involves public policy or political leadership, tell your AI tool during setup (select "public policy") and reference `templates/HKS_PUBLIC_POLICY_GUIDANCE.md` for adapted frameworks.
