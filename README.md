# Career Coach for Codex

An evidence-led resume coaching plugin: start from an existing resume, interview the user, separate demonstrated experience from learning goals, research target roles, and prepare truthful resume and cover-letter drafts.

**Status: 0.1.0, local companion application required for connected features.** This repository publishes the plugin, not the companion application's source or a hosted service. The modified companion is currently available in the maintainer's local workspace. Other users can use the evidence-interview instructions manually on pasted text; installing this plugin alone does not create the backend. Stock Reactive Resume does not provide our added evidence-interview endpoints.

## What we reused and what we added

| Platform or component | Reused | Added in this project |
| --- | --- | --- |
| OpenAI Codex | Plugin/skills execution, cloud-hosted model conversations, local executor, MCP client | Local plugin manifest, marketplace packaging, workflow instructions; no new model |
| [Reactive Resume 6.1.0](https://github.com/reactive-resume/reactive-resume/tree/8034bc43e8e101c83c99b79541ee249d3658a46e) | 32 unchanged career skills, icons, source notes and MIT license | One `evidence-interview` skill and its connected-workflow reference; 33 skills total |
| MCP / Streamable HTTP / OAuth | Standard transport and account authorization | Connection to `http://localhost:3110/mcp`; tools discovered from the actual connected server |
| GitHub | Source hosting and Git-based plugin distribution | This public marketplace repository and usage documentation |

The added interview asks focused follow-ups about contributions, dates, outcomes, experience context and relevant AI work. It supports corrections, exclusions, uncertainty and private/skipped answers. Market demand never becomes a claim that the applicant has a skill. Parallel drafting and a factual critic are used when authorized and available. Nothing promises an interview, salary or offer.

The 32 upstream skills and upstream `SOURCES.md` are reused unchanged; their source research is credited to upstream, not claimed as original work here. See [ATTRIBUTION.md](ATTRIBUTION.md).

## Install in Codex

Use a Codex installation with plugin marketplace commands and a local executor. Start the companion app first for connected use, then run:

```powershell
codex plugin marketplace add eldarush/career-coach-codex-plugin --ref main --json
codex plugin add career-coach-local@career-coach-public --json
```

Alternatively clone this repository and register its directory with `codex plugin marketplace add ./career-coach-codex-plugin --json`.

Open a new Codex chat if the skill does not appear immediately. Select **Career Coach (local)** and complete account authorization against the local app when prompted. Installation does not establish an authenticated connection. The package contains no password or API key. The localhost endpoint requires Codex to reach the same machine; it is not a remote ChatGPT-hosted endpoint.

Packaging follows the [OpenAI plugin format](https://developers.openai.com/plugins/build/plugins). This is GitHub distribution, not a claim of approval or listing in the OpenAI public directory.

## Use it step by step

1. Import your existing resume in the companion and review parsing, dates, links and section layout. You can also supply text directly for a conversation-only interview.
2. Start with: **“Use evidence-interview in deep mode. Help me tailor my existing resume to this job. Ask one question at a time, and ask about relevant AI experience without inventing skills.”** Supply your target role, geography, level, work preferences and job description.
3. Correct or exclude disputed source material. Describe what you personally did, where you did it, and the results. Estimates remain estimates; courses and personal projects remain distinct from professional work. Do not send sensitive details to a chat merely to mark them private afterward.
4. Review the evidence ledger. Connected interviews persist only when the server exposes those operations; otherwise the interview stays in the conversation. Approval applies to the current source versions and must be renewed after changes.
5. Ask: **“Research current employer requirements for my target role. Give dated sources and coverage limits. Separate missing skills from supported experience.”** Web research depends on tools available in your Codex session; this plugin does not bundle a search service.
6. Ask for a tailored draft, optional cover letter, factual review and change summary. Review before saving or exporting. Interview approval never authorizes applications or public profile edits.

For the companion's cloud drafting, connect a provider under Settings → AI connections. The app's provider key is separate from a Codex subscription. **No local AI models are started or required.** Cloud AI use can incur provider charges; no live cloud draft has been verified in the current local acceptance run.

## Companion system: separate implementation

The local application extends Reactive Resume rather than recreating its editor. Its reused stack is React, TanStack Router/Query and Vite on the web; Node.js, Hono and oRPC on the server; PostgreSQL with Drizzle, Redis and Better Auth; MCP tools; the existing AI SDK/provider framework; and Expo/React Native for the mobile client. Docker Compose runs local PostgreSQL and Redis. No mobile emulator is needed for the web workflow.

Upstream supplies accounts, resume/cover-letter editing and exports, LinkedIn member-export import, Knowledge, application tracking and offers. Added companion features include:

- Persistent evidence interviews with provenance, revision checks, source corrections, exclusions and approval invalidation.
- Dated public Greenhouse, Lever and Ashby job-board research with coverage warnings, fit constraints and conservative compensation comparison.
- Approved-evidence cloud drafting with two specialists and a critic; suggestions require review and do not automatically edit documents.
- Evidence and market dashboards plus bounded application policies, immutable reviewed packets, background queueing, deduplication, pause controls and receipt reconciliation.
- A **local employer simulator only** for application delivery tests. No live ATS submission or LinkedIn Easy Apply connector is enabled.

Those server features are not contained in this plugin repository and are not made available by installing these skills. LinkedIn support means user-provided export import, not scraping or automatic profile access. Salary ranking is a heuristic, not evidence of improved hiring outcomes.

## Local test walkthrough

On the maintainer's prepared machine, open `http://localhost:3110`, create/sign into an account, import a resume, then open Career → Evidence. Complete the interview and review the resulting evidence before approving. Next use Career → Market to inspect supported employer postings and their source dates. Use Applications to track progress.

For simulation, start the companion's `node tooling/local/employer-simulator.mjs`, create a bounded policy, review the exact document packet, and queue an attempt. Inspect its receipt and history. A confirmed simulator receipt means delivery to the local simulator, not an employer application or interview. Keep real submissions disabled during testing.

## Verification and limits

The prepared companion passed synthetic HTTP/browser checks for evidence review, account isolation, PDF packet simulation, lost-response reconciliation and packet replacement. Authenticated MCP tool discovery was tested with a scoped API key. The end-user Codex OAuth connection and a real cloud-provider drafting call remain unverified. These companion checks do not establish functionality in a fresh public clone without a backend.

Private resumes, account archives, application packets, `.env` files and credentials are excluded from this repository. Follow-up work includes separately distributing the companion and validating OAuth end to end before describing this as a turnkey public product.
