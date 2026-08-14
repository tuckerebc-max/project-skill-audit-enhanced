# Project Skill Audit Protocol

## Minimum inventory fields

`Skill ID`, `Folder`, `SKILL.md Path`, `Frontmatter Name`, `Description`, `Line Count`, `UI Metadata`, `References`, `Scripts`, `Assets`, `Placeholders`, `Validation Status`, `Likely Triggers`, `Notes`.

## Finding schema

Use one finding per issue:

`Finding ID`, `Priority`, `Skill/Package`, `Dimension`, `File`, `Line or Condition`, `Finding`, `Evidence`, `Impact`, `Recommended Fix`, `Status`, `Verification`.

Use `Open`, `Accepted`, `Fixed`, `Deferred`, or `Won't fix` for status. If a finding cannot be tied to evidence, label it as a recommendation rather than a defect.

## Scoring anchors

- **Pass:** clear, internally consistent, operational, and supported by validation evidence.
- **Needs work:** usable but ambiguous, incomplete, duplicated, weakly bounded, or not yet tested.
- **Fail:** cannot reliably trigger, execute, validate, or be installed; or creates material safety/integrity risk.

Do not collapse all dimensions into one opaque number. If a roll-up is requested, report the dimension scores and explain the weighting.

## Overlap analysis

Compare skills by:

1. user intent and trigger phrases;
2. input artifacts and file types;
3. primary actions and tool use;
4. output artifacts and schemas;
5. safety and approval boundaries;
6. likely handoff direction.

Classify pairs as `Distinct`, `Adjacent - define handoff`, `Overlapping - narrow`, or `Duplicate - merge candidate`. Prefer narrowing descriptions and documenting handoffs before merging packages.

## Remediation checklist

- Read the current file before patching.
- State exact files to change/create/delete.
- Preserve unrelated changes and original source artifacts.
- Fix trigger descriptions before adding body detail.
- Replace vague advice with decisions, defaults, statuses, and output contracts.
- Move long variant-specific content into one-level-deep references.
- Remove generated placeholders and broken links.
- Keep destructive or external actions behind explicit approval.
- Re-check metadata and all linked resources after editing.

## Release checklist

Before calling a skill release-ready:

1. Folder and frontmatter names match.
2. Frontmatter contains only `name` and `description`.
3. Description names concrete capabilities and triggers.
4. `agents/openai.yaml` is valid and aligned with the skill.
5. No accidental TODOs, broken links, or missing required resources remain.
6. Core workflow is concise and imperative.
7. Scope, safety, unknowns, and handoffs are explicit.
8. Output contract and completion criteria are testable.
9. Structural validator passes, or the dependency limitation is documented.
10. At least one realistic forward-test supports the skill's behavior when the skill is complex or high impact.
