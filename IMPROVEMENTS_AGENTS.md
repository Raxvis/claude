# Agent System — Improvements Needed

A critical review of all 16 agent files and `agents/README.md`. Issues are grouped by severity tier.

**Status: All items resolved.**

---

## Tier 1: Blocking Issues

### 1.1 Input/Output Mismatches Between Agents — RESOLVED

Added missing input sources to: reviewer.md (Refactor, Tester), tester.md (Refactor), bug-gatherer.md (UX Critic, Reviewer, Tester), coder.md (Security, Performance, Asset Gen, Reviewer, Tester, Validator), validator.md (Product sign-offs, Reviewer, Tester).

### 1.2 No Agent Lists Docs Writer as an Output Consumer — RESOLVED

Added Docs Writer as output consumer to: product.md, architect.md, ui.md, coder.md, debugger.md, performance.md, ux-critic.md, asset-gen.md.

### 1.3 Debugger and Bug Gatherer Use Different Bug Formats — RESOLVED

Defined a two-stage Bug Lifecycle in debugger.md: Bug Report (owned by Bug Gatherer, initial filing) → Bug Investigation (owned by Debugger, adds root cause, alternative solutions, recommended fix). Status flow: New → Triaged → In Progress → Fixed → Verified → Closed. Bug Gatherer cross-references debugger.md for the full lifecycle.

### 1.4 Conflict Resolution Is Contradictory — RESOLVED

Rewrote Validator's Authority section to clarify: hierarchy applies to inter-agent disputes, unilateral authority applies within each agent's domain when no dispute exists. Added Clarification paragraph.

---

## Tier 2: Major Gaps

### 2.1 Missing Standard Sections in Agent Files — RESOLVED

Added Interaction Rules sections to reviewer.md, debugger.md, and bug-gatherer.md. Enhanced trigger conditions and ownership clarity in each.

### 2.2 Unclear Trigger/Activation Conditions — RESOLVED

Defined explicit triggers for: Reviewer (runs after Tester passes), Debugger (includes Product validation bugs), Release (activates on Product milestone signal + Validator compliance), Bug Gatherer (triggered by any agent or external source submission).

### 2.3 Workflow Ordering Is Ambiguous — RESOLVED

Rewrote README Per-Task Workflow with explicit sequencing: Tester runs first as automated gate, Reviewer runs only after tests pass, Refactor loops back to Tester then Reviewer.

### 2.4 Missing Escalation Paths — RESOLVED

Added Escalation Protocols table to README with 10 specific scenarios and resolutions covering all identified gaps.

### 2.5 Overlapping Responsibilities — RESOLVED

Added Responsibility Boundaries table to README designating primary owners for all 6 overlapping areas: code quality (Reviewer), architecture adherence (Architecture), documentation (Docs Writer), bug severity (Bug Gatherer initial, Product final), implementation scope (Coder new features, Refactor restructuring), pre-submission checks (complementary).

### 2.6 Refactor Has No Submission Checklist — RESOLVED

Created Refactor Submission Checklist template in refactor.md with: scope verification, affected modules table, architecture reference, testing requirements, quality checks.

### 2.7 Cross-Reference Rules Are Incomplete — RESOLVED

Added cross-reference rules to README for: Reviewer (cite standard/convention violated), Refactor (cite architectural principle), Security (cite vulnerability category), Performance (cite performance budget/metric).

---

## Tier 3: Structural Issues

### 3.1 Interaction Diagram Is Incomplete — RESOLVED

Redrew the README interaction diagram to include all 16 agents with proper boxes and connections: added Asset Gen, Bug Gatherer as proper boxes, showed Release/Docs Writer/Validator as process-wide agents.

### 3.2 Templates Table Missing Entries — RESOLVED

Added 7 entries to the README Templates table: Refactor Submission Checklist, Usability Heuristics, Severity Levels, Performance Budget Tracking, Asset Inventory, Process Checklist (Per Task), Severity Rubric. Total now 20 templates listed.

### 3.3 Documentation Placement Table Doesn't Match Agent Files — RESOLVED

Expanded Documentation Placement table to include a Tracking Format column specifying the exact column structure for each agent's Current Work section. Structured all agent Current Work tables with appropriate columns.

### 3.4 Validator Authority Description Is Confusing — RESOLVED

Rewrote Validator Authority to explicitly state: "Validator enforces the documented priority hierarchy. It does not substitute its own judgement — it enforces the hierarchy." Added Clarification paragraph distinguishing unilateral authority from dispute resolution.

### 3.5 Open Questions Tracking Is One-Sided — RESOLVED

Added Open Questions section to coder.md with tracking table. Added system-wide Open Questions Tracker to validator.md. Updated Validator's Session-Start Checklist to review pending Open Questions.

---

## Tier 4: Completeness Issues

### 4.1 No "Current Work" Tables Are Structured for Real Use — RESOLVED

Designed agent-specific Current Work table columns for: Reviewer, Tester, Debugger, Security, Performance, Refactor, UX Critic, Release, Docs Writer. Each now has columns appropriate to its actual workload.

### 4.2 No Agent Has Decisions Log Entries — RESOLVED

Added guidance to the README Agent File Structure description explaining what constitutes a notable decision worth logging.

### 4.3 Validator Session-Start Checklist References Unmeasurable Conditions — RESOLVED

Replaced session-based aging with calendar-based aging: "Confirm no unresolved conflicts are more than [MAX_AGE_DAYS, e.g., 3 days] old (use the Date column in the Conflicts table)."

### 4.4 Performance Budget Tables Are Duplicated — RESOLVED

Designated Architecture as the owner of targets (simplified to Metric/Target/Notes) and Performance as the owner of live tracking (Metric/Target/Current/Status/Notes). Each file cross-references the other.

### 4.5 Coder's Pre-Handoff Doesn't Require Minimum Test Coverage — RESOLVED

Added Pre-Handoff Checklist item: "Test coverage meets or exceeds [COVERAGE_TARGET]% for new code."

### 4.6 No Process for Handling Blocked Agents — RESOLVED

Added Blocked Agent Protocol to validator.md with 4-step escalation: immediate identification → same session notification → after N days reassignment/decomposition → after critical threshold human escalation. Also covered by Escalation Protocols table entry "An agent is blocked for more than 2 sessions."

### 4.7 Asset Gen Has No Relationship to UX Critic — RESOLVED

Added UX Critic as input source to asset-gen.md. Added Asset Gen as output consumer to ux-critic.md.
