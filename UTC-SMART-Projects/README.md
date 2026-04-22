# Transportation Research Aggregator — Skill for Claude

A reusable Claude skill that builds an AI-powered interactive research dashboard, simultaneously searching three federal transportation research databases for any keyword. Designed for researchers, professors, and graduate students at US universities.

---

## What it does

When triggered, this skill generates a fully interactive HTML dashboard that:

- **Auto-searches on load** using a default keyword (CAV — Connected & Autonomous Vehicles)
- **Queries 3 databases in parallel** using Claude's built-in web search
- **Displays filterable results** across three sections with live filter boxes
- **Exports results** as CSV files or a full HTML report

### The 3 data sources

| Database | URL | What you get |
|----------|-----|--------------|
| **RIP** | rip.trb.org | Research in Progress — project title, summary, status, lead organization, publications |
| **ROSAP** | rosap.ntl.bts.gov | National Transportation Library — publication cards with authors, year, abstract |
| **UTC** | rip.trb.org/Maps/UTC | University Transportation Centers — center name, host university, research focus, region |

---

## How to install this skill in Claude

### Step 1 — Open Claude Settings

Go to [claude.ai](https://claude.ai) and sign in. Click your profile icon in the top-right corner, then select **Settings**.

### Step 2 — Navigate to Skills

In the Settings sidebar, click **Skills** (sometimes listed under "Customization" or "Advanced").

> **Note:** Skills are available on Claude Pro, Team, and Enterprise plans.

### Step 3 — Upload the skill file

1. Click **Add skill** or **Upload skill**
2. Select the file `transportation-research-aggregator.skill` from your computer [![Download (https://custom-icon-badges.demolab.com/badge/-Download-blue?style=for-the-badge&logo=download&logoColor=white)](https://github.com/mcity/mcity-claude-skills/blob/main/UTC-SMART-Projects/transportation-research-aggregator.skill)
3. Claude will validate the file and show a confirmation — click **Install**

The skill is now active in your account.

---

## How to use it

Once installed, simply describe what you want in any Claude conversation. Example prompts that trigger this skill:

```
Search transportation research databases for CAV projects
```
```
Find publications on connected autonomous vehicles in ROSAP and RIP
```
```
Search RIP and UTC centers for V2X research
```
```
Aggregate federal transportation research on pedestrian safety
```
```
Show me research from rip.trb.org on electric vehicles
```

Claude will automatically detect that this skill applies and build the interactive dashboard for you.

### Changing the search term

The dashboard defaults to **CAV**. You can specify any term in your prompt:

- `"search for V2X"` → pre-fills V2X
- `"look up autonomous trucks"` → pre-fills autonomous trucks
- `"find research on pedestrian detection"` → pre-fills pedestrian detection

You can also type directly in the search box inside the dashboard and click **Search** to re-fetch all three sources.

---

## Dashboard features

### Filtering results
Each section (RIP, ROSAP, UTC) has its own filter box. Type any keyword to narrow down results within that section — no re-fetch required, filtering happens instantly in your browser.

### Status badges (RIP projects)
Projects are tagged with color-coded status pills:
- **Active** (green) — currently funded and ongoing
- **In Progress** (blue) — underway
- **Completed** (gray) — finished projects

### Downloading results

| Button | What it downloads |
|--------|-------------------|
| Download RIP as CSV | Spreadsheet of all RIP project rows |
| Download ROSAP as CSV | Spreadsheet of all ROSAP publication rows |
| Download full HTML report | Single HTML file combining all 3 sections — shareable with colleagues |

---

## Example use cases

**Graduate student writing a literature review on CAV safety:**
> "Search transportation research databases for CAV safety"

**Professor preparing a grant proposal on V2I infrastructure:**
> "Find federal research and UTC centers working on V2I"

**Researcher tracking active projects on pedestrian detection:**
> "Search RIP for active pedestrian detection projects and show related ROSAP publications"

**University administrator mapping UTC centers by region:**
> "Show all UTC centers related to freight and logistics"

---

## Tips for best results

- **Be specific**: `"CAV safety intersection"` returns more targeted results than just `"vehicles"`
- **Use acronyms**: TRB databases index by common transportation acronyms (CAV, V2X, AV, DSRC, MaaS, etc.)
- **Combine concepts**: `"connected vehicles urban"` will surface projects at the intersection of both topics
- **Export early**: Download the HTML report to save a snapshot — results may change as databases are updated

---

## Technical notes

- The skill uses Claude's web search capability to fetch live data from each source at search time
- Results are as current as the underlying databases — no caching
- Each search typically takes 20–40 seconds as all 3 sources are queried in parallel
- Requires an active internet connection and a Claude plan that supports skills and web search

---

## Support

If the skill doesn't trigger automatically, try rephrasing your prompt to include one of the trigger phrases listed above, or simply type:

```
Use the transportation research aggregator skill to search for [your term]
```

For issues with the skill file itself, re-download and re-upload it via Settings → Skills.
