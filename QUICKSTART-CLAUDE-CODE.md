# Quick Start: Claude Code — Alternative Path

This guide walks you through building your Harvard Business School (HBS)-style case study using **Claude Code** — an alternative path for students who already have Claude Code configured. Claude Code runs in your terminal, reads and writes your repository files directly, and uses `/slash-commands` to automate each phase of the workflow.

> **Not set up yet?** If you don't already have Claude Code installed, the [Claude Cowork path](QUICKSTART-CLAUDE-COWORK.md) is simpler to get started — no terminal or CLI tools required.

---

## What You Need

| Requirement | Details |
| --- | --- |
| **Claude Pro subscription** | ~$20/month at [claude.ai](https://claude.ai/) — required for Claude Code access |
| **Claude Code CLI** | Install at [claude.ai/code](https://claude.ai/code) — follow the installation instructions for your OS |
| **GitHub account** | Free at [github.com](https://github.com/) — needed to create your repo from the template |
| **Git** | Usually pre-installed on Mac; Windows users install from [git-scm.com](https://git-scm.com/downloads) |
| **Perplexity** | Used separately for research queries and source discovery — access via AU at [perplexity.ai](https://www.perplexity.ai/) |

You do **not** need GitHub Desktop, VS Code, or GitHub Education for this path. Git and Claude Code handle everything from the terminal.

---

## Step 1: Create Your Repository from the Template

1. Go to the repository template on GitHub (link on the Canvas page for this assignment).
2. Click the green **"Use this template"** button near the top right.
3. Select **"Create a new repository"**.
4. Name your repo something like `acme-dt-case-study` (use your company name).
5. Set visibility to **Private** for now — you will make it public before submitting.
6. Click **"Create repository"**.

GitHub creates your personal copy of the starter kit. This is the repository you will submit.

---

## Step 2: Clone Your Repository

Open your terminal and run:

```bash
cd ~/Desktop
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
cd YOUR-REPO-NAME
```

Replace `YOUR-USERNAME` and `YOUR-REPO-NAME` with your actual GitHub username and repo name. You can find the exact URL on your repository's GitHub page — click the green **"Code"** button and copy the HTTPS URL.

---

## Step 3: Open Your Repository in Claude Code

From inside your cloned repository folder, launch Claude Code:

```bash
claude
```

Claude Code reads `CLAUDE.md` automatically and loads the project context. It also detects the `/slash-commands` in `.claude/skills/`. You are ready to begin.

> **First time in this repo?** Say: *"Please read README.md and CLAUDE.md so you understand the project structure and your role. Then help me get started."*

---

## Step 4: Start Your Running Log

The assignment requires you to maintain an `ai-usage-log.md` file recording your AI tool usage throughout the project. Start it at the beginning of every session.

**Copy and paste this prompt at the start of every Claude Code session:**

> *"Please open ai-usage-log.md and add a new entry for today's session. Record the current date and time, a one-sentence summary of where we left off last session, and what we plan to accomplish today. Continue updating this file as we work — note each major action taken, key prompts used, where AI output was helpful, and where you had to correct or verify something. At the end of our session, add a closing entry summarizing what was completed and what to tackle next."*

This produces the iterative, timestamped log the assignment requires and serves as the primary record of your process for grading.

---

## Step 5: Configure Your Case Study

Run the setup skill:

```
/setup-case
```

Claude Code will walk you through a short Q&A covering:

- Company name and industry
- The DT initiative you are researching
- Your protagonist (the executive who drove the initiative)
- The course this is for

Claude Code writes the configuration to `case-config.yaml` automatically. This file is read by all subsequent skills, so you do not need to edit it manually.

**If you already know your company and just want to jump in**, you can say:

> *"I'm doing a case study on [Company]'s [initiative]. The protagonist is [Name], [Title]. Please configure my case and then help me assess my source readiness."*

---

## Step 6: Add Your Research Sources

Place your research files in the appropriate `sources/` subfolders:

| Subfolder | What goes here |
| --- | --- |
| `sources/transcripts/` | Interview transcripts, podcast notes, conference talk notes |
| `sources/financial/` | SEC filings, earnings reports, investor presentations |
| `sources/news/` | News articles, press releases |
| `sources/reports/` | Industry reports, analyst research, market data |

Then register and assess them:

```
/add-sources
```

This scans for new files, asks metadata questions, assigns quality tiers (T1/T2/T3), and updates the Source Registry.

Next, get a go/no-go assessment:

```
/assess-sources
```

- **Green** — ready to write
- **Yellow** — can proceed with caution; gaps noted
- **Red** — need more sources before writing

**Using Perplexity for research**: Use Perplexity (in your browser, separately) to find executive interviews, financial data, news coverage, and analyst reports. Copy relevant content or save files, then drop them into the appropriate `sources/` subfolder.

---

## Step 7: Write Your Case Study Documents

Create the three required documents **in this order**. Each builds on the previous.

> **Note**: The starter kit supports four documents (including a Teaching Note). This assignment requires three: Additional Sources, Main Case, and Technical Supplement. You do not need to produce the Teaching Note.

Run the writing skill for each document:

```
/write-document
```

Claude Code will:
- Check that prerequisites are met before starting
- Determine the next document to write
- Ask document-specific setup questions
- Write section by section, pausing for your feedback
- Flag unverified claims inline
- Save the completed document to `case-study/`

### Case Study Document 1: Additional Sources

Compiles your raw research into a structured reference — excerpts, quotes, timeline, bibliography. Run `/write-document` and Claude Code will select this first.

### Case Study Document 2: Main Case Narrative (1,500–3,000 words)

The protagonist-centered narrative. When prompted for the opening scene, push for tension — not a company history summary.

### Case Study Document 3: Technical Supplement (500–1,500 words)

Supporting context: industry economics, competitive landscape, technology frameworks, glossary.

### Research Loops

During writing, Claude Code will pause when it finds gaps — a missing number, an unverifiable claim, a date it can't confirm. When this happens:

1. Find the source (Perplexity helps here)
2. Drop it into the appropriate `sources/` subfolder
3. Run `/add-sources` to register it
4. Resume writing — Claude Code picks up where it left off

Budget 2–4 research loops per document. This is expected, not a problem.

---

## Step 8: Verify Quality and Accuracy

This step is **just as important as writing** — it is a graded component.

```
/verify-all
```

This runs all checks in sequence:

| Check | What It Does |
| --- | --- |
| `/verify-consistency` | Data point matching across documents |
| `/verify-sources` | Attribution completeness |
| `/verify-quotes` | Quote traceability to dated sources |
| `/validate-financials` | Arithmetic accuracy |
| `/verify-links` | URL validation |
| `/assess-bias` | Perspective balance |
| `/verify-cross-document` | Structural alignment |

For every flag raised, either find a source that confirms the claim or remove it. Then update your log:

> *"Please update ai-usage-log.md with all the verification issues found and the corrections I made."*

---

## Step 9: Commit and Push Your Work

After each major step (sources registered, each document drafted, verification complete), save your progress to GitHub.

**Option A — use the built-in skill:**

```
/git-update
```

Claude Code will stage all changes, prompt for a commit message, commit, and push.

**Option B — use the terminal directly:**

```bash
git add -A && git commit -m "Complete Main Case first draft" && git push
```

> **Recommended commit points**: after sources are registered, after each document is drafted, after verification is complete, and after any significant revision.

---

## Step 10: Export PDFs

When your case study is complete, add disclaimers and prepare for export:

```
/add-disclaimers
/export-pdf
```

Claude Code will format the documents and provide export-ready versions. Save PDFs to the `exports/` folder.

---

## Step 11: Make Your Repository Public and Submit

**Make your repo public** (required for submission):

1. Go to your repository on [github.com](https://github.com/).
2. Click **Settings**.
3. Scroll to the **Danger Zone** section at the bottom.
4. Click **Change repository visibility → Make public**.
5. Confirm.

**Submit to Canvas**:

1. Your **two-page report** (PDF) — summarizing case quality, verification, reflection, and AI tool usage
2. **PDF export(s) of your case study documents** (may be combined into one PDF):
   - Document 1: Main Case Narrative
   - Document 2: Technical Supplement
   - Document 3: Additional Sources
3. **Link to your public GitHub repository**

---

## Tips

**Start each session with the running log prompt.** The ai-usage-log.md is a graded deliverable. Starting each session with the prompt above keeps it current and timestamped.

**Use `/check-status` anytime.** This gives you a project dashboard — what's done, what's next, current verification debt count, and source quality summary.

**Use Perplexity for discovery, Claude Code for analysis.** Perplexity is better at finding sources; Claude Code is better at analyzing and synthesizing them. A good loop: Perplexity finds the source → you save the file → Claude Code analyzes it in context.

**Be specific when Claude Code is vague.** If a draft says "the company invested significantly," push back: *"Can you find a specific dollar figure from our sources, or flag this as unverified?"*

**Verification is a graded component, not a formality.** The assignment explicitly grades on what errors you caught and corrected. Document every correction in ai-usage-log.md.

**Commit after every session.** `/git-update` takes five seconds. A commit after every session gives you a safety net and builds the iterative history the assignment expects.

---

## Troubleshooting

| Problem | Solution |
| --- | --- |
| `claude: command not found` | Make sure Claude Code is installed and your terminal PATH is updated. Restart your terminal after installing |
| `/setup-case` not found | Make sure you ran `claude` from inside the cloned repository folder, not a parent directory |
| `git: command not found` | Install Git from [git-scm.com/downloads](https://git-scm.com/downloads), then restart your terminal |
| `git clone` fails | Use the HTTPS URL (starts with `https://`), not SSH. Find it under the green "Code" button on GitHub |
| Claude Code doesn't know my case | Say: *"Please read case-config.yaml and CLAUDE.md to catch up on my project"* |
| Session lost context | Say: *"Please read ai-usage-log.md, case-config.yaml, and the latest document in case-study/ to catch up"* |
| Skill not found | Make sure you're in the repo root. Run `ls .claude/skills/` to confirm skills are present |
| Claude Code produces unverifiable claims | This is expected — flag it, find a source, or remove the claim. Document in ai-usage-log.md |
| Can't push to GitHub | Run `git remote -v` to confirm the remote is set. Run `git push --set-upstream origin main` if needed |

Still stuck? Ask your instructor or TA for help.
