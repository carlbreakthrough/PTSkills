# PTSkills — Claude Code Skills for Physical Therapy Practice Owners

## What This Project Is

A library of Claude Code skills built for private-practice PT owners. Each skill is a standalone `.skill` file that installs into a customer's Claude Code and produces high-quality, practice-specific output without them having to re-explain their context every time.

Skills are distributed to Breakthrough customers. They should work for any PT practice type: orthopedic, sports, pelvic health, neuro, cash-pay, and multi-location.

---

## The Practice Profile System

The most important architectural decision in this project: all skills share a single persistent file at `~/.claude/practice-profile.md` on the customer's machine.

This file is the source of truth for everything practice-specific. Skills read it before doing anything, and write to it after collecting information the practice hasn't provided yet.

### Core Fields (universal across all skills)

Every skill must be able to read and use these fields:

```
# Practice Profile

## Core
- Practice name:
- Owner:
- Location(s):
- Specialties:
- Staff size (PTs):
- Culture descriptors:
- Core values:
- Key differentiator:
- Website:
- Last updated:
```

### Skill-Specific Sections

Each skill appends its own section under a clearly labeled header. Examples:

```
## Hiring
- Current opening:
- Hire type:
- Comp range:
- Top differentiators:
- Productivity standard:
- Advanced training/certs:
- Urgency:
- Last updated:

## Marketing
- Ideal patient profile:
- Primary referral sources:
- Marketing channels active:
- Last updated:

## Finance
- Revenue model (insurance/cash/hybrid):
- Avg visits per patient per episode:
- Last updated:
```

Only collect and write what the skill actually needs. Do not create fields speculatively.

---

## How to Build a New Skill

Follow this checklist every time:

### 1. Define the trigger

The `description:` field in the SKILL.md frontmatter is what causes Claude to auto-invoke the skill. Write it to cover all natural-language variations of the request. Be specific about PT context so it does not fire on unrelated requests.

### 2. Read the practice profile first

Every skill must open with this logic:

- Read `~/.claude/practice-profile.md`
- If the file does not exist: run Core Intake, save the file, then run skill-specific intake
- If the file exists but is missing the skill's section: skip core intake, run only skill-specific intake
- If the file is fully populated for this skill: skip all intake and go straight to output

Never ask questions the profile already answers. Never re-run intake unless the user explicitly asks to update their profile.

### 3. Run Core Intake (only if profile does not exist)

Use this exact flow — conversational, grouped, one group at a time:

**Group 1: The Basics**
- Practice name
- Owner name
- City, state, number of locations
- Practice type and specialties

**Group 2: Culture and Values**
- How staff would describe working there in three words
- Core values (formal or informal)
- One thing genuinely differentiated about the practice

**Group 3: Size and Context**
- Number of PTs on staff
- Website (optional)

Save answers to `~/.claude/practice-profile.md` under `## Core`.

### 4. Run Skill-Specific Intake

Collect only the fields this skill needs that are not already in the profile. Ask in a natural, grouped way. Mark optional questions clearly so time-pressed owners can skip them.

Append answers to `~/.claude/practice-profile.md` under the skill's own section header.

### 5. Produce output using profile data only

Every variable in the output must be filled from the practice profile. No placeholder text. No generic examples. No defaulting to example practices.

### 6. Quality check before delivering

Include a self-check block the skill runs before outputting anything. At minimum: does the output use specific data from the profile? Does it avoid the banned phrases list?

---

## Banned Phrases

Never appear in any output from any skill:

- "competitive salary"
- "fast-paced environment"
- "dynamic team"
- "we are a family"
- "passionate about"
- "results-driven"
- "synergy" or any variant

---

## Voice and Tone (for all skills)

Breakthrough's customers are private-practice owners, not enterprise HR teams. They are busy, they are operators, and they have low patience for corporate language.

- Warm, direct, peer-to-peer
- Specific numbers over vague descriptors ("60 visits per week at 40-minute sessions" not "reasonable caseload")
- Authentic over polished
- Lead with what is in it for the reader (candidate, patient, referral source) not what the practice wants
- No em dashes in any output

---

## Skill File Structure

Each skill lives in its own subdirectory:

```
PTSkills/
  CLAUDE.md
  hire-dpt/
    SKILL.md
  [next-skill]/
    SKILL.md
```

### Packaging for Distribution

To produce a `.skill` file ready to send to customers:

```bash
cd PTSkills
zip -r hire-dpt.skill hire-dpt/
```

The `.skill` file is a zip archive. The customer installs it into Claude Code. That is the entire distribution mechanism.

Output packaged `.skill` files to `PTSkills/dist/` (create the folder when first needed):

```
PTSkills/
  dist/
    hire-dpt.skill
```

---

## Skills Built So Far

| Skill | File | Status | Description |
|---|---|---|---|
| hire-dpt | hire-dpt/SKILL.md | Shipped v1 | Recruiting assets for hiring a DPT |

---

## Planned Skills (not yet built)

Ideas for future skills. Update this list as skills are confirmed or ruled out.

- **market-pt** — patient marketing: referral outreach, Google Business optimization, email campaigns
- **retain-pt-staff** — staff retention: stay interviews, culture diagnostics, compensation benchmarking
- **onboard-pt** — new hire onboarding plan generator (30/60/90 days)
- **pt-job-offer** — verbal offer script and offer letter language
- **pt-profile-update** — standalone skill to update the practice profile without triggering a specific recruiting or marketing task

---

## The Shared Onboarding Skill (future)

Once multiple skills are in use, consider building a `/pt-onboard` skill that runs Core Intake plus all known skill-specific sections in one session. This fills the practice profile completely so every subsequent skill skips intake entirely.

Build this after at least two skills are in production and you know which fields actually matter across skills. Do not build it speculatively.

---

## Example Practice Reference

Madden and Gilbert Physical Therapy (Central PA, six locations) is the reference practice used during development. It should appear only in appendices labeled "reference only." It must never be used as a default for any other practice's output.

Use it to show what a well-differentiated practice profile looks like, not as content.
