# MORPHEUS Workbench

https://github.com/omghotekar01-dotcom/prompts---morpheus
UI/UX inspiration:
https://github.com/cjwirth/awesome-ios-ui
https://github.com/topics/uiux?l=swift
https://github.com/topics/ios-ui?l=javascript&o=desc&s=forks
https://github.com/topics/ios-component
https://github.com/topics/iphone-ui

You are a senior product designer and full-stack engineer. Redesign and implement the MORPHEUS web experience using the repository provided (https://github.com/omghotekar01-dotcom/prompts---morpheus) and an ultra-refined, iOS-inspired UI/UX design language. First inspect the existing frontend, API client, backend routes, tests, and documentation. Then make the actual website coherent, polished, simple to demonstrate, and connected to the existing system.

Do not return only a mockup or a proposal. Implement the frontend changes in the project. Preserve working features and backend contracts. Do not replace real behavior with demo-only responses.

### 1. Product truth: what MORPHEUS is

MORPHEUS is a workload-aware data-structure selection and synthesis workbench for software engineers and DSA learners. A user describes or uploads data, declares the operations an application performs and their expected frequency, and sets constraints. MORPHEUS evaluates its registered data-structure implementations, explains the eligible candidates, estimates their costs, and can generate a C++20 physical-plan artifact for inspection and verification.

The central user journey is:

1. Supply a dataset or choose a clearly marked synthetic example.
2. Describe the data fields and expected operations (lookups, ranges, filters, prefixes, and supported mutations).
3. Set workload weights and constraints.
4. Compare the feasible evaluated data-structure candidates and understand why they were included or excluded.
5. Inspect generated C++20, run its compile and behavior checks, and review the saved evidence.

Be precise about results:
- A profile's row count, field types, and distinct-value counts come from the supplied data.
- A reference query reports matches found by scanning supplied records; it is not an index benchmark.
- Candidate latency, memory, and scores are modeled estimates unless the screen explicitly presents valid measurement evidence.
- Compile/behavior verification proves only the checks actually run; it does not prove a speedup.
- A "best" candidate means the best feasible candidate MORPHEUS evaluated for the submitted model, constraints, and search budget—not a universally fastest structure.
- Operation weights are user assumptions unless derived from a real workload trace. A dataset alone does not reveal how an application will query it.
- Never invent a winner, timing, verification pass, telemetry, record, or evidence to make the screen look complete.

### 2. Accurate implementation and language layers

Keep the existing architecture and use the repository to confirm exact file names, behavior, and routes:
- **React + TypeScript frontend:** user interaction, forms, navigation, state, and result presentation. Reuse the current API client and existing shared types.
- **Python FastAPI control plane:** HTTP validation, workload orchestration, data adapters, cost/scoring compatibility, code-generation orchestration, and evidence/run APIs.
- **C++20 engine:** native dataset profiling and bounded configuration-space search; the actual registered physical structures include Robin Hood Hash, B+ Tree, Sorted Array, Radix Trie, Compressed Bitmap, and CSR Graph. Which structures are eligible depends on operation and field semantics.
- **Java 17+ scorer:** evaluates weighted modeled objectives and constraints when compiled and enabled. It scores modeled inputs; it is not itself a hardware benchmark.
- **C11 learning example:** a separate, small binary-search lesson. Do not imply it is the C++ synthesis engine.
- **Persistence/evidence:** saved runs, artifacts, and the integrity ledger belong to the existing backend. Display their real status and errors.
- **Optional AI:** may draft or explain language when configured. It is not required for normal synthesis, must not choose results in place of the engine, and must not create evidence or control actions.

### 3. Product and audience

Design for two overlapping audiences:
- A student/teacher who needs to understand and demonstrate DSA concepts in plain language.
- An engineer who wants a transparent, evidence-aware workload-specific design workflow.

Make the first view understandable in under a minute. Explain unfamiliar terms inline (short tooltips or "What does this mean?" disclosures), not with paragraphs of jargon.

**MORPHEUS — Workload-aware DSA Workbench**
"See how your data is used. Compare implemented data structures. Inspect and verify the generated C++."

### 4. Information architecture: simple first, advanced when needed

Use a small primary navigation:
1. **Home** — what MORPHEUS does, system connection state, and one obvious "Start a demo" action.
2. **Data** — upload the supplied demo workbook or a user's own supported data; show the actual profile and preview.
3. **Workload** — choose operations/fields, set relative traffic weights and constraints, and run synthesis.
4. **Results** — recommendation, alternatives, per-operation eligibility, rejection explanations, search coverage, and clear evidence labels.
5. **Code & Verify** — inspect generated C++, run compile/behavior checks, and show exactly which gates passed.
6. **Learn DSA** — a compact teaching area explaining the structures actually implemented and the separate C and Java learning/code paths.

Put **Saved Runs** and secondary engineering screens under a tidy **More / Advanced** area rather than showing all of them as equal-priority navigation. Preserve useful current advanced functions such as Decision Review, Hot Path Doctor/Watch, Search Space, Cost Model, Primitive Registry, Machine Profiles, Runtime Observatory, Audit & Evidence, and MORPHEUS Copilot. Group them by purpose and label them advanced; do not delete them or put them in the first-run path.

### 5. Visual design system (iOS-inspired fidelity)

Create a calm, professional, modern engineering/education interface with iOS-inspired craftsmanship:
- iOS-style segmented controls, clean frosted cards, crisp typography, and refined micro-interactions.
- Dark navy structure, cool accent actions, neutral surfaces, semantic status indicators.
- Responsive mobile, tablet, and desktop layouts.
- Clear distinction between model estimates, actual measurements, and verification gates.

This project was built with [Lovable](https://lovable.dev).

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/378a73a2-7b13-4d09-acac-a083fd0cf707).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
