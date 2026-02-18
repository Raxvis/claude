<!-- TEMPLATE INSTRUCTIONS
PURPOSE: This file is the master overview of the multi-agent documentation system for your project.
It describes every agent, how they interact, and the conventions that govern them.

HOW TO CUSTOMIZE:
1. Replace [PROJECT_NAME] with the name of your project.
2. Replace [AI_MODEL] with the model used by all agents (e.g., the model powering your AI assistant).
3. Replace [FEATURE_AREA_*] placeholders with real feature areas, modules, or subsystems in your project.
4. Replace [ARTIFACT_TYPE_*] with the categories of deliverables your project produces.
5. Review the Agent table and remove rows for agents your project does not need.
6. Update the ASCII diagram to reflect any changes to the agent lineup.
7. Update the Documentation Placement table to match your actual folder/file conventions.
-->

# [PROJECT_NAME] — Agent System Overview

## What Is This?

This directory contains the working documentation for each specialized agent that assists in developing [PROJECT_NAME]. Each agent owns a domain, maintains its own decisions log, and hands off work to other agents via structured outputs.

All agents run on **[AI_MODEL]**.

---

## Agent Roster

| Agent | File | Role |
|---|---|---|
| Product | `product.md` | Owns requirements, validates completed tasks against acceptance criteria, maintains the feature backlog, and signs off on milestones. |
| Architecture | `architect.md` | Owns system design, module boundaries, data schemas, and code review standards. Produces architecture documents that Coder implements. |
| UI | `ui.md` | Owns visual design, layout specifications, the style guide, and interaction patterns. Produces screen specs that Coder implements. |
| Coder | `coder.md` | Implements features as directed by Product, Architecture, and UI. Writes all production code and performs pre-handoff self-review. |
| Reviewer | `reviewer.md` | Reviews everything the Coder produces. Evaluates code against quality standards, architecture documents, and UI specifications. |
| Tester | `tester.md` | Generates and maintains automated test coverage. Runs after every change the Coder makes. |
| Debugger | `debugger.md` | Investigates bugs found by Reviewer, Tester, or the user. Logs to `docs/BUGS.md`, explains defects, and provides alternative solutions. |
| Refactor | `refactor.md` | Improves code structure without changing behaviour. Triggered by Reviewer or Tester issues, or invoked by the user. |
| Docs Writer | `docs-writer.md` | Produces and maintains developer-facing documentation. Runs after any other agent completes work. Accepts direct user input. |
| UX Critic | `ux-critic.md` | Evaluates user flows against usability heuristics. Runs after Product and Coder. Files issues with Bug Gatherer. |
| Security | `security.md` | Identifies vulnerabilities and insecure patterns. Runs after Architecture changes or plans. Can be invoked by the user. |
| Performance | `performance.md` | Profiles, identifies bottlenecks, and proposes optimisations. Runs after Architecture changes and provides feedback to Architecture. |
| Release | `release.md` | Owns release preparation: changelogs, versioning, and build verification. |
| Asset Gen | `asset-gen.md` | Specifies and produces visual assets. Coordinates with UI for design consistency and Coder for integration. |
| Validator | `validator.md` | Owns the process. Enforces agent protocols, resolves conflicts between agents, tracks milestone progress, and runs retrospectives. |
| Bug Gatherer | `bug-gatherer.md` | Collects and structures bug reports from testers or stakeholders. Produces standardized reports that Product triages and Coder fixes. |

---

## Conflict Resolution Priority

When agents disagree, the following hierarchy applies:

1. **Product** — business requirements and user experience goals take highest priority
2. **Architecture** — system design constraints and technical feasibility
3. **UI** — visual and interaction design

The **Validator** agent does not override any of the above; it enforces that all agents follow the documented process.

---

## Agent File Structure

Every agent file follows this standard structure:

| Section | Description |
|---|---|
| **Purpose** | One-paragraph description of what this agent owns. |
| **Goals** | Bulleted list of success criteria for this agent. |
| **Authority** | What decisions this agent can make unilaterally. |
| **Inputs** | What this agent receives from other agents or external sources. |
| **Outputs** | What this agent produces and who consumes it. |
| **Current Work** | Active tasks, queues, and in-progress items. |
| **Decisions Log** | Record of notable decisions made by this agent and their rationale. Log when: accepting a non-standard approach, deviating from convention, choosing between alternatives, or establishing a precedent that future work should follow. |
| **Future Work** | Deferred items, nice-to-haves, and post-launch ideas. |

---

## Agent Interaction Diagram

```
                           ┌─────────────┐
                           │   Product   │
                           └──────┬──────┘
                                  │ requirements & acceptance criteria
                  ┌───────────────┼───────────────┐
                  ▼               ▼               │
         ┌──────────────┐ ┌─────────────┐         │
         │ Architecture │ │     UI      │         │
         └──┬───┬───┬───┘ └──────┬──────┘         │
            │   │   │            │                │
            │   │   │  arch docs │ UI specs       │
            │   │   │            │                │
            │   │   │     ┌──────┴──────┐         │
            │   │   └────►│  Asset Gen  │         │
            │   │         └──────┬──────┘         │
            │   │                │ asset specs    │
            │   │                ▼                │
            │   │         ┌──────────────┐◄───────┘
            │   │         │    Coder     │
            │   │         └──────┬───────┘
            │   │                │ every change
            │   │                ▼
            │   │         ┌──────────────┐
            │   │         │   Tester     │ (automated gate)
            │   │         └──────┬───────┘
            │   │                │ tests must pass
            │   │                ▼
            │   │         ┌──────────────┐
            │   │         │   Reviewer   │◄──────────────┐
            │   │         └──────┬───────┘               │
            │   │                │ defects / issues       │
            │   │         ┌──────┴───────┐               │
            │   │         ▼              ▼               │
            │   │  ┌──────────────┐ ┌──────────────┐     │
            │   │  │   Debugger   │ │   Refactor   │─────┘
            │   │  └──────┬───────┘ └──────────────┘
            │   │         │ logs via          ▲ loops back
            │   │         ▼                  │ to Tester then
            │   │  ┌──────────────┐          │ Reviewer until
            │   │  │ Bug Gatherer │          │ both approve
            │   │  └──────┬───────┘
            │   │         │ structured reports
            │   │         ▼
            │   │  ┌──────────────┐
            │   │  │   Product    │ (triages bugs, validates work)
            │   │  └──────────────┘
            │   │
            │   └────────►┌──────────────┐
            │             │   Security   │ (after arch changes)
            └────────────►└──────────────┘
            │
            └────────────►┌──────────────┐
                          │ Performance  │ (after arch changes,
                          └──────────────┘  feeds back to Architecture)

         ┌──────────────┐
         │  UX Critic   │ (after Product & Coder)
         └──────┬───────┘
                │ files issues with Bug Gatherer
                ▼
         ┌──────────────┐
         │ Bug Gatherer │ (single entry point for all bugs)
         └──────────────┘

  ┌──────────────┐    ┌──────────────┐    ┌──────────────┐
  │  Docs Writer │    │   Release    │    │  Validator   │
  │ (after all   │    │ (milestone   │    │ (process     │
  │  agents)     │    │  readiness)  │    │  oversight)  │
  └──────────────┘    └──────────────┘    └──────────────┘
```

---

## Workflow

### Per-Milestone Workflow

1. **Product** defines milestone goals and acceptance criteria.
2. **Architecture** produces architecture documents for all new modules.
3. **Security** and **Performance** review architecture plans and provide feedback.
4. **UI** produces screen specifications for all new interfaces.
5. **Coder** implements features using the above documents as authoritative references.
6. **Tester** runs tests after every Coder change. **Reviewer** reviews every Coder submission.
7. **Debugger** investigates any bugs found. **Refactor** addresses structural issues, then flows back to **Tester** and **Reviewer** to confirm completeness.
8. **UX Critic** evaluates user flows after Product and Coder complete work.
9. **Docs Writer** updates documentation after each agent completes work.
10. **Product** validates completed work against acceptance criteria.
11. **Release** prepares changelog, versioning, and build verification.
12. **Validator** runs a milestone retrospective.

### Per-Task Workflow

1. **Product** writes a task definition with acceptance criteria.
2. **Architecture** and/or **UI** produce relevant specifications if not already available.
3. **Security** reviews architecture changes. **Performance** evaluates and feeds back to Architecture.
4. **Coder** implements the task, completes the Pre-Handoff Checklist, and marks the task ready for review.
5. **Tester** runs tests (automated gate). If tests fail, work returns to **Coder**. Tester must pass before proceeding.
6. **Reviewer** reviews the code (only after Tester passes). If changes are required, work returns to **Coder** or **Refactor**. **Refactor** flows back to step 5 (Tester then Reviewer) — this loop repeats until both approve.
7. **Debugger** investigates any defects found by Tester or Reviewer. Logs to `docs/BUGS.md` via **Bug Gatherer**.
8. **UX Critic** evaluates user-facing flows and files issues with **Bug Gatherer**.
9. **Product** reviews and signs off or returns with feedback. If rejected, work returns to step 4.
10. **Docs Writer** updates documentation.
11. **Validator** records the outcome in the process log.

### Cross-Reference Rules

- **Coder** must reference the relevant architecture document section for every module it touches.
- **Coder** must reference the relevant UI spec section for every screen or component it implements.
- **Product** must reference a specific acceptance criterion when rejecting a task.
- **Validator** must cite the specific rule that was violated when flagging a process violation.
- **Reviewer** must cite the specific standard, convention, or document that a piece of code violates when requesting changes.
- **Refactor** must cite the architectural principle or quality issue that justifies each refactoring change.
- **Security** must cite the vulnerability category (e.g., OWASP item) or security principle that applies to each finding.
- **Performance** must cite the specific performance budget or metric that is affected by each finding.

### Session Start

At the start of every working session:

1. **Validator** reviews the Agent Status Dashboard and confirms no agents are in a blocked state.
2. **Product** confirms the current milestone and priority order.
3. **Coder** selects the next unstarted task from the Work Queue.

### Escalation Protocols

| Scenario | Resolution |
|---|---|
| Tester fails but Reviewer would approve | Tester gate takes precedence. Tests must pass before Reviewer runs. Coder fixes the test failure first. |
| Reviewer rejects work that Tester passed | Work returns to Coder with Reviewer's specific change requests. Tester re-runs after Coder's changes. |
| Product rejects work that Reviewer approved | Work returns to Coder with Product's cited acceptance criteria. Tester and Reviewer re-run after changes. Coder may raise an Open Question if the rejection criteria are unclear. |
| Coder disputes Product's rejection | Coder raises an Open Question citing the specific acceptance criterion. Validator mediates using the conflict resolution hierarchy. Product has final say per hierarchy. |
| Debugger cannot reproduce a bug | Debugger marks status as "Cannot Reproduce" with investigation details. Bug Gatherer notifies the original reporter. Product decides whether to close or request further investigation. |
| Tests fail due to infrastructure, not code | Tester flags the failure as "Environment Issue" and notifies Validator. Validator pauses the test gate until infrastructure is resolved. Coder is not blocked from continuing other work. |
| Security finds Critical issue in Approved architecture | Security files a blocking finding. Architecture must revise the document (status changes to "Superseded"). Coder stops implementation of affected modules. Validator tracks the blocker. |
| Product's acceptance criteria require an architecture change | Coder raises an Open Question to Architecture. Architecture revises the document and routes through Security/Performance review. If Architecture disagrees with the criteria, Validator applies the hierarchy (Product > Architecture). |
| Refactor breaks tests after change | Work returns to Refactor to fix. Tester re-runs. If the failure is a test infrastructure issue, Tester flags as environment issue per the protocol above. |
| An agent is blocked for more than 2 sessions | Validator escalates: reassigns work if possible, calls a process review, or escalates to a human stakeholder. |

---

## Responsibility Boundaries

When two agents cover related territory, one is the **primary owner** and the other defers or escalates.

| Area | Primary Owner | Secondary | Boundary |
|---|---|---|---|
| Code quality assessment | Reviewer | Tester | Reviewer owns conventions, correctness, style, and architecture adherence. Tester owns test adequacy, coverage metrics, and pass/fail results. Tester does not assess code quality; Reviewer does not write or run tests. |
| Architecture adherence | Architecture | Reviewer | Architecture has final say on module boundary disputes and design questions. Reviewer flags violations during code review and defers to Architecture if Coder disagrees. |
| Documentation of code | Docs Writer | Coder | Coder documents in-code references (architecture doc citations, UI spec citations) via the Pre-Handoff Checklist. Docs Writer maintains all files in `docs/` and ensures documentation stays current after every agent action. Coder does not update `docs/` directly. |
| Bug severity assignment | Bug Gatherer | Debugger | Bug Gatherer suggests initial severity when filing the report (status: New). Debugger does not change severity — it adds investigation fields (root cause, alternative solutions). Product sets final severity during triage. |
| Implementation scope | Coder | Refactor | Coder implements new features and fixes assigned bugs. Refactor restructures existing code without changing behaviour. When Reviewer or Tester flags a structural issue, it goes to Refactor. When a feature or bug fix is needed, it goes to Coder. |
| Pre-submission quality checks | Coder (self-check) | Product (validation) | Coder's Pre-Handoff Checklist is a self-assessment before submission. Product's Task Validation Checklist is an independent verification. Both are required — they are complementary, not redundant. Coder checks before submitting; Product validates after receiving. |

---

## Documentation Placement

| Document Type | Owner | Location | Tracking Format |
|---|---|---|---|
| Feature requirements | Product | `product.md` → Current Work | Task / Milestone / Status / Notes |
| Architecture documents | Architecture | `architect.md` → Architecture Documents table | Document / Module / Status / Milestone |
| Screen specifications | UI | `ui.md` → Screen Specifications table | Screen / Milestone / Status / Notes |
| Code review verdicts | Reviewer | `reviewer.md` → Current Work | Submission / Source Agent / Date / Verdict / Notes |
| Test results and coverage | Tester | `tester.md` → Current Work | Change / Source Agent / Tests Run / Pass-Fail / Coverage Delta |
| Bug investigations | Debugger | `docs/BUGS.md` | Bug ID / Source / Status / Assigned To / Notes |
| Bug reports (initial) | Bug Gatherer | `docs/BUGS.md` via Bug Report Template | See `bug-gatherer.md` → Bug Report Template |
| Security audit findings | Security | `security.md` → Current Work | Finding / Severity / Module / Status / Notes |
| Performance analysis | Performance | `performance.md` → Current Work | Finding / Metric / Impact / Status / Notes |
| UX evaluations | UX Critic | Filed with Bug Gatherer | Via Bug Gatherer Bug Report Template |
| Asset specifications | Asset Gen | `asset-gen.md` → Asset Inventory | Asset Name / Category / Format / Size / Status |
| Developer documentation | Docs Writer | `docs/` directory | Per `docs/README.md` index |
| Changelog and versioning | Release | `docs/CHANGELOG.md` | Per Release Checklist Template |
| Milestone retrospectives | Validator | `validator.md` → Milestone Retrospective | Per Milestone Retrospective Template |
| Decisions | Each agent | Agent's own Decisions Log table | Date / Decision / Rationale / Impact |

---

## Templates

Each agent file contains reusable templates:

| Template | Location |
|---|---|
| Task Validation Checklist | `product.md` |
| Module Architecture Doc | `architect.md` |
| System Architecture Doc | `architect.md` |
| Data Schema Doc | `architect.md` |
| Code Review Checklist | `architect.md` |
| Pre-Handoff Checklist | `coder.md` |
| Review Checklist | `reviewer.md` |
| UI Spec Template | `ui.md` |
| UX Review Checklist | `ui.md` |
| Refactor Submission Checklist | `refactor.md` |
| Bug Investigation Fields | `debugger.md` |
| Usability Heuristics | `ux-critic.md` |
| Severity Levels | `security.md` |
| Performance Budget Tracking | `performance.md` |
| Asset Inventory | `asset-gen.md` |
| Release Checklist | `release.md` |
| Milestone Retrospective | `validator.md` |
| Process Checklist (Per Task) | `validator.md` |
| Bug Report | `bug-gatherer.md` |
| Severity Rubric | `bug-gatherer.md` |
