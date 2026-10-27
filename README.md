# Pharos Agent Arena — Docs MCP Onboarding

> **Task:** Easy · Developer Docs MCP · 50 points (+ optional 50-point video bonus)
>
> **Status:** Evidence report drafted from genuine AI.PHAROS sessions. No task reward or reviewer approval is claimed. No smart contract or Hardhat dApp has been deployed as part of this task.

## Goal and method

Self-onboard to [AI.PHAROS](https://ai.pharos.xyz/) using **only Developer Docs MCP**, without asking AI.PHAROS to consult web search or external documentation. Preserve (1) each question and observed answer, (2) 3+ concrete gaps with exact queries, (3) a proposed documentation fix for every gap, and (4) an honest account of what was **actually run**.

The original task is about **documentation feedback**, not necessarily deploying a new dApp. The follow-up Hardhat tutorial was an attempt to locate a reproducible beginner exercise, not a claim of completion or deployment.

## Tools and sources discovered in the successful session

AI.PHAROS reported a reachable GitBook Developer Docs MCP endpoint:

`https://docs.pharos.xyz/~gitbook/mcp`

| Reported tool | Purpose |
|---|---|
| `searchDocumentation` | Search Pharos developer documentation |
| `getPage` | Retrieve a documentation page in Markdown |
| `askQuestion` | Answer a question using documentation with source links |
| `sendFeedback` | Send feedback about documentation (write operation, **not used**) |

This is **Developer Docs MCP**, distinct from the Pharos **Chain MCP** at `https://mcp.pharos.xyz/mcp`. Tool names and responses below were reported by AI.PHAROS in captured screenshots, not independently executed by this static page.

## Step-by-step onboarding log

### Step 01 — Initial discovery failed

**Prompt sent (excerpt of first user message):**

> I am completing the Pharos Agent Arena "Docs MCP Onboarding" task. I want to onboard myself to ai.pharos.xyz using ONLY the official Developer Docs MCP. Please connect to and use the Developer Docs MCP tools; list available tools, explain AI.PHAROS and beginner onboarding, cite exact source pages, suggest a practical task, and explicitly identify gaps. Do not use web search or external documentation.

**Observed response:** `MCP tools: 0`; "Developer Docs MCP is not available in this session." AI.PHAROS reported its attempted `dtcoder mcp list` command was blocked by security policy. No Docs MCP pages were retrieved in this session.

**Outcome:** blocked in session 1. **Limit:** the later success disproves any claim that Docs MCP is universally inaccessible.

### Step 02 — Restarted investigation in a new session

**Prompt sent (full text):**

```text
I am completing the Pharos Agent Arena Docs MCP Onboarding task.

In my previous session, the agent reported MCP tools: 0 and the command dtcoder mcp list was denied by security policy.

Please check whether the official Developer Docs MCP is available in this new session.

1. List the actual Developer Docs MCP tools available to you.
2. If available, invoke one tool to retrieve the official beginner onboarding documentation for AI.PHAROS.
3. Show the actual tool name, request parameters, response and documentation source.
4. If unavailable, explain the exact reason and provide the supported recovery instructions from the tools you can actually access.
5. Do not use web search, external docs or invented tool outputs.

Please distinguish verified tool responses from assumptions.
```

**Observed response:** The assistant reported access to the four tools listed above, a bundled MCP Inspector, and a successful `askQuestion` call:

```json
{
  "question": "What is the official beginner onboarding documentation for AI.PHAROS?",
  "goal": "complete the Pharos Agent Arena Docs MCP Onboarding task"
}
```

It returned instructions for Pharos Chain MCP, connecting MCP-capable external clients, and links to Skill Engine, Anvita Flow and dApp guides.

**Outcome:** Docs MCP reachable in that session; first documentation question completed.

### Step 03 — Focused search for AI.PHAROS Docs MCP onboarding

**Exact prompt sent:**

```text
Using ONLY Developer Docs MCP, please use
searchDocumentation and getPage to find the exact
official onboarding guide for Developer Docs MCP
inside ai.pharos.xyz.

I do NOT want instructions for connecting Pharos
Chain MCP to Claude Desktop or other external clients.

Show:
1. Exact search queries and returned results.
2. Official documentation page titles and URLs.
3. Step-by-step AI.PHAROS interface instructions.
4. How a beginner verifies Docs MCP is connected.
5. Any missing or unclear steps and proposed fixes.

Do not invent documentation or use web search.
```

**Search queries reported by AI.PHAROS:**

1. `Developer Docs MCP onboarding ai.pharos.xyz` → top hit [Pharos MCP](https://docs.pharos.xyz/tooling-and-infrastructure/mcp) (Chain MCP; not the requested workflow).
2. `Agent Arena onboarding ai.pharos.xyz developer console` → top hit [Publish Service Agent](https://docs.pharos.xyz/tooling-and-infrastructure/overview/publish-skill-af), which concerns Anvita Flow service agents.
3. `Docs MCP GitBook MCP server ai.pharos.xyz` → no specific Docs MCP onboarding page was found in the reported results.

Other reported hits included [Anvita Flow](https://docs.pharos.xyz/tooling-and-infrastructure/overview). The answer supplied instructions for an Anvita Flow service-agent console at `flow.anvita.xyz`, not for navigating Docs MCP inside `ai.pharos.xyz`.

**Outcome:** Search and read workflow exercised; searches **did not locate** the requested AI.PHAROS-specific guide. That does **not** establish that such a page does not exist anywhere.

### Step 04 — Read a concrete Hardhat beginner guide via Docs MCP

**Exact prompt sent:**

```text
Using ONLY Developer Docs MCP, find the official
"Write Your First dApp (Hardhat)" beginner guide.

Call searchDocumentation and getPage.

Provide:
1. Exact source page and URL.
2. Required software and versions.
3. Complete step-by-step commands.
4. Pharos network configuration from the docs.
5. Expected results for each major step.
6. Missing, ambiguous or contradictory instructions.

Do not invent commands or use external documentation.
I want to reproduce a real beginner task on Windows.
```

**Reported tool activity:** `searchDocumentation` queried `Write Your First dApp Hardhat beginner guide`; `getPage` retrieved [Write Your First dApp](https://docs.pharos.xyz/developer-guide/hardhat/write-your-first-dapp). A second search retrieved [Atlantic Testnet](https://docs.pharos.xyz/getting-started/network/atlantic-testnet) to identify RPC and chain ID.

**Returned guide steps (summarized):**

```shell
git clone https://github.com/PharosNetwork/examples
cd examples/dapp/hardhat
npm install
npx hardhat vars set PRIVATE_KEY
cd contract && npm install
npx hardhat ignition deploy ./ignition/modules/Counter.js --network pharos
# Edit src/app.jsx and replace YOUR_CONTRACT_ADDRESS
npm start
```

The queried Pharos Atlantic Testnet page reported RPC `https://atlantic.dplabs-internal.com` and chain ID `688689`. The guide itself uses `--network pharos` without defining which network the alias should target.

**Outcome:** Documentation was retrieved and assessed. **Not executed locally**: No contract was deployed; no key was supplied. The point of this onboarding task was to identify instructions that would block a new developer.

## Concrete gaps, exact queries, and suggested fixes

### Gap 1 — Intermittent Docs MCP access with no actionable recovery path

- **Exact query:** The full session-2 prompt in Step 02 (including reference to the earlier `MCP tools: 0` failure).
- **Observed problem:** Session 1 reported no registered tools and a denied CLI listing; session 2 successfully exposed four tools. The onboarding flow did not document a supported recovery path after the first failure.
- **Suggested fix:** Add a prominent Docs MCP connection diagnostic to AI.PHAROS, document expected tool names, distinguish session issues from server outages, and describe supported reinitialization/retry steps.
- **Scope:** Agent/session experience, not proof of a global Docs MCP outage.

### Gap 2 — Onboarding search does not distinguish Developer Docs MCP in AI.PHAROS from Chain MCP / Anvita Flow

- **Exact query:** The full focused prompt in Step 03.
- **Observed problem:** Even after explicitly excluding external clients, the reported search results and extracted instructions concerned [Pharos Chain MCP](https://docs.pharos.xyz/tooling-and-infrastructure/mcp) and [Publish Service Agent](https://docs.pharos.xyz/tooling-and-infrastructure/overview/publish-skill-af).
- **Suggested fix:** Publish a dedicated **Using Developer Docs MCP inside AI.PHAROS** guide, including where to activate the docs skill, how to verify tool discovery, a minimal `searchDocumentation` / `getPage` example, and common errors. Ensure search ranks this page above unrelated Chain MCP instructions.
- **Scope:** Missing/poorly ranked documentation in the **observed search results**, not an assertion that the entire documentation site lacks the guide.

### Gap 3 — Hardhat tutorial omits required network configuration steps

- **Exact query:** The full Hardhat prompt in Step 04.
- **Observed problem:** The [dApp guide](https://docs.pharos.xyz/developer-guide/hardhat/write-your-first-dapp) invokes `--network pharos` without showing the `hardhat.config.js` network entry or explaining its RPC placeholder. A related official example does have [contract/hardhat.config.js](https://github.com/PharosNetwork/examples/blob/main/dapp/hardhat/contract/hardhat.config.js), where the URL is a `<PHAROS_RPC_URL>` placeholder. The guide does not walk the learner through this setup.
- **Suggested fix:** Link directly to the example config; explain how to replace the placeholder for **Atlantic Testnet**, specify chain ID and account method, show a safe testnet-only setup, and explain how to check the network before deploying.
- **Scope:** Documented gap in the tutorial; **not** a claim that the source repository lacks config.

### Gap 4 — Beginner prerequisites lack version and Windows instructions

- **Exact query:** The full Hardhat prompt in Step 04.
- **Observed problem:** The guide links to Node.js and Hardhat but does not specify validated versions, npm requirements, or Windows PowerShell-specific steps. A Windows beginner cannot tell which toolchain versions were used to verify the recipe.
- **Suggested fix:** Publish a tested version matrix with Node.js, npm and Hardhat version ranges; add a Windows PowerShell subsection and expected commands/output.
- **Scope:** Version guidance is missing from the **page**. The sample repository pins broad ranges in package.json, but the page does not explain them.

### Gap 5 — Frontend example lacks explicit ethers.js compatibility requirements

- **Exact query:** The full Hardhat prompt in Step 04.
- **Observed problem:** The tutorial uses `ethers.providers.Web3Provider(window.ethereum)`, the ethers v5 API pattern, while not naming a compatible ethers major version. The guide also does not mention how a beginner should provision and connect a browser wallet for `window.ethereum`.
- **Suggested fix:** Pin ethers v5 alongside the example *or* provide a tested ethers v6 sample using `BrowserProvider`. Include wallet setup and connection guidance.
- **Scope:** Compatibility/documentation omission; the example has not been executed in the user's environment.

### Additional issues observed (not required to count toward the three)

- The guide says to run `npm start` in the frontend directory without spelling out the directory and expected script configuration; `examples/dapp/hardhat/package.json` has no `start` script in the inspected repository.
- The guide's troubleshooting references testnet tokens but does not provide a faucet/link or a full deployment output example.
- It does not explicitly explain whether the learner should choose Atlantic Testnet or Pacific Mainnet.

## What was actually built or run by the end

**Completed in AI.PHAROS (as reported in screenshots):**
- First session: diagnosed a tool-discovery blocker.
- Second session: discovered the remote Docs MCP endpoint and four tools.
- Invoked `askQuestion` to retrieve beginner onboarding material.
- Queried `searchDocumentation` for AI.PHAROS Docs MCP onboarding, inspected returned pages and sources.
- Queried `searchDocumentation` and `getPage` to retrieve the Hardhat tutorial and consulted the Atlantic Testnet page.
- Documented at least three independent documentation/experience gaps and concrete fixes.
- Created a public report repository and report page.

**Not completed / not claimed:** no Hardhat dApp was run locally; no smart contract deployed; no `sendFeedback` mutation performed; no Agent Arena reviewer approval yet.

### Reproduction checklist for reviewers

1. Visit [AI.PHAROS](https://ai.pharos.xyz/).
2. Ask the exact questions in Steps 02–04 using Developer Docs MCP only.
3. Compare retrieved page excerpts with the listed source URLs.
4. Inspect each proposed fix and the explanation of limitations.
5. If the page appears stale, press **F5**, or **Ctrl + F5** on Windows to bypass cached content.

### Evidence note

This README transcribes and organizes **user-provided screenshots**. The official public documentation was separately checked for consistency when preparing the report, but those external checks were **not** used as substitutes for the user's Docs MCP-only AI.PHAROS session. Original screenshots can be added under `evidence/` for visual reviewer verification.
