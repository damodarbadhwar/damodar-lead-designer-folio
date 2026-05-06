---
name: tailor-application
description: Tailors a job application for Damodar Badhwar (Lead Product Designer) by producing a customized cover letter and targeted resume bullet swaps based on a pasted job description. Use this skill whenever Damodar pastes a job description (JD) along with phrases like "cover letter and resume", "tailor for this JD", "tailor my application", "rewrite for this role", "apply to this", or any signal that he's preparing application materials for a specific job — even if he doesn't say the exact trigger phrase. Do NOT use this skill for generic cover-letter writing requests that aren't tied to a specific pasted JD.
---

# Tailor Application — Damodar Badhwar

This skill produces tailored job application materials for Damodar Badhwar, a Lead / Senior Product Designer with 10+ years of experience. It takes a pasted job description and returns a cover letter, resume bullet swaps, and ATS keywords — all in chat, copy-paste ready.

## When to use

Trigger when Damodar pastes a job description and signals he wants application materials. Common phrases: "cover letter and resume", "tailor my application", "rewrite for this JD", "apply to this", or just a JD paste with an expectation of output. If unclear, ask once: "Want the full tailored set (cover letter + bullets + keywords)?"

## What to output (exact structure)

Always return these four blocks in this order. No preamble, no closing commentary. Damodar is copy-pasting these directly.

### 1. Role fit (3 lines max)

Three short lines that explain why he matches. This is a sanity check before he sends — not part of the application. Keep it factual: which signature win maps to which JD requirement.

### 2. Cover letter (~150 words)

A formal, copy-paste-ready cover letter. Rules:

- **Tone:** Formal. No casual phrases. No emojis. No "I'm excited to" openers — those are weak.
- **Length:** ~150 words, four short paragraphs.
- **Opening:** State the role and one concrete reason he's a strong fit. Lead with a metric where possible.
- **Middle paragraphs (1-2):** Map 2-3 signature wins to specific JD requirements. Use the company's language from the JD (their words for users, problems, products).
- **Close:** Reference the folio, signal availability, sign off.
- **Sign-off:** Always end with "Sincerely, Damodar Badhwar" followed by contact line: `damodarbadhwar@gmail.com  •  +91 9870526099  •  https://damodar-work.netlify.app/`
- **Never invent metrics, employers, or projects.** Only use what's in the baseline below.
- **Address line:** If a hiring manager name is in the JD, use "Dear [Name],". Otherwise, "Dear Hiring Team,".

### 3. Resume bullet swaps (OLD → NEW)

Only show bullets that actually change. Format as:

```
[Company — Role]
OLD: <existing bullet verbatim from baseline>
NEW: <rewritten bullet>
```

Rules:

- Rewrite only the bullets where the JD's language or focus area meaningfully shifts the framing. If a bullet already maps cleanly, leave it alone.
- Preserve metrics exactly. Never inflate, never round up, never invent.
- Lead bullets with the verb that matches the JD's seniority signal: "Led", "Drove", "Owned", "Architected" for senior/lead JDs; "Designed", "Shipped", "Built" for IC-leaning JDs.
- Weave in 1-2 keywords from the JD per bullet, naturally.
- Keep length similar to the original (one line, ~20-30 words).

### 4. ATS keywords (2-3)

Pull 2-3 high-signal keywords from the JD that should appear in the resume but currently don't. List them comma-separated. Skip generic terms ("design", "UX") — focus on specific frameworks, methods, domains, or tools the JD calls out repeatedly.

## Signature wins (use these as anchors)

These are the metrics Damodar wants leveraged across applications. Pick the 2-3 most relevant per JD. Never invent new ones.

- **Card Design Studio mobile redesign** (Wells Fargo) — transformed a 13-year-old desktop feature into mobile; ~30M cards customized to date.
- **Flipkart UPI** — designed end-to-end; adopted by 4M+ users.
- **Flipkart Payments page** — UX enhancements drove ~8% success rate uplift.
- **Flipkart Pay Later** — improved acquisition funnel, ~12% uplift across a 10M user base.
- **Flipkart Grocery homepage** — revamp drove ~7% increase in cart additions.

Secondary anchors (use when JD calls for them):

- **Smart Start Banking** (Wells Fargo) — Lead designer for ages 6-17 banking experience.
- **Design systems** — built foundational systems at MoveInSync (desktop + Android) and BillTrim.
- **AI-assisted workflows** — built automated pipeline to upscale legacy UI assets across 100+ pages at Wells Fargo.

## Resume baseline (verbatim)

When swapping bullets, use these as the OLD versions. These are the exact lines from Damodar's current resume.

**Wells Fargo — Sr. Product Designer (Oct '24 – Present, Bangalore)**
- Led design for Smart Start Banking (ages 6–17), guiding the overall product experience.
- Built an automated workflow to upscale legacy UI assets across 100+ pages, improving visual quality and design consistency.
- Redesigned the alerts experience to improve clarity and control.
- Led the mobile redesign of Card Design Studio, transforming a 13-year-old desktop feature into a mobile experience. ~30M incremental cards have been customized so far.

**Flipkart — Product Designer 2 (Feb '22 – Sep '24, Bangalore)**
- Designed Flipkart UPI, adopted by 4M+ users.
- Improved Payments page success rate by ~8% through UX enhancements.
- Improved Flipkart Pay Later acquisition funnel, driving ~12% uplift across a 10M user base.
- Revamped the Grocery homepage, increasing cart additions by ~7%.

**MoveInSync — Sr. UX Designer (Dec '20 – Feb '22, Bangalore)**
- Built a foundational design system for desktop and Android in collaboration with engineering.
- Designed workplace tools including desk booking, office check-in/out, visitor management, and meeting room scheduling.

**BillTrim — UX Designer (Aug '18 – Dec '20, Bangalore)**
- Designed experiences that help users detect utility overcharges and find ways to save without changing plans.
- Conducted user interviews and surveys to validate design decisions.
- Built a foundational design system to ensure product consistency.
- Created illustrations and micro-interactions for landing pages.

**Gaming Monk (parent MPL) — UX Designer (Oct '17 – Mar '18, Delhi)**
- Designed matchmaking flows, including leaderboards and tournament summaries.
- Created design guidelines for social media content.

**Addodoc Tech Pvt Ltd — Creative Designer (Jan '16 – Sep '17, Delhi)**
- Designed experiences that connect new parents with other parents and doctors for trusted advice.
- Made a video that went viral (9.7M+ views), helping us gain ~20K Facebook page likes.

## Standing facts

- **Name:** Damodar Badhwar
- **Email:** damodarbadhwar@gmail.com
- **Phone:** +91 9870526099
- **Folio URL:** https://damodar-work.netlify.app/
- **Education:** Mechanical Engineering, ABES Engineering College, Ghaziabad (2011-2015)
- **Years of experience:** 10+
- **Current title:** Sr. Product Designer (targeting Lead Product Designer roles)
- **Location:** Bangalore, India

## Tone guide — formal but not stiff

Formal does not mean robotic. Aim for the register of a strong industry letter: confident, specific, no hedging.

**Avoid:** "I am writing to express my interest", "I would love to", "I'm thrilled", "I believe I would be a great fit", "passionate", "team player", emojis, exclamation marks.

**Prefer:** Direct claims backed by metrics. Active voice. Past-tense ownership verbs. Industry-specific nouns over abstract ones.

**Example openings (good):**
- "Your search for a Lead Product Designer to own [X] aligns directly with my work at Wells Fargo, where I led the mobile redesign of Card Design Studio — a feature now responsible for ~30M customized cards."
- "I am applying for the [Role] position. At Flipkart, I designed Flipkart UPI from the ground up; today it serves 4M+ users."

**Example openings (avoid):**
- "I'm super excited to apply for this amazing role!" (casual, weak)
- "I am writing to express my keen interest in the Lead Product Designer position." (boilerplate)

## Working principles

- **Read the JD twice before writing.** First pass: what's the role really about. Second pass: what specific keywords, frameworks, or methods recur. Tailor against the second pass.
- **Mirror the JD's language.** If they say "customer", don't say "user". If they say "0-to-1", use that phrase.
- **One JD = one tailored output.** Don't try to make a generic letter that fits multiple roles.
- **If the JD is ambiguous or you're missing context** (e.g., it's a screenshot with cut-off text, or no company name), ask one targeted question before generating.
- **Never fabricate.** If a JD asks for skills Damodar doesn't have in the baseline, don't claim them. Either reframe an adjacent skill honestly or skip that requirement in the cover letter.
