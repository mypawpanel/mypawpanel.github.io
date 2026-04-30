# MEMORY.md — Bobby's Long-Term Memory

Last consolidated: 2026-04-30

---

## Who I Am

- Name: **Bobby** 🎩
- Named by Weijian on 2026-04-18, first session
- Vibe: casual, direct, opinionated when useful
- Running on: OpenClaw, Telegram (DM), WeijianPC (WSL2, Singapore)

---

## Who Weijian Is

- **Full name:** Weijian Yeo
- **Timezone:** Asia/Singapore (GMT+8)
- **Reaches me via:** Telegram DM (primary), "New business ideas" group chat (set up Apr 19)
- **Work:** ExxonMobil, Polyethylene Market Development Manager, South Asia Pacific (India, SEA, Oceania)
- **Team:** India, Singapore, Malaysia, Indonesia, Vietnam
- **Travel:** ~1–2 weeks/month overseas
- **First time using an AI assistant** (started Apr 18, 2026)
- **Prefers:** Casual tone, concise answers, no corporate speak
- **Pets:** Soju (female mini Pomeranian, born Jan 2020), Moutai (female Chow Chow, born Dec 2021)
- **Vet:** Mount Pleasant Vet, East Coast branch — transactional relationship only
- **API:** Anthropic direct keys (Sonnet 4.6 default, Opus for heavy research)

---

## Active Projects

### 1. Daily PE Market Brief (RUNNING ✅)
- Cron job ID: `3ce0186e-55ce-4d70-a6c8-4bb8bf99b8fc`
- Schedule: 8am SGT daily (every day incl weekends)
- Model: Sonnet 4.6
- Timeout: 600s
- Delivers to: Telegram chat 8571161660
- Cost: ~$0.16/brief, ~$4.76/month — very cheap, not the token burn issue

**Brief scope (15 sections):**
1. TL;DR
2. Upstream: Feedstock & Crude
3. PE Resin Prices & Supply
4. Asia-Pacific Cracker Monitor (standing)
5. China PE Export Monitor (standing, incl. active VAT rebate watch)
6. Supply Side: Producers & Capacity
7. Converter & Processor Landscape
8. Brand Owner & Packaging Trends
9. Waste, Recycling & Regulatory Policy
10. End Consumer & Macro Signals
11. Agricultural Film & Seasonal Cycles
12. Shipping & Freight
13. Regional Demand Intelligence (India/SEA/Oceania)
14. What to Watch This Week
15. ICIS Pull List

**Key brief rules:**
- Past 7 days only; ⚡ [24h] tag for last 24h items
- → causal chain notation required throughout
- NO hallucination: only name companies with verified sources + date
- NO false causality: don't link events from different timeframes
- Price sanity checks enforced (ranges in cron prompt)
- Omit sections with nothing fresh
- Monitor SET/Bursa/BSE/IDX/Tadawul exchange filings for plant news

**Known brief issues fixed:**
- Hallucinated company names (Parke Products, Lahori Zeera price hikes) — added no-hallucination rule
- False causality (Dabur Jan announcement grouped with Apr Iran events) — added date-stamping rule
- Wrong price units (RIL HDPE INR 4,000/MT) — added price sanity checks
- SKU downsizing → less PE (wrong) — correct is more PE per kg of product
- China coal-based cost ranking was wrong pre-chart; corrected after Weijian shared feedstock cost chart showing naphtha up ~95% vs coal up ~5% since conflict began

### 2. Pet Health Analytics (RESEARCH DONE, IDEATION ONGOING)
- Research report saved: `/home/yeowj1985/.openclaw/workspace/research/pet-health-analytics-scan.md`
- Key findings:
  - No direct at-home pet diagnostics competitor in SG yet
  - Hero test: allergy/skin sensitivity panel (hair-based), SGD 120-200
  - Pawllergy (SG competitor) sells at S$209, currently sold out — strong demand signal
  - ZumVet cautionary tale: raised S$4.8M, shut abruptly late 2024 — subscription tele-vet model failed on vet staffing costs
  - Don't build subscription tele-vet; referral model is safer
  - Lab partners: AnimalBiome, Orivet, i-screen Pets AU, Hemopet, IDEXX
  - MVP budget: SGD 4,000-15,000
  - Regulatory: AVS allows wellness panels if not claiming "diagnosis"; need vet to review report template
  - Mount Pleasant Vet (East Coast) is logical first vet partner
  - Soju and Moutai = authentic brand story, seed with their real test results
  - New Veterinary Council legislation passed Apr 8, 2026 — rules tightening
- Option 2 (no vet partner): refer to ZumVet or similar for interpretation
- Status: Weijian wants to park ideation in "Pet Health Analytics" group chat (not yet working — needs gateway restart to allowlist)

### 3. Drop-shipping
- Low priority — only if genuinely low effort
- Suggested: tie to pet brand merch if pet business takes off

---

## Infrastructure & Config

### Model routing
- Default: `anthropic/claude-sonnet-4-6` (alias: `sonnet`)
- Heavy research/strategy: `anthropic/claude-opus-4-7` (alias: `opus`)
- Set 2026-04-18

### Telegram group chats
- "New business ideas" — chat ID: `-1003762725975`, working ✅
  - requireMention: false (allowlisted)
- "Pet Health Analytics" — NOT YET WORKING
  - Needs: `openclaw gateway restart` from Weijian's terminal to apply allowlist config
  - Config already set, just needs restart

### Gateway restart
- Cannot be done by Bobby (kills parent process)
- Must be run by Weijian from terminal: `openclaw gateway restart`

### Cost management
- Token burn issue: long chat sessions load full history each turn
- Plan: **weekly session refresh** (every Sunday/Monday)
- Bobby to: consolidate memory to MEMORY.md → flag Weijian → start fresh session
- Daily brief: only ~$0.16/run, not the issue
- Sub-agent research scans: use sparingly, only for real decisions

---

## PE Market Intelligence — Key Knowledge Built Up

### Weijian's value chain focus
- **Consumer packaging**: packed food, home care, personal care
- **Industrial packaging**: heavy duty sacks, collation shrink (beverages), stretch hood, stretch films (pallet stabilisation)
- Full value chain monitoring: feedstock → PE resin → converters → brand owners → machinery OEMs → end consumers → macro

### Key PE market context (as of late April 2026)
- **Middle East conflict** is dominant market driver since ~Feb 28, 2026
- Strait of Hormuz effectively closed; US naval blockade of Iranian ports
- ME PE supply ~12-18 months from full restoration (ICIS estimate)
- Borouge Al Ruwais (UAE, 1.4M tonnes PE) offline since Apr 5
- SCC/SCG Long Son Petrochemicals (LSP) Vietnam suspending mid-May 2026 (feedstock constraints)
- Shell-CNOOC Nanhai cracker China closed March 6
- LG Chem Korea cut to 60% utilisation

### China PE cost curve (post-conflict)
- Naphtha feedstock cost up ~95% since conflict; coal up only ~5%
- **Revised ranking: ethane (cheapest) < coal < naphtha (most expensive)**
- China capacity: ~65% naphtha, ~20% coal (MTO), ~10-15% ethane
- Total capacity: ~45M tonnes in 2026
- Chinese naphtha-based exports to SEA: selling ~$200-400/MT below cash cost — fixed cost absorption strategy, not profitable
- Coal-based: may be marginally cash-covering at current coal prices
- PE export VAT rebate NOT removed in April 1, 2026 round (PVC/polyols affected, not PE) — ACTIVE WATCH

### Key sources to monitor
- Polymerupdate, ChemAnalyst, Reuters, ChemOrbis free, Plastics News, Business Standard, Economic Times
- Nation Thailand, Kaohoon International (for SCC/SET filings)
- SET, Bursa, BSE, IDX, Tadawul exchange filings
- SunSirs (China PE)
- ADB, IMF, World Bank for macro

### Macro outlook (Apr 2026)
- ADB: Asia-Pacific growth slowing to 5.1% (Middle East conflict impact)
- World Bank: South Asia slowing to 6.3% (from 7.0% in 2025)
- IMF: global growth cut to 3.1%
- No recession base case but tail risk if Hormuz closure extends to 2027

### Kharif/Rabi — India agricultural seasons
- Kharif: sown June-July, harvested Sep-Oct (rice, cotton, soybean) — agri film demand peaks May-July
- Rabi: sown Oct-Nov, harvested Mar-Apr (wheat, chickpeas) — agri film + HDPE sack demand Oct-Nov
- Currently (Apr-May 2026): Kharif prep window = active agri film demand period

### Stretch film vs flexible packaging profitability
- Stretch film structurally lower margin due to:
  1. Performance tolerance — compensate with more wraps, lower quality bar
  2. Fragmented value chain — no quality discipline, low claims risk
  3. $/tonne buying behaviour — obscures cost-in-use, commoditises market

---

## Lessons Learned

- Brief hallucinations are a real risk — always verify company-specific claims before treating as fact
- Date-stamping every event is critical to prevent false causality in analysis
- Gateway restart must come from Weijian's terminal, not from Bobby
- Sub-agent research scans can be expensive; use sparingly
- ICIS has the best data but can't be automated (login/ToS); flag specific ICIS reports for Weijian to check manually
- Price sanity checks are necessary — AI will generate plausible but wildly wrong numbers if not constrained
- Weijian's industry network surfaces signals (like LSP suspension document) before public news — the brief complements but doesn't replace human intel

---

## Reminders / One-off Tasks

- Weekly session refresh: consolidate memory Sunday/Monday, start fresh chat
- "Pet Health Analytics" group chat: needs gateway restart to activate
- Cost review (originally week 2): done — daily brief cheap, chat history is the cost driver
