---
name: evidence-interview
description: Conducts a step-by-step evidence interview before improving a resume or cover letter. Use when the user wants career material tailored to a role, needs help discovering relevant achievements or AI experience, or has conflicting or incomplete resume claims.
---

# Evidence interview

Improve the existing resume through an interactive interview, then deliver a reviewed draft. Work from the user's actual experience. A desired technology, job-ad requirement, or market trend is a learning gap until the user supplies experience that supports it. Confirmed means user-attested, not independently verified.

## Start from what exists

Read the selected resume and the job requirements already provided. Reuse the user's saved preferences and enabled Knowledge only when that context is authorized. Keep the source document unchanged while drafting a tailored copy. A LinkedIn export or pasted profile is an additional source, not permission to scrape or edit LinkedIn.

Offer quick or deep mode when the preference is unknown and a choice would help. Quick mode confirms the target and source accuracy, then asks only high-value follow-ups. Deep mode explores responsibilities, outcomes, measurements, chronology, qualifications, and relevant AI work. Respect an already-stated preference and any instruction to proceed with available information.

Ask one focused question at a time. Use a quote from the user's source to make a question concrete. Do not ask again for an answer already given. Support **skip**, **exclude from the draft**, and **keep private**. Do not persist the content of a private answer in a connected interview or pass it to another agent. An optional unanswered question is not a reason to prolong the interview indefinitely.

## Establish evidence, then branch

1. Confirm target role, level, audience, language, and submission constraints from available context. Separate aspirations from titles already held.
2. Identify corrections or contradictions in the sources. Preserve exact employers, dates, qualifications, and credential status. Confirming a report of an error does not mean the source is correct. Obtain an explicit resolution for the current source versions: reviewed and correct, changes still needed, or an entire source excluded from drafting. Correct and refresh disputed sources, or honor the explicit exclusion; do not silently choose between conflicting versions.
3. Ask about a relevant contribution. Record personal responsibility and whether it happened in employment, freelance work, a project, a course, a lab, or volunteering.
4. If there is substantive work to include, ask what changed. In deep mode, ask how the result was measured and what the user contributed. Qualitative outcomes are useful. Never pressure the user to invent a number; retain estimates as estimates or omit an uncertain metric.
5. When relevant, ask about existing AI experience. Start with the user's own tools and work. Useful prompts include coding assistants, LLM integration, retrieval, evaluation, automation, model deployment, latency/cost, data handling, and human review. Ask only the applicable follow-up; a tutorial stays a tutorial. Never add a fashionable stack merely because a posting mentions it.
6. Keep a compact evidence ledger: source/quote, claim, experience context, certainty, and inclusion decision. Unknown or conflicting claims that would enter the draft must be resolved or excluded. Gaps remain separate from experience.

## Research, draft, and review

For market tailoring, research the target role, geography, level, and work arrangement using dated employer postings and official technical sources. Search by role and skills, without private resume details. State the cohort size, retrieval dates, salary currency/period, and limits. Separate market frequency from evidence about this candidate. Do not promise an ATS score, interview, salary, or offer.

Use parallel research, drafting, and factual review agents when the user authorized parallel work. Give each the minimum needed context and separate responsibilities. Only the coordinating agent may propose saved changes. The critic checks every number, date, credential, tool, and seniority claim against the evidence ledger. Review findings can trigger another focused question or a smaller truthful claim.

Return a resume draft and, if needed, a concise role-specific cover letter using the same confirmed evidence. Keep coaching preferences, salary constraints, and source-correction notes out of employer-facing prose. Include a change summary, omitted uncertainties, and learning gaps separately. Ask for review of the concrete version when approval is needed. An approved interview is permission to use its evidence in drafting; it does not authorize publishing, account edits, or applications.

## Connected interview workflow

Use the tools actually exposed by the user's chosen server. If evidence-interview operations are present, read [the connected workflow](references/connected-workflow.md). Otherwise keep the interview in the conversation and use existing resume reading, tailoring, Knowledge, and export tools; do not claim that a persistent interview was saved.

Before saving a requested change, re-read its current revision and preserve concurrent edits. Keep exact source versions and user confirmations attached to the draft. If a source or answer changes, the old approval no longer applies. Report a save or export only after tool success and validate the exported document before claiming its layout or parsing passed.
