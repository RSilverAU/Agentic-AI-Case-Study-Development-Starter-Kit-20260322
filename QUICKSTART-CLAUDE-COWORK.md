# Quick Start: Claude Cowork — Recommended Path

This guide walks you through building your Harvard Business School (HBS)-style case study using **Claude Cowork** — the recommended path for this assignment. Cowork gives Claude direct access to your case study folder on your computer. You interact entirely through a chat interface; Claude reads and writes your files, guides the research and writing process, and keeps a running log of everything you do.

No terminal. No command-line tools. No extensions to install beyond Claude itself.

NOTE: See **WORKFLOW.md** in the repository for more details about the process of building your business case.

---

## What You Need

| Requirement                 | Details                                                                                                                  |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Claude Pro subscription** | $20/month at [claude.ai](https://claude.ai/) — gives you access to the Claude desktop app                                |
| **Claude desktop app**      | Download at [claude.ai/download](https://claude.ai/download) — Mac and Windows                                           |
| **GitHub account**          | Free at [github.com](https://github.com/) — needed to create your repo from the template                                 |
| **GitHub Desktop**          | Free at [desktop.github.com](https://desktop.github.com/) — required for submission (see note below)                     |
| **Perplexity**              | Used separately for research queries and source discovery — access via AU at [perplexity.ai](https://www.perplexity.ai/) |

> **Why GitHub Desktop is required**: The assignment requires you to submit a link to a public GitHub repository containing your case study. GitHub Desktop handles all the git mechanics — committing your work and pushing it to GitHub — with no command-line knowledge needed. You will use it for 2–3 clicks after each major work session.

You do **not** need VS Code, Claude Code, a terminal, or GitHub Education for this path.

---

## Step 1: Create Your Repository from the Template

1. Go to [github.com/RSilverAU/Agentic-AI-Case-Study-Development-Starter-Kit-20260322](https://github.com/RSilverAU/Agentic-AI-Case-Study-Development-Starter-Kit-20260322) *(use the link provided in your course materials)*.
2. Click the green **"Use this template"** button near the top right.
3. Select **"Create a new repository"**.
4. Name your repo something like `acme-dt-case-study` (use your company name).
5. Set visibility to **Private** for now — you will make it public before submitting.
6. Click **"Create repository"**.

GitHub creates your personal copy of the starter kit. This is the repository you will submit.

---

## Step 2: Clone Your Repository Using GitHub Desktop

Cloning downloads your repository to your computer so Claude Cowork can access the files.

1. Install [GitHub Desktop](https://desktop.github.com/) if you haven't already.
2. Open GitHub Desktop. Sign in with your GitHub account.
3. Go to **File → Clone repository**.
4. Find your newly created repo (it will appear in the list) and click it.
5. Choose a **local path** — pick a folder that is **not** inside OneDrive, iCloud, or Dropbox. These sync services can interfere with how Cowork accesses files.
   - **Windows example**: `C:\Users\YourName\Documents\CaseStudy\`
   - **Mac example**: `/Users/YourName/Documents/CaseStudy/`
6. Click **Clone**.

GitHub Desktop downloads all the starter kit files to that local folder. You should see folders named `case-study/`, `sources/`, `exports/`, and files like `README.md` and `CLAUDE.md`.

---

## Step 3: Open Your Repository in Cowork

1. Open the Claude desktop app and sign in with your Claude Pro account.
2. Enable **Cowork mode** — look for a folder icon or "Select a folder" option in the interface.
3. Select the local folder where GitHub Desktop cloned your repository (the same path you chose in Step 2).

Claude now has direct access to all your case study files. You are ready to begin.

---

## Step 4: Start Your Running Log

The assignment requires you to maintain an `ai-usage-log.md` file recording your AI tool usage throughout the project. Claude Cowork will maintain this automatically — but you need to start it at the beginning of every session.

**Copy and paste this prompt at the start of every Cowork session:**

> *"Please open ai-usage-log.md and add a new entry for today's session. Record the current date and time, a one-sentence summary of where we left off last session, and what we plan to accomplish today. Continue updating this file as we work — note each major action taken, key prompts used, where AI output was helpful, and where you had to correct or verify something. At the end of our session, add a closing entry summarizing what was completed and what to tackle next."*

This produces the iterative, timestamped log the assignment requires and serves as the primary record of your process for grading.

**At the start of your very first session**, also say:

> *"Please read README.md and CLAUDE.md so you understand the project structure and your role. Then help me get started."*

---

## Step 5: Configure Your Case Study

Tell Claude about your company and DT initiative. In the Cowork chat, say:

> *"Please run setup-case."*

Claude will read the setup skill and walk you through a short Q&A covering:

- Company name and industry
- The DT initiative you are researching
- Your protagonist (the executive who drove the initiative)
- The course this is for

Claude writes the configuration to `case-config.yaml` automatically. This file is read by all subsequent steps, so you do not need to edit it manually.

**If you already know your company and just want to jump in**, you can say:

> *"I'm doing a case study on [Company]'s [initiative]. The protagonist is [Name], [Title]. Please configure my case and then help me assess my source readiness."*

---

## Step 6: Add Your Research Sources

Place your research files in the `sources/` folder. You can do this in two ways:

**Option A: Drag files into the Cowork chat**

Drag your source files (PDFs, Word docs, text files) into the chat window and say:

> *"Please save copies of these files to the appropriate subfolder inside sources/ — transcripts go in sources/transcripts/, financial documents in sources/financial/, news articles in sources/news/, and industry reports in sources/reports/."*

**Option B: Copy files directly**

Open File Explorer (Windows) or Finder (Mac) and drag your files into the appropriate subfolders yourself.

**After adding sources**, ask Claude to register and assess them:

> *"Please scan the sources/ folder, register any new files in the Source Registry, and give me an honest assessment of my source quality. Tell me whether I have enough to start writing, and what gaps I should fill first."*

Claude will evaluate depth, breadth, and reliability, and give you a **go/no-go** signal:

- **Green** — ready to write
- **Yellow** — can proceed with caution; gaps noted
- **Red** — need more sources before writing

**Using Perplexity for research**: Use Perplexity (in your browser, separately) to find executive interviews, financial data, news coverage, and analyst reports. Copy relevant content or save files, then bring them into your `sources/` folder.

---

## Step 7: Write Your Case Study Documents

Create the three required documents **in this order**. Each builds on the previous.

> **Note**: The starter kit supports four documents (including a Teaching Note). This assignment requires three: Additional Sources, Main Case, and Technical Supplement. You do not need to produce the Teaching Note.

### 7a. Additional Sources Document

This compiles your raw research into a structured reference — excerpts, quotes, timeline, bibliography.

> *"Please help me write the Additional Sources document. Start by reviewing what's in sources/ and then compile the key material into a structured bibliography with excerpts and a timeline of significant events."*

### 7b. Main Case Narrative (1,500–3,000 words)

The protagonist-centered narrative that reads like business journalism.

> *"Please help me write the Main Case. Before you start, offer me 2–3 options for the opening scene — I want a moment of decision or tension, not a company history summary. Then write section by section, pausing after each section for my feedback before continuing."*

**During writing, Claude will discover gaps** — a missing number, an unverifiable claim, a date you can't confirm. This is normal. When it happens, pause writing, find the source (Perplexity helps here), bring it into `sources/`, and resume. Budget 2–4 of these research loops per document.

### 7c. Technical Supplement (500–1,500 words)

Supporting context: industry economics, competitive landscape, technology frameworks, glossary.

> *"Please help me write the Technical Supplement. Cover the industry economics, competitive landscape, and key technology concepts relevant to [Company]'s initiative."*

### Keeping your log current

Remind Claude periodically to update your log:

> *"Please update ai-usage-log.md with what we've done so far in this session."*

---

## Step 8: Verify Quality and Accuracy

This step is **just as important as writing** — it is a graded component. Before considering your case complete:

> *"Please run all quality checks on my case study. Check every factual claim against the sources in sources/, flag any quotes or statistics you cannot trace back to a named source, and identify anything that may be AI-generated rather than sourced."*

Claude will check:

- Quote traceability — every quote back to a dated source
- Data point attribution — every number to a named document
- Cross-document consistency — same figures used throughout
- Narrative accuracy — does the story match what sources actually say?

**Your job during verification**: For every flag Claude raises, either find a source that confirms it or remove the claim. Document what you found and corrected — this feeds directly into your two-page report.

> *"Please update ai-usage-log.md with all the verification issues found and the corrections I made."*

---

## Step 9: Commit and Push Your Work Using GitHub Desktop

After each major step (sources registered, each document drafted, verification complete), save your progress to GitHub:

1. Open **GitHub Desktop**.
2. You will see a list of changed files on the left. Write a short commit message in the **Summary** box at the bottom left describing what you completed (e.g., *"Complete Main Case first draft"*).
3. Click **Commit to main**.
4. Click **Push origin** (top right).

Your work is now saved to GitHub with a timestamped record. Do this after every session — it only takes 30 seconds and gives you a full version history.

> **Recommended commit points**: after sources are registered, after each document is drafted, after verification is complete, and after any significant revision.

---

## Step 10: Export PDFs

When your case study is complete:

> *"Please prepare my case documents for PDF export — add the required AI methodology disclaimer to each and review the formatting."*

Then export each document from your word processor or markdown editor to PDF. Save all PDFs to the `exports/` folder. You may submit the three documents as separate PDFs or combine them into one — either is acceptable.

---

## Step 11: Make Your Repository Public and Submit

**Make your repo public** (required for submission):

1. Go to your repository on [github.com](https://github.com/).
2. Click **Settings**.
3. Scroll to the **Danger Zone** section at the bottom.
4. Click **Change repository visibility → Make public**.
5. Confirm.

**Submit to Canvas**: See the **Assignment Instructions PDF** on Canvas for the complete deliverables list and file-naming requirements. In brief, you will submit your two-page report (PDF), PDF export(s) of your three case documents (Main Case, Technical Supplement, and Additional Sources — combined into one PDF or separate files), and a link to your public GitHub repository.

---

## Tips

**Start each session with the running log prompt.** This one habit keeps your ai-usage-log.md current and ensures you always pick up exactly where you left off. Claude reads the log to restore context between sessions.

**Let Claude lead the process.** You don't need to know the workflow in detail — Claude does. Say *"Where should we pick up?"* at the start of a session and it will check your current state and recommend the next step.

**Use Perplexity for discovery, Claude for analysis.** Perplexity is better at finding sources; Claude is better at analyzing and synthesizing them. A good loop: Perplexity finds the source → you save the content → Claude analyzes it in context.

**Be specific in your case.** When Claude produces vague output like "the company invested significantly in technology," push back: *"Can you find a specific dollar figure from our sources, or flag this as unverified?"*

**Verification is a graded component, not a formality.** The assignment explicitly grades on what errors you caught and corrected. Document every correction in your ai-usage-log.md.

**Keep your working folder local.** The folder Cowork accesses must not be inside OneDrive or iCloud. Keep it local; push finished work to GitHub for backup and submission.

**Commit early and often.** GitHub Desktop commits take 30 seconds. A commit after every session gives you a safety net and builds the iterative history the assignment expects.

---

## Troubleshooting

| Problem                                  | Solution                                                                                                                               |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------- |
| Cowork can't access my files             | Make sure the folder is **not** inside OneDrive or iCloud. Move it to a local path and re-select it in Cowork                          |
| Claude doesn't know my case details      | Say: *"Please read case-config.yaml and CLAUDE.md to catch up on my project"*                                                          |
| Session lost context between chats       | Say: *"Please read ai-usage-log.md, case-config.yaml, and the latest document in case-study/ to catch up"*                             |
| Claude says it can't find a skill        | Say: *"Please read the file at .claude/skills/[skill-name].md and follow its instructions"* (e.g., `.claude/skills/assess-sources.md`) |
| Claude produces unverifiable claims      | This is expected — flag it, find a source, or remove the claim. Document in ai-usage-log.md                                            |
| GitHub Desktop shows "no changes"        | Cowork may have saved changes inside the folder that Git doesn't see yet. Try clicking **Repository → Refresh** in GitHub Desktop      |
| Can't push to GitHub                     | Make sure you're signed in to GitHub Desktop with the same account that owns the repo. Try **Repository → Push** from the menu         |
| Sources folder is empty after dragging   | Confirm Claude has access to the correct local folder in Cowork. Ask: *"What files can you see in sources/?"*                          |
| Can't find Cowork mode in the Claude app | Check that you have the latest version of the Claude desktop app and an active Claude Pro subscription                                 |

Still stuck? Ask your instructor or TA for help.
