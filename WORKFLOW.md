# Case Development Workflow

> **REVISED — March 2026**: This document now lists **Claude Cowork prompts first** in each phase — Cowork is the recommended path for this assignment. Claude Code and VS Code + Copilot instructions follow in each section for students on those paths.

This document explains the end-to-end workflow for creating a case study using this template. For Cowork users, the full step-by-step setup guide is in [QUICKSTART-CLAUDE-COWORK.md](QUICKSTART-CLAUDE-COWORK.md).

---

## The Process Model

Case study development is **iterative**, not linear. You'll cycle between gathering sources and writing as gaps are discovered. This is called a **research loop** — and it's normal.

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

Create your repository and configure the case study.

### Create Repository

1. Click **"Use this template"** on the template repository
2. Name it `[company]-case-study` and set to **Private**
3. Clone to your computer — Cowork and Chat tool users use **GitHub Desktop**; Claude Code and VS Code users clone via terminal (see README.md)

### Configure

**Cowork users** — in the Cowork chat, say:
> *"Please run setup-case."*

Claude reads the setup skill and walks you through a short Q&A covering company name, industry, DT initiative, protagonist, and course context. It writes the configuration to `case-config.yaml` automatically.

**At the start of your very first session**, also say:
> *"Please read README.md and CLAUDE.md so you understand the project structure and your role. Then help me get started."*

**Claude Code users** — run the setup skill:
```
/setup-case
```

**VS Code + Copilot users** — open the Copilot chat panel (Agent Mode) and say:
> *"Help me configure my case study"*

Copilot reads `.github/copilot-instructions.md` and walks you through the same setup process.

**Chat tool users** — the starter prompt asks you about your case when you begin.

**Manual** — edit `case-config.yaml` with your case details.

### Git Checkpoint

**Cowork users** — open GitHub Desktop, write a commit message (e.g., *"Configure case study for [Company]"*), click **Commit to main**, then **Push origin**.

**Claude Code / VS Code terminal:**
```bash
git add -A && git commit -m "Configure case study for [Company]" && git push
```

---

## Phase 2: Source Collection

Add research materials to the `sources/` folder:

| Subfolder | What Goes Here |
|-----------|---------------|
| `sources/transcripts/` | Interview transcripts, podcast notes, conference talk notes |
| `sources/financial/` | SEC filings, earnings reports, investor presentations |
| `sources/news/` | News articles, press releases, media profiles |
| `sources/reports/` | Industry reports, analyst research, market data |

**What makes good source material:**
- A named protagonist who made interesting decisions under uncertainty
- Direct quotes from interviews, podcasts, or conference talks
- Concrete numbers (revenue, investment, headcount, timeline)
- Multiple perspectives (executive, industry, customer)
- Strategic tension with no obvious "right answer"

**Using Perplexity for research**: Use Perplexity (in your browser, separately from Cowork) to find executive interviews, financial data, news coverage, and analyst reports. Copy relevant content or save files, then bring them into your `sources/` folder.

### Register Sources

**Cowork users** — drag source files (PDFs, Word docs, text files) into the Cowork chat window and say:
> *"Please save copies of these files to the appropriate subfolder inside sources/ — transcripts go in sources/transcripts/, financial documents in sources/financial/, news articles in sources/news/, and industry reports in sources/reports/."*

Or copy files directly using File Explorer (Windows) or Finder (Mac), then say:
> *"Please scan the sources/ folder and register any new files in the Source Registry."*

**Claude Code users:**
```
/add-sources
```
This scans for new files, asks metadata, assigns quality tiers (T1/T2/T3), and updates the Source Registry.

**VS Code + Copilot users:** Say *"Scan the sources folder and register any new files"* in Agent Mode.

**Chat tool users:** Upload or paste your source materials into the chat.

See `templates/SOURCE_ACQUISITION.md` for detailed guidance on finding and transcribing sources.

### Assess Source Quality

**Cowork users:**
> *"Please assess my source quality and tell me whether I have enough to start writing, and what gaps I should fill first."*

**Claude Code users:**
```
/assess-sources
```

**VS Code + Copilot users:** Say *"Evaluate my source quality and give me a go/no-go assessment"*.

This evaluates depth, breadth, reliability, and completeness with a **go/no-go gate**:
- **GREEN**: Ready to write
- **YELLOW**: Can proceed with caution
- **RED**: Need more sources first

### Git Checkpoint

**Cowork users** — open GitHub Desktop → commit → push. Recommended message: *"Add source materials"*.

**Claude Code / VS Code terminal:**
```bash
git add -A && git commit -m "Add source materials" && git push
```

---

## Phase 3: Writing

Create the three required documents **in order**. Each document builds on the previous ones.

> **Note**: The full starter kit supports four documents (including a Teaching Note). This assignment requires three: Additional Sources, Main Case, and Technical Supplement. You do not need to produce the Teaching Note.

| Order | Document | Prerequisites |
|-------|----------|--------------|
| 1 | Additional Sources | Sources collected and assessed |
| 2 | Main Case | Additional Sources complete |
| 3 | Technical Supplement | Main Case complete |

### Writing Each Document

**Cowork users** — use these prompts for each document:

**Additional Sources** (compiles raw research into a structured reference):
> *"Please help me write the Additional Sources document. Start by reviewing what's in sources/ and then compile the key material into a structured bibliography with excerpts and a timeline of significant events."*

**Main Case** (1,500–3,000 words — protagonist-centered narrative):
> *"Please help me write the Main Case. Before you start, offer me 2–3 options for the opening scene — I want a moment of decision or tension, not a company history summary. Then write section by section, pausing after each section for my feedback before continuing."*

**Technical Supplement** (500–1,500 words — industry context and frameworks):
> *"Please help me write the Technical Supplement. Cover the industry economics, competitive landscape, and key technology concepts relevant to [Company]'s initiative."*

**Claude Code users** — the writing skill handles prerequisites and sequencing:
```
/write-document
```

**VS Code + Copilot users** — say *"Help me write the next document in my case study"* in Agent Mode.

The writing process will:
- Check prerequisites are met
- Determine the next document to write
- Ask document-specific setup questions
- Write section by section, pausing for your feedback
- Check attribution and flag unverified claims
- Save to `case-study/` when complete

**Chat tool users** — use the prompts in `templates/PROMPTS.md` to guide writing.

### Research Loops

During writing, you'll often discover gaps: a missing competitor's revenue, an unverifiable claim, a date you can't confirm. When this happens:

1. **Pause writing** at the current section
2. **Find the source** — use Perplexity, check your materials, or search online
3. **Add the source** to the appropriate subfolder and register it
4. **Resume writing** from where you left off

This is expected behavior, not a problem. Budget 2–4 research loops per document.

### Keeping Your Log Current

**Cowork users** — remind Claude periodically to update your running log:
> *"Please update ai-usage-log.md with what we've done so far in this session."*

### Verification Gates

Between documents, check attribution and consistency before continuing:

**Cowork users:**
> *"Before we move on, please do a quick check — are there any claims or quotes in what we just wrote that you can't trace back to a specific source? Flag anything uncertain."*

**Claude Code users** — the skill automatically runs a quick consistency check between documents and reports current verification debt.

### Git Checkpoint (after each document)

**Cowork users** — open GitHub Desktop → commit → push. Recommended message: *"Complete [Document Name] draft"*.

**Claude Code / VS Code terminal:**
```bash
git add -A && git commit -m "Complete [Document Name] draft" && git push
```

---

## Phase 4: Targeted Edits

After completing all three documents, review and refine:

1. **Cross-document consistency**: Do the same numbers appear everywhere?
2. **Quote accuracy**: Are all quotes exact and properly attributed?
3. **Financial accuracy**: Do percentages match the underlying numbers?
4. **Narrative accuracy**: Does the case story match what sources actually say?

**Cowork users:**
> *"Please review my three documents for consistency — check that the same figures are used throughout, that all quotes are properly attributed, and flag anything that looks inconsistent between documents."*

This phase is about precision, not rewriting.

---

## Phase 5: Verification

Run quality checks before submitting. **This step is a graded component** — the assignment explicitly evaluates what errors you caught and corrected. Every correction should be documented in your `ai-usage-log.md`.

**Cowork users:**
> *"Please run all quality checks on my case study. Check every factual claim against the sources in sources/, flag any quotes or statistics you cannot trace back to a named source, and identify anything that may be AI-generated rather than sourced."*

Claude will check:
- Quote traceability — every quote back to a dated source
- Data point attribution — every number to a named document
- Cross-document consistency — same figures used throughout
- Narrative accuracy — does the story match what sources actually say?

For every flag Claude raises, either find a source that confirms it or remove the claim. Then:
> *"Please update ai-usage-log.md with all the verification issues found and the corrections I made."*

**Claude Code users** — run the comprehensive check:
```
/verify-all
```

This runs all checks in sequence:
- `/verify-consistency` — data point matching
- `/verify-sources` — attribution completeness
- `/verify-quotes` — quote traceability
- `/validate-financials` — arithmetic accuracy
- `/verify-links` — URL validation
- `/assess-bias` — perspective balance
- `/verify-cross-document` — structural alignment

**VS Code + Copilot users** — say *"Run all quality checks on my case study"* in Agent Mode.

**Chat tool users** — use the quality checklist in `templates/QA_WORKFLOW.md`.

Address any issues and re-run until clean.

---

## Phase 6: Publication

### Add Disclaimers

**Cowork users:**
> *"Please prepare my Main Case document for PDF export — add the required AI methodology disclaimer and review the formatting."*

**Claude Code users:**
```
/add-disclaimers
/export-pdf
```

### Export to PDF

Export from your word processor or markdown editor to PDF. Save the PDF to the `exports/` folder.

### Make Repository Public and Submit

1. Go to your repository on [github.com](https://github.com/)
2. Click **Settings → scroll to Danger Zone → Change visibility → Make public**
3. Confirm

Submit to Canvas:
1. Your **two-page report** (PDF)
2. **PDF export** of your Main Case document
3. **Link to your public GitHub repository**

### Final Git Checkpoint

**Cowork users** — open GitHub Desktop → write *"Final case study package"* → **Commit to main** → **Push origin**.

**Claude Code / VS Code terminal:**
```bash
git add -A && git commit -m "Final case study package" && git push
```

---

## Quick Reference: Cowork Prompts

| Phase | Cowork plain English | Claude Code |
|-------|---------------------|-------------|
| Configure | *"Please run setup-case"* | `/setup-case` |
| Add sources | *"Scan sources/ and register new files"* | `/add-sources` |
| Assess sources | *"Assess my source quality"* | `/assess-sources` |
| Write next document | *"Help me write the next document"* | `/write-document` |
| Check status | *"What's the current status of my case study?"* | `/check-status` |
| Verify all | *"Run all quality checks"* | `/verify-all` |
| Check financials | *"Check all financial figures"* | `/validate-financials` |
| Check bias | *"Assess my source balance"* | `/assess-bias` |
| Add disclaimers | *"Add AI methodology disclaimers"* | `/add-disclaimers` |
| Export | *"Prepare for PDF export"* | `/export-pdf` |
| Save progress | GitHub Desktop: commit + push | `/git-update` |

> **Public Policy Cases**: If your case involves public policy or political leadership, tell your AI tool during setup (select "public policy") and reference `templates/HKS_PUBLIC_POLICY_GUIDANCE.md` for adapted frameworks.
