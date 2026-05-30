# Prompt Logic & Documentation

> This document explains the prompt engineering decisions behind the Notion UGC Ad Content Pack.

---

## Why UGC-Style Ads?

UGC (User Generated Content) ads outperform traditional polished ads because:
- They feel authentic — like a real person's opinion
- They match the native format of Instagram Reels and YouTube Shorts
- Viewers don't immediately recognise them as ads (lower skip rate)
- They build trust faster than brand-produced content

The goal of each prompt was to generate content that sounds like a **real user talking**, not a marketing team writing.

---

## Prompt Design Decisions

### 1. Using Bracketed Variables `[like this]`

Every prompt uses `[bracketed placeholders]` instead of hardcoded values.

**Why:** This makes each prompt a reusable template. The same hook generator prompt works for Notion, Canva, a local gym, or a skincare brand — just swap the variable.

**Example:**
```
For [Product: Notion] → replace with [Product: Canva] or [Product: Your Salon Name]
```

---

### 2. Explicit Tone Instructions

Each prompt includes negative constraints alongside positive ones.

**Included tone rules:**
- "No marketing buzzwords"
- "No exclamation marks"
- "No emojis"
- "Sound like a real person, not a brand"

**Why:** LLMs default to enthusiastic marketing language without these guardrails. Explicit negative instructions prevent the model from slipping into ad-speak.

---

### 3. The Problem → Solution → CTA Framework

All scripts follow this 3-part structure:

| Part | Purpose | Length |
|------|---------|--------|
| Hook | Stop the scroll — relatable pain or POV | 1 sentence |
| Problem | Expand the pain — make viewer feel seen | 2–3 sentences |
| Solution | Show how product solves it — no jargon | 2–3 sentences |
| CTA | Soft ask — not pushy | 1 sentence |

**Why this works:** It mirrors how people naturally recommend products to friends. It leads with empathy (problem) before introducing the product (solution).

---

### 4. Platform-Specific Adaptation (Prompt 03)

Different platforms need different treatments:

| Platform | Audience | Tone | Length |
|----------|---------|------|--------|
| Instagram Reel | 18–30, visual-first | Casual, fast | 15–45 sec |
| YouTube Shorts | 18–35, intent-based | Slightly more detailed | 30–60 sec |
| Facebook Ad | 25–45, text-tolerant | Warmer, benefit-first | 45–90 sec |

Prompt 03 was designed specifically to take a script written for one platform and adapt it for another without losing the UGC feel.

---

### 5. Audience Segmentation

Three distinct audience segments were targeted:

| Segment | Pain Point | Notion Angle |
|---------|-----------|-------------|
| Freelancers | Too many tools, no system | All-in-one workspace |
| Remote teams | Scattered tasks, missed deadlines | Team wiki + project tracker |
| Students | No structure, overwhelmed | Free student plan + templates |

Each script addresses a different pain — even though the product is the same. This demonstrates how a single product can have multiple UGC angles depending on who you're targeting.

---

## What I Learned

1. **Specificity beats generality** — "I had sticky notes on my monitor" converts better than "I was disorganised"
2. **Negative constraints are as important as positive ones** — telling the AI what NOT to do is crucial for UGC tone
3. **Variables make prompts scalable** — the same prompt system can be sold to any brand
4. **Platform matters** — the same script needs different pacing for Instagram vs Facebook

---

## How to Reuse This System for Any Brand

1. Open `prompts/prompts.md`
2. Replace `[Product: Notion]` with your chosen product
3. Update `[Target audience]` based on who the brand sells to
4. Change `[Platform]` to match where the ad will run
5. Run Prompt 01 → get hooks, run Prompt 02 → get scripts
6. Use Prompt 03 to adapt across platforms

This system can generate a full UGC content pack for any brand in under 30 minutes.

---

*Part of FUTURE_PE_02 — Future Interns Prompt Engineering Track*
