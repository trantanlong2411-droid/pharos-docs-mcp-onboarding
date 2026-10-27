# Pharos Agent Arena — Docs MCP Onboarding

**Task:** Easy · Developer Docs MCP · 50 points (+ optional video bonus)

**Status:** In progress. Two sessions documented; one confirmed onboarding obstacle; further independent documentation gaps and a practical outcome remain to be tested. This is **not yet a completed 50-point submission**.

## Task objective

Onboard to [AI.PHAROS](https://ai.pharos.xyz/) using **only the Developer Docs MCP** for documentation research, without web search or external documentation, and record:

1. A numbered log of attempted steps, exact queries to Docs MCP, and returned answers.
2. At least **three distinct**, concrete documentation gaps or failures, with the **exact question** for each.
3. A suggested fix for every gap, explaining what the docs should have said.
4. A final statement of what was actually built or run.

## Developer Docs MCP tools (reported in session 2)

Session 2 reported a remote MCP server at `https://docs.pharos.xyz/~gitbook/mcp` with these four tools:

| Tool | Reported role |
|---|---|
| `searchDocumentation` | Find relevant documentation, examples, references, and guides |
| `getPage` | Retrieve a specific page's Markdown |
| `askQuestion` | Ask natural-language questions and retrieve source-linked answers |
| `sendFeedback` | Send documentation feedback (write operation) |

**Evidence quality:** These tool names, their descriptions, and the successful `askQuestion` result are from the AI.PHAROS session's **reported tool activity** in screenshots. They are not independently re-tested by this website, and earlier and later sessions had different availability.

## Session 1 — Tool discovery blocked

**Exact user prompt (key excerpt):**
> I am completing the Pharos Agent Arena "Docs MCP Onboarding" task. I want to onboard myself to ai.pharos.xyz using ONLY the official Developer Docs MCP. … Connect to and use the Developer Docs MCP tools … list the available tools … show the exact documentation sources.

**Observed AI.PHAROS response:**
- Reported `MCP tools: 0` and "Developer Docs MCP is not available in this session".
- Attempt to run `dtcoder mcp list` reportedly denied by a security policy (`denylist pattern match`).
- No Developer Docs MCP documentation retrieved in that attempt.

**Documentation/product experience gap #1 — access and recovery visibility:**
The beginner task presumes Docs MCP access, but the agent session had no discoverable tools and did not provide a supported onboarding-specific recovery route. Recommend a built-in connection health check, list of MCP tools available, an explanation of session-scoped availability, and official steps for recovery. **Session 2 succeeded, so the issue was intermittent/session-dependent — NOT proof of a permanent outage.**

## Session 2 — MCP accessible and question answered

**Exact user prompt:**
> I am completing the Pharos Agent Arena Docs MCP Onboarding task. In my previous session, the agent reported MCP tools: 0 and the command dtcoder mcp list was denied by security policy. Please check whether the official Developer Docs MCP is available in this new session. (1) List actual Docs MCP tools. (2) If available, invoke one tool for official beginner onboarding docs for AI.PHAROS. (3) Show name, request, response and source. (4) If unavailable, explain why. (5) Do not use web search, external docs, or invented outputs. Distinguish verified responses from assumptions.

**Reported outcome:**
- Bundled MCP client and Node.js `v22.22.2` were found by the agent.
- Remote Developer Docs MCP reported reachable; four tools listed above.
- `askQuestion` was invoked with:
  - `question`: "What is the official beginner onboarding documentation for AI.PHAROS?"
  - `goal`: "complete the Pharos Agent Arena Docs MCP Onboarding task"
- Returned answer focused on [Pharos Chain MCP](https://github.com/PharosNetwork/pharos-mcp), client MCP configuration and other resources, rather than a clear step-by-step **AI.PHAROS UI + Developer Docs MCP** onboarding sequence.

**Potential gap #2 (NEEDS REPRODUCTION):** The documentation answer may conflate Developer Docs MCP onboarding on `ai.pharos.xyz` with *connecting Chain MCP to an external agent client*. Do **not** count this as a confirmed gap until the follow-up test below demonstrates the missing distinctions.

## Follow-up tests (not yet executed; preserve actual results)

### Probe A — Confirm AI.PHAROS UI onboarding documentation

> Using Developer Docs MCP tools ONLY, search for an official step-by-step guide to using Developer Docs MCP *inside ai.pharos.xyz*, not Pharos Chain MCP in Claude Desktop. Search using `searchDocumentation`, open the most relevant hit with `getPage`, and answer with exact page titles and source links. Explain how to activate Developer Docs MCP in AI.PHAROS and how to verify that it worked. If no such page is returned, show the actual search query and the closest matching result; do not invent UI steps.

**Record:** actual tool invocations; returned results; whether sources directly answer the specific UI question; gap / fix if unsupported.

### Probe B — Obtain a reproducible beginner practical example

> Use ONLY Developer Docs MCP searchDocumentation and getPage to find an official, runnable beginner tutorial using Pharos development tools. Provide prerequisites, commands, expected output, source links, versions, and troubleshooting from the retrieved pages. Do not use external search or compose commands that are not in the documents. If two pages conflict or steps are missing, quote the exact sections and explain what needs correcting.

**Record:** source titles and code snippets; commands tried; errors observed; *independent* gap / fix if reproduced.

### Probe C — Verify documentation feedback workflow

> Using only Developer Docs MCP, locate the official explanation for the `sendFeedback` tool: required parameters, whether submission is public, what data it sends, and how to verify a submission. Read-only research only; DO NOT call `sendFeedback` yet. Quote the relevant sections and mention any missing guidance.

**Record:** source references and any actual unanswered issue; do not claim submitted feedback without a real confirmed tool result.

## Final outcome — provisional

- Public GitHub report repository created.
- Session-1 missing-tool blocker and session-2 successful MCP discovery documented.
- First official question answered via reported `askQuestion` response.
- **Still required:** three independent documented gaps with exact queries + suggested fixes, a demonstrable final exercise/outcome, accessible public proof with sufficient evidence.

The public proof is a record of results, not a claim that the Docs MCP server is continuously healthy. Any cited source outside the onboarding session is for context only and **not** a substitute for Docs MCP-only evidence.
