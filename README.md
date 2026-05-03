# Swedish Home Buying Guide

A personalised property evaluation tool for first-time Swedish home buyers. Track multiple properties through a structured 6-stage journey — from financial readiness to closing the deal.

**Live demo:** Deploy to GitHub Pages using the instructions below.

---

## What it does

- **Stage 1 — Am I Ready?** Financial readiness calculator (KALP, lånelöfte estimate)
- **Stage 2 — What Can I Afford?** True monthly cost calculator for Bostadsrätt & Äganderätt
- **Stage 3 — Finding the Right Home** Viewing checklist + personalised property scorer (0–100)
- **Stage 4 — Reading the Documents** AI analysis of BRF årsredovisning or besiktningsprotokoll
- **Stage 5 — Making an Offer** AI bid strategy generator
- **Stage 6 — Closing the Deal** Contract & moving checklist

Property scores are weighted by the user's priorities, set in the setup wizard at first launch.

---

## Deploy to GitHub Pages (5 minutes)

1. Fork or create a new repo, upload `index.html`
2. Go to **Settings → Pages → Source → Deploy from branch → main / (root)**
3. GitHub will publish it at `https://<your-username>.github.io/<repo-name>/`

That's it — no build step needed.

---

## Setting up AI features

The AI analysis features (Stage 4 BRF analysis, Stage 5 bid strategy, Knowledge Fountain Q&A) require an Anthropic API key.

### For user testing (researcher sets up devices)

1. Open the app on each test device
2. Tap the **⚙ Set AI API key** button in the sidebar (desktop) or at the bottom of any stage
3. Enter your Anthropic API key — it's stored only in that browser's localStorage
4. The key persists until the browser data is cleared

### Getting an API key

1. Go to [console.anthropic.com](https://console.anthropic.com)
2. Create a free account
3. Go to **API Keys → Create Key**
4. Copy the key (starts with `sk-ant-`)

> **Cost:** The app uses `claude-sonnet-4-20250514`. Each AI analysis costs roughly $0.01–0.03. A full user test session with all AI features costs under $0.10.

---

## User test checklist

Before each test session:
- [ ] Set API key on the test device
- [ ] Clear localStorage if re-using a device: DevTools → Application → Local Storage → Clear
- [ ] The onboarding screen shows on first visit — don't skip it, it's part of the test
- [ ] Test the complete flow: Onboarding → Wizard → Add property → All 6 stages

Key flows to observe:
- [ ] Wizard completion (10 questions, one at a time)
- [ ] Adding a new property from the home screen
- [ ] Viewing checklist during a "virtual viewing"
- [ ] Property evaluator scoring (does the score make sense?)
- [ ] AI BRF analysis in Stage 4
- [ ] Bid strategy in Stage 5
- [ ] Export backup

---

## Data & privacy

All user data is stored in **browser localStorage only** — nothing is sent to any server except direct API calls to Anthropic when AI features are used. There is no account, no database, no tracking.

---

## Tech stack

Single-file HTML app — no framework, no build step, no dependencies except:
- Google Fonts (Playfair Display, DM Sans) — loaded from CDN
- Anthropic API — only when AI features are used

---

*Prototype v2.0 · Built with Claude Code*
