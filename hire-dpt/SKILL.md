---
name: hire-dpt
description: >
  Write job ads, outreach messages, interview guides, and recruiting plans for hiring a Doctor of Physical Therapy (DPT) at a private practice PT clinic. Use this skill any time the user wants to recruit, attract, or hire a physical therapist — including requests like "write a PT job ad," "help me recruit a DPT," "create outreach for a physical therapist position," "what should I say on LinkedIn to find a PT," "help me write interview questions for a physical therapist," "improve my job posting," "build a 90-day hiring plan," or "create a candidate scorecard." Applies to all PT practice types: orthopedic, sports, pelvic health, neuro, cash-pay, and multi-location. Always trigger this skill when the output involves recruiting or hiring a physical therapist, even if the request is casual.
---

# Hiring a DPT — Private Practice Recruiting Skill

## Purpose
Produce high-converting DPT recruiting assets customized to this specific practice: job ads, direct outreach, LinkedIn posts, email sequences, interview guides, candidate scorecards, and 90-day recruitment plans.

---

## Step 1: Load or Build the Practice Profile

**Every time this skill runs, do this first.** Read `~/.claude/practice-profile.md`.

### If the file does not exist — run Core Intake

Say this to the user:

> "Before I write anything, I need to learn about your practice. This takes about 3 minutes and I'll save your answers so you never have to repeat yourself — for this skill and any others you add down the road."

Ask questions in groups, one group at a time. Wait for answers before moving to the next group.

**Group 1: The Basics**
1. What is your practice name?
2. What is your name?
3. What city and state are you in? How many locations do you have?
4. What type of PT do you primarily practice? (orthopedic, sports, pelvic health, neuro, cash-pay, mixed)

**Group 2: Culture and Values**
5. How would your current staff describe working there in three words?
6. What are your core values, formal or informal? If you haven't defined them, answer this instead: what do you look for in every hire, no matter the role?
7. What is one thing about your practice that you are genuinely proud of that most PT clinics cannot say?

**Group 3: Size and Context**
8. How many PTs are currently on staff?
9. What is your website URL? (optional)

After collecting all answers, write `~/.claude/practice-profile.md` with this structure:

```
# Practice Profile

## Core
- Practice name: [answer]
- Owner: [answer]
- Location(s): [answer]
- Specialties: [answer]
- Staff size (PTs): [answer]
- Culture descriptors: [answer]
- Core values: [answer]
- Key differentiator: [answer]
- Website: [answer]
- Last updated: [date]
```

Then immediately proceed to Hiring Intake below.

### If the file exists

Check whether a `## Hiring` section is present and populated.

- If yes: skip to Step 2 and produce output.
- If no: tell the user "I have your practice profile on file. A few quick hiring-specific questions and I will get started," then run Hiring Intake below.

---

## Hiring Intake

Ask these questions. If the user is in a hurry, let them skip any question marked (optional).

1. What role are you hiring for? (title, full-time or part-time)
2. Is this a backfill, a growth hire, or succession planning?
3. What is your compensation range? Base salary plus bonus if applicable. (optional, but unlocks better copy)
4. What are your differentiators as an employer? These are the reasons a strong PT candidate would choose you over another offer. List as many as apply.

   Present this example to help them think it through:

   > Here is what a well-differentiated practice looks like. Madden and Gilbert PT in Central PA leads with:
   > - COMT (Certified Orthopedic Manual Therapy) training covered 100% within two years
   > - 60 visits per week at 40-minute sessions — well below the industry burnout threshold
   > - No weekend hours, ever
   > - Clear career ladder: staff PT to clinical director to potential equity
   > - Open-book financials and a production bonus
   > - Daily mentorship from FAAOMPT-credentialed clinicians
   > - Advanced technology: LightForce laser, RunDNA, vestibular program
   > - Six locations, therapist-led culture
   >
   > Think about your practice from a clinician's point of view. What do you offer that most clinics in your area do not? Consider: schedule and work-life balance, mentorship and training, productivity expectations, career growth, compensation structure, specialties and technology, culture, and location.
   >
   > List your differentiators here — even rough notes are fine. We will sharpen them together.

   Take whatever they give and use it. If they list only two or three things, that is enough to work with.

5. What is your productivity standard? Visits per week, session length.
6. Do you offer any advanced training or certifications? Examples: COMT, dry needling, Pilates, running analysis, vestibular.
7. How urgent is this hire? (ASAP, within 90 days, or planning ahead)

Append to `~/.claude/practice-profile.md`:

```
## Hiring
- Current opening: [role, FT/PT]
- Hire type: [backfill/growth/succession]
- Comp range: [answer or not provided]
- Top differentiators: [answer]
- Productivity standard: [visits/week, session length]
- Advanced training/certs: [answer]
- Urgency: [answer]
- Last updated: [date]
```

---

## Step 2: Produce Output

Use the practice profile to fill every variable. Never use placeholder text or generic language. Every asset should be specific to this practice.

Determine what the user needs and deliver it:

| Request | Output |
|---|---|
| "Write a job ad" | Full Indeed/LinkedIn posting in direct-response format |
| "Write outreach message" | Personalized LinkedIn or email message, cold or warm |
| "Create interview questions" | Full interview guide with follow-up probes |
| "Build a scorecard" | Candidate scorecard with dimensions and 1-4 ratings |
| "Write a recruiting plan" | 90-day sprint with channels, timeline, and budget |
| "Improve my existing ad" | Rewrite with critique and rationale |
| "Write new grad outreach" | DPT program message targeting clinical coordinators |

---

## What PT Candidates Actually Want (Research-Backed)

Lead every asset with what candidates care about most, in this order:

1. **Work-life balance** — 69% of candidates will accept less pay for it
2. **Good people and a supportive supervisor** — 55% will accept less pay
3. **Reasonable productivity standards** — 52% will accept less pay
4. **Mentorship and growth** — especially critical for new grads
5. **Clear career path** — staff PT to clinical director to equity or partnership
6. **Salary** — ranks seventh; it matters, but it does not lead

Most PT job ads lead with the wrong things. Salary, job duties, and credential requirements dominate generic ads. Winning ads lead with the candidate's pain points: burnout, high-volume mills, lack of mentorship, no life outside of work.

---

## Job Ad Framework

### Headline Formula

Lead with a question or bold claim that speaks to candidate pain. Examples:
- "Ready to Master Manual Therapy Without Burning Out?"
- "Physical Therapist Who Values Real Relationships Over High Volume?"
- "What If Your Clinic Invested in You, Not Just Your Productivity Numbers?"

Write a headline specific to this practice's top differentiator. Do not use generic headlines.

### Ad Structure (follow this order)

1. **Hook** — Candidate pain point plus the promise this practice delivers
2. **Who We're Looking For** — Two to three questions the ideal candidate answers "yes" to
3. **Why Clinicians Join Us** — Lead with work-life balance, mentorship, growth; not salary
4. **What You'll Do** — Brief, outcome-focused; not a laundry list of duties
5. **What You'll Get** — Benefits, advanced training, bonus structure, career path
6. **Our Story and Culture** — Authentic and specific; include staff quotes if available
7. **Who Should Not Apply** — Optional but powerful filter (high-volume chaser, clock-puncher)
8. **Call to Action** — Two to three application questions, not just "submit your resume"

### Sample Application Questions (pick two or three)
- "Why are you considering a change from your current position?"
- "What does the ideal clinical environment look like for you?"
- "Describe a patient case where you got an outcome you're proud of."
- "What drew you to manual therapy?"

### Quality Check Before Delivering Any Job Ad

Before outputting, verify all four:
- Does the headline speak to candidate pain, not company needs?
- Does the copy include at least one specific number (visits per week, session length, etc.)?
- Have the phrases "competitive salary," "fast-paced environment," and "dynamic team" been removed?
- Would the wrong candidate know to self-select out?

---

## Outreach Message Templates

### Cold Outreach to a Licensed PT (LinkedIn or Email)

```
Subject: [Name]: Opportunity at [Practice Name] in [City]

Hi [Name],

I came across your profile and wanted to reach out personally. We are a [X]-location [specialty] PT practice in [City] with a strong reputation for [top differentiator in one phrase].

We are growing, and we are selective. We are not looking for high-volume throughput. We are looking for clinicians who want to get really good.

If you are even passively curious about what a different environment looks like, I would love a 15-minute conversation. No pressure at all.

[Owner Name]
[Practice Name]
[Phone or email]
```

### Passive Candidate Outreach on LinkedIn

Lead with the outcome (mastery, mentorship, career growth), not the open position. Ask one question. Keep it under 150 words. Follow up once after five to seven days if no response.

### New Grad Outreach (DPT Programs)

Target clinical coordinators at accredited DPT programs near the practice. Lead with a site visit offer, guest lecture opportunity, or clinical affiliation — not a job pitch. Program relationships produce candidates year after year.

---

## Recruiting Channels (Priority Order)

1. **State-licensed PT list by zip code** — Available for purchase; use for direct mail and email outreach to PTs within commute range
2. **DPT program partnerships** — Build relationships with clinical coordinators at regional accredited programs
3. **LinkedIn** — Best for passive candidates; personal outreach from the owner outperforms job postings
4. **Indeed** — High volume, lower signal; optimize the headline and the first three lines (what shows in the preview)
5. **PT-specific boards** — PTJobs.com, APTA Career Center, state chapter job boards
6. **Referrals** — Highest quality candidates; offer a referral bonus and ask current staff directly and explicitly

---

## Interview Process

Based on the "Who" methodology by Geoff Smart and Randy Street.

### Four Steps

1. **Screening Call (15 min)** — Baseline fit, logistics, licensure status, and why they are looking
2. **Focused Interview (60 min)** — Walk through career chronologically. For each role ask: What were you hired to do? What did you accomplish? What would your supervisor say about you? Why did you leave?
3. **Skills Interview (30 to 45 min)** — Clinical scenario discussion; manual therapy demonstration if applicable
4. **Reference Calls (30 min each, three references)** — Ask: "In what environment does this person do their best work? Their worst work?" and "Would you hire them again?"

### Red Flags

- Negative about every past employer
- Vague or evasive about patient outcomes
- Prioritizes schedule over clinical development
- Cannot name a mentor or someone they learned from
- Answers in the interview do not match what references say

---

## Candidate Scorecard

Rate each dimension 1 to 4. (1 = no evidence, 4 = strong evidence)

| Dimension | What to Look For |
|---|---|
| Curiosity and Growth Mindset | Asks good questions, names books or courses, credits mentors |
| Insistence on Outcomes | Specific patient success stories, intolerance of clinical plateaus |
| Team Player | Describes lifting others up, references team wins over personal wins |
| Clinical Motivation | Hands-on preference, interest in continued training and specialization |
| Communication | Clear and patient-centered language; confident without being arrogant |
| Coachability | Responds positively to feedback examples; no defensiveness |
| Culture Fit | Seems like someone the team would genuinely enjoy working with |

**Hiring bar:** No A-player should score below 3 in any category. Do not hire on "potential" for core values — they are either there or they are not.

Customize dimension names and descriptions to match the practice's core values from the practice profile.

---

## 90-Day Recruitment Sprint

### Phase 1: Days 1 to 30 — Build the Pipeline
- Pull state-licensed PT list filtered to a 30-minute commute radius
- Send personalized outreach to 200 or more candidates via email and LinkedIn
- Contact clinical coordinators at regional DPT programs
- Post to Indeed, APTA Career Center, LinkedIn Jobs, and state PT board job board

### Phase 2: Days 31 to 60 — Drive Engagement
- Follow up with non-responders one time only
- Host a clinic open house or virtual info session for DPT students
- Ask every current PT for one referral — make it easy and offer an incentive
- A/B test two different job ad headlines on Indeed

### Phase 3: Days 61 to 90 — Select and Close
- Run all active candidates through the four-step interview process
- Complete three reference checks on each finalist
- Extend offers with a clear start date and a written 90-day onboarding plan

### Sample Budget ($15,000 to $20,000 total)
- Direct outreach, list purchase, postage, tools: $3,000
- Job board advertising: $3,000
- Sign-on bonus or relocation assistance: $5,000 to $8,000
- Internal referral bonus: $2,000
- DPT program partnerships and events: $2,000

---

## Style Rules for All Output

- Tone: Warm, direct, no corporate jargon
- Voice: Speaks to the candidate as a peer, not a subordinate
- Specificity beats vagueness: "60 visits per week at 40-minute sessions" beats "reasonable caseload"
- Authentic over polished: real numbers, real names, real outcomes
- Always lead with what is in it for the candidate
- Never use: "competitive salary," "fast-paced environment," "dynamic team," or "we are a family"

---

## Appendix: Example of a Well-Differentiated Practice

*Reference only. Do not use this content for any practice other than Madden and Gilbert Physical Therapy.*

**Practice:** Madden and Gilbert Physical Therapy, Central PA, six locations

**Differentiators ranked by candidate priority:**
- Mentorship: daily access to experienced clinicians; FAAOMPT-credentialed experts on staff
- COMT training: Certified Orthopedic Manual Therapy covered 100% within two years
- Reasonable productivity: 60 visits per week at 40-minute sessions
- No weekend hours
- Career ladder: staff PT to clinical director to potential equity or partnership
- Open-book financials and production bonus system
- Full benefits: health, dental, PTO, 401K, continuing education stipend
- Advanced technology: LightForce laser, RunDNA, vestibular, Parkinson's program
- Six locations, 100-plus staff, therapist-led culture

**Core values:** Beginner's Mind, Insistence on Outcomes, Team Player
