# Quick Start: VS Code + GitHub Copilot — Alternative Path

This guide walks you through building your Harvard Business School (HBS)-style case study using **VS Code with GitHub Copilot in Agent Mode** — an alternative path for students who already have GitHub Education and Copilot configured. Copilot reads your repository files directly through VS Code and guides the entire workflow through natural-language conversation — no slash commands required.

> **Not set up yet?** If you don't already have GitHub Education and VS Code + Copilot configured, the [Claude Cowork path](QUICKSTART-CLAUDE-COWORK.md) is simpler to get started — no extensions or GitHub Education required.

---

## What You Need

| Requirement | Details |
| --- | --- |
| **GitHub Education account** | Free at [education.github.com](https://education.github.com) — gives you **Copilot Pro at no cost** |
| **VS Code** | Free at [code.visualstudio.com](https://code.visualstudio.com/) |
| **GitHub Copilot extension** | Install from the VS Code Extensions panel — search "GitHub Copilot" |
| **GitHub account** | Free at [github.com](https://github.com/) — needed to create your repo from the template |
| **Git** | Usually pre-installed on Mac; Windows users install from [git-scm.com](https://git-scm.com/downloads) |
| **Perplexity** | Used separately for research queries and source discovery — access via AU at [perplexity.ai](https://www.perplexity.ai/) |

> **GitHub Education**: Sign up at [education.github.com](https://education.github.com) with your AU email address. Approval typically takes 1–3 days. Once approved, Copilot Pro is activated automatically on your GitHub account — you will see it in VS Code after signing in.

You do **not** need Claude Code, Claude Cowork, or GitHub Desktop for this path. VS Code's built-in Source Control panel handles git operations.

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

**Option A — VS Code terminal:**

Open VS Code, then open the terminal (**View → Terminal** or `` Ctrl+` ``) and run:

```bash
cd ~/Desktop
git clone https://github.com/YOUR-USERNAME/YOUR-REPO-NAME.git
```

Replace `YOUR-USERNAME` and `YOUR-REPO-NAME` with your actual values. Find the exact URL on your GitHub repo page — click the green **"Code"** button and copy the HTTPS link.

**Option B — VS Code directly:**

Open the Command Palette (**Cmd/Ctrl+Shift+P**), type `Git: Clone`, paste your repository URL, and choose a local folder to clone into.

> **Folder location**: Choose a local folder that is **not** inside OneDrive, iCloud, or Dropbox. Sync services can cause file conflicts.

---

## Step 3: Open Your Repository in VS Code

1. In VS Code, go to **File → Open Folder** and select the folder where you cloned your repository.
2. Open the **Copilot Chat panel** — click the chat bubble icon in the left sidebar, or use **View → GitHub Copilot Chat**.
3. In the chat panel, click the **mode selector** (the dropdown at the top of the chat) and select **"Agent"**.

Copilot automatically reads `.github/copilot-instructions.md`, which contains the project's behavioral guidance. You are ready to begin.

> **First time in this repo?** In the Copilot chat, say: *"Please read README.md and the copilot instructions so you understand the project structure and your role. Then help me get started."*

---

## Step 4: Start Your Running Log

The assignment requires you to maintain an `ai-usage-log.md` file recording your AI tool usage throughout the project. Start it at the beginning of every session.

**Copy and paste this prompt at the start of every Copilot session:**

> *"Please open ai-usage-log.md and add a new entry for today's session. Record the current date and time, a one-sentence summary of where we left off last session, and what we plan to accomplish today. Continue updating this file as we work — note each major action taken, key prompts used, where AI output was helpful, and where you had to correct or verify something. At the end of our session, add a closing entry summarizing what was completed and what to tackle next."*

This produces the iterative, timestamped log the assignment requires and serves as the primary record of your process for grading.

---

## Step 5: Configure Your Case Study

In the Copilot chat (Agent Mode), say:

> *"Help me configure my case study."*

Copilot will walk you through a short Q&A covering:

- Company name and industry
- The DT initiative you are researching
- Your protagonist (the executive who drove the initiative)
- The course this is for

Copilot writes the configuration to `case-config.yaml` automatically. This file is read by all subsequent steps, so you do not need to edit it manually.

**If you already know your company and just want to jump in**, you can say:

> *"I'm doing a case study on [Company]'s [initiative]. The protagonist is [Name], [Title]. Please configure my case and then help me assess my source readiness."*

---

## Step 6: Add Your Research Sources

Place your research files in the appropriate `sources/` subfolders. You can do this through VS Code's Explorer panel (drag and drop) or File Explorer / Finder:

| Subfolder | What goes here |
| --- | --- |
| `sources/transcripts/` | Interview transcripts, podcast notes, conference talk notes |
| `sources/financial/` | SEC filings, earnings reports, investor presentations |
| `sources/news/` | News articles, press releases |
| `sources/reports/` | Industry reports, analyst research, market data |

Then ask Copilot to register and assess them (Agent Mode):

> *"Scan the sources folder and register any new files in the Source Registry."*

> *"Evaluate my source quality and give me a go/no-go assessment — tell me whether I have enough to start writing and what gaps I should fill first."*

Copilot evaluates depth, breadth, and reliability and gives you a **go/no-go** signal:
- **Green** — ready to write
- **Yellow** — can proceed with caution; gaps noted
- **Red** — need more sources before writing

**Using Perplexity for research**: Use Perplexity (in your browser, separately) to find executive interviews, financial data, news coverage, and analyst reports. Copy relevant content or save files, then drop them into the appropriate `sources/` subfolder.

---

## Step 7: Write Your Case Study Documents

Create the three required documents **in this order**. Each builds on the previous.

> **Note**: The starter kit supports four documents (including a Teaching Note). This assignment requires three: Additional Sources, Main Case, and Technical Supplement. You do not need to produce the Teaching Note.

Ask Copilot to guide you through each document (Agent Mode):

> *"Help me write the next document in my case study."*

Copilot will check prerequisites, determine the next document, ask setup questions, write section by section pausing for your feedback, flag unverified claims, and save the completed document to `case-study/`.

### Case Study Document 1: Additional Sources

Compiles your raw research into a structured reference — excerpts, quotes, timeline, bibliography.

> *"Help me write the Additional Sources document. Start by reviewing what's in sources/ and compile the key material into a structured bibliography with excerpts and a timeline of significant events."*

### Case Study Document 2: Main Case Narrative (1,500–3,000 words)

The protagonist-centered narrative. When offered opening scene options, push for tension — not a company history summary.

> *"Help me write the Main Case. Before you start, offer me 2–3 options for the opening scene — I want a moment of decision or tension, not a company history summary. Then write section by section, pausing after each section for my feedback before continuing."*

### Case Study Document 3: Technical Supplement (500–1,500 words)

Supporting context: industry economics, competitive landscape, technology frameworks, glossary.

> *"Help me write the Technical Supplement. Cover the industry economics, competitive landscape, and key technology concepts relevant to [Company]'s initiative."*

### Research Loops

During writing, Copilot will pause when it finds gaps — a missing number, an unverifiable claim, a date it can't confirm. When this happens:

1. Find the source (Perplexity helps here)
2. Drop it into the appropriate `sources/` subfolder
3. Ask Copilot: *"A new source has been added to sources/. Please register it and incorporate it into what we were writing."*
4. Resume writing from where you left off

Budget 2–4 research loops per document. This is expected, not a problem.

### Keeping your log current

Remind Copilot periodically:

> *"Please update ai-usage-log.md with what we've done so far in this session."*

---

## Step 8: Verify Quality and Accuracy

This step is **just as important as writing** — it is a graded component.

> *"Run all quality checks on my case study."*

Copilot will check:
- Quote traceability — every quote back to a dated source
- Data point attribution — every number to a named document
- Cross-document consistency — same figures used throughout
- Narrative accuracy — does the story match what sources actually say?

You can also run individual checks:

| What to ask | What it checks |
| --- | --- |
| *"Check for data consistency across my documents"* | Numbers and dates match throughout |
| *"Verify that all quotes are properly attributed"* | Every quote traced to a source |
| *"Check the arithmetic and financial figures"* | Percentages, totals, calculations |
| *"Analyze my sources for perspective balance"* | Diversity of viewpoints |

For every flag Copilot raises, either find a source that confirms the claim or remove it. Then update your log:

> *"Please update ai-usage-log.md with all the verification issues found and the corrections I made."*

---

## Step 9: Commit and Push Your Work

After each major step (sources registered, each document drafted, verification complete), save your progress to GitHub.

**Option A — VS Code Source Control panel:**

1. Click the **Source Control icon** in the left sidebar (looks like a branch).
2. You will see a list of changed files. Review them.
3. Type a short commit message in the **Message** box (e.g., *"Complete Main Case first draft"*).
4. Click the **✓ Commit** button, then click **Sync Changes** (or **Push**) to push to GitHub.

**Option B — VS Code terminal:**

```bash
git add -A && git commit -m "Complete Main Case first draft" && git push
```

> **Recommended commit points**: after sources are registered, after each document is drafted, after verification is complete, and after any significant revision.

---

## Step 10: Export PDFs

When your case study is complete, ask Copilot to prepare for export:

> *"Add AI methodology disclaimers to my documents and prepare them for PDF export."*

Then export from VS Code's markdown preview or your preferred markdown editor to PDF. Save PDFs to the `exports/` folder.

---

## Step 11: Make Your Repository Public and Submit

**Make your repo public** (required for submission):

1. Go to your repository on [github.com](https://github.com/).
2. Click **Settings**.
3. Scroll to the **Danger Zone** section at the bottom.
4. Click **Change repository visibility → Make public**.
5. Confirm.

**Submit to Canvas**: Follow the submission instructions on the Canvas assignment page. In brief, you will submit your two-page report (PDF), PDF export(s) of your case study documents, and a link to your public GitHub repository. See the assignment page for file naming requirements and the complete deliverables list.

---

## Tips

**Start each session with the running log prompt.** The ai-usage-log.md is a graded deliverable. Starting each session with the prompt above keeps it current and timestamped.

**Always use Agent Mode, not Chat Mode.** Agent Mode lets Copilot read and write your repository files. Regular Chat Mode cannot access files on disk — make sure the mode selector in the chat panel shows "Agent."

**Check project status anytime:**

> *"Show me my project status and what to do next."*

Copilot reads `case-config.yaml` and `case-study/` to report what's complete, what's in progress, and what gaps remain.

**Use Perplexity for discovery, Copilot for analysis.** Perplexity is better at finding sources; Copilot is better at analyzing and synthesizing them. A good loop: Perplexity finds the source → you save the file → Copilot analyzes it in context.

**Be specific when Copilot is vague.** If a draft says "the company invested significantly," push back: *"Can you find a specific dollar figure from our sources, or flag this as unverified?"*

**Verification is a graded component, not a formality.** The assignment explicitly grades on what errors you caught and corrected. Document every correction in ai-usage-log.md.

**Commit after every session.** VS Code's Source Control panel makes this a 4-click operation. A commit after every session builds the iterative history the assignment expects.

---

## Troubleshooting

| Problem | Solution |
| --- | --- |
| Copilot chat not visible | Go to **View → GitHub Copilot Chat** to open the panel |
| Copilot not in Agent Mode | Click the mode selector dropdown at the top of the Copilot chat panel and select "Agent" |
| GitHub Copilot not activated | Make sure you've completed the GitHub Education sign-up and are signed into VS Code with the same GitHub account |
| `git: command not found` | Install Git from [git-scm.com/downloads](https://git-scm.com/downloads), then restart VS Code |
| `git clone` fails | Use the HTTPS URL (starts with `https://`), not SSH |
| Copilot doesn't read my files | Make sure you opened the **cloned folder** in VS Code, not just a single file. Go to **File → Open Folder** |
| Copilot can't find a source file | Confirm the file is in the correct `sources/` subfolder. Ask: *"What files can you see in sources/?"* |
| Session lost context | Say: *"Please read ai-usage-log.md, case-config.yaml, and the latest document in case-study/ to catch up on where we are"* |
| Copilot produces unverifiable claims | This is expected — flag it, find a source, or remove the claim. Document in ai-usage-log.md |
| Can't push to GitHub | Make sure you're signed into VS Code with the GitHub account that owns the repo. Check **Accounts** in the bottom-left corner of VS Code |

Still stuck? Ask your instructor or TA for help.
