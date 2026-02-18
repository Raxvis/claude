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
| Architecture | `architecture.md` | Owns system design, module boundaries, data schemas, and code review standards. Produces architecture documents that Builder implements. |
| UI | `ui.md` | Owns visual design, layout specifications, the style guide, and interaction patterns. Produces screen specs that Builder implements. |
| Builder | `builder.md` | Implements features as directed by Product, Architecture, and UI. Writes all production code and performs pre-handoff self-review. |
| Validator | `validator.md` | Owns the process. Enforces agent protocols, resolves conflicts between agents, tracks milestone progress, and runs retrospectives. |
| Bug Gatherer | `bug-gatherer.md` | Collects and structures bug reports from testers or stakeholders. Produces standardized reports that Product triages and Builder fixes. |

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
| **Decisions Log** | Record of notable decisions made by this agent and their rationale. |
| **Future Work** | Deferred items, nice-to-haves, and post-launch ideas. |

---

## Agent Interaction Diagram

```
                        ┌─────────────┐
                        │   Product   │
                        │   Agent     │
                        └──────┬──────┘
                               │ requirements & acceptance criteria
               ┌───────────────┼───────────────┐
               ▼               ▼               │
      ┌──────────────┐ ┌─────────────┐         │
      │ Architecture │ │     UI      │         │
      │    Agent     │ │    Agent    │         │
      └──────┬───────┘ └──────┬──────┘         │
             │ arch docs      │ UI specs       │
             └───────────────►│◄───────────────┘
                              ▼
                      ┌──────────────┐
                      │   Builder    │
                      │    Agent     │
                      └──────┬───────┘
                             │ completed work for review
                             ▼
                      ┌──────────────┐
                      │   Product    │◄─── Bug Gatherer
                      │  (Validates) │         │
                      └──────┬───────┘         │ bug reports
                             │                 │
                      ┌──────▼───────┐         │
                      │  Validator   │◄────────┘
                      │   Agent      │
                      └──────────────┘
```

---

## Workflow

### Per-Milestone Workflow

1. **Product** defines milestone goals and acceptance criteria.
2. **Architecture** produces architecture documents for all new modules.
3. **UI** produces screen specifications for all new interfaces.
4. **Builder** implements features using the above documents as authoritative references.
6. **Product** validates completed work against acceptance criteria.
7. **Validator** runs a milestone retrospective.

### Per-Task Workflow

1. **Product** writes a task definition with acceptance criteria.
2. **Architecture** and/or **UI** produce relevant specifications if not already available.
3. **Builder** implements the task, completes the Pre-Handoff Checklist, and marks the task ready for review.
4. **Product** reviews and signs off or returns with feedback.
5. **Validator** records the outcome in the process log.

### Cross-Reference Rules

- **Builder** must reference the relevant architecture document section for every module it touches.
- **Builder** must reference the relevant UI spec section for every screen or component it implements.
- **Product** must reference a specific acceptance criterion when rejecting a task.
- **Validator** must cite the specific rule that was violated when flagging a process violation.

### Session Start

At the start of every working session:

1. **Validator** reviews the Agent Status Dashboard and confirms no agents are in a blocked state.
2. **Product** confirms the current milestone and priority order.
3. **Builder** selects the next unstarted task from the Work Queue.

---

## Documentation Placement

| Document Type | Owner | Location |
|---|---|---|
| Feature requirements | Product | `product.md` → Decisions Log |
| Architecture documents | Architecture | `architecture.md` → Architecture Documents table |
| Screen specifications | UI | `ui.md` → Screen Specifications section |
| Bug reports | Bug Gatherer | `bug-gatherer.md` or issue tracker |
| Milestone retrospectives | Validator | `validator.md` → Milestone Retrospective |
| Decisions | Each agent | Agent's own Decisions Log table |

---

## Templates

Each agent file contains reusable templates:

| Template | Location |
|---|---|
| Task Validation Checklist | `product.md` |
| Module Architecture Doc | `architecture.md` |
| System Architecture Doc | `architecture.md` |
| Data Schema Doc | `architecture.md` |
| Code Review Checklist | `architecture.md` |
| Pre-Handoff Checklist | `builder.md` |
| UI Spec Template | `ui.md` |
| UX Review Checklist | `ui.md` |
| Milestone Retrospective | `validator.md` |
| Bug Report | `bug-gatherer.md` |
