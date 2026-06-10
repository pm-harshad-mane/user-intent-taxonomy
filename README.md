# User Intent Taxonomy Proposal

This repository packages a proposed **User Intent Taxonomy** as a candidate addition to the IAB Tech Lab taxonomy family.

The proposal is designed to complement existing taxonomy layers rather than replace them:

- **Content taxonomy** describes what content is about
- **Audience taxonomy** describes the audience segment or user attribute being labeled
- **Ad product taxonomy** describes what product or service is being advertised
- **User intent taxonomy** describes what the user appears to be trying to do based on the content they are consuming

The central claim is that the ad industry still lacks a standard layer for classifying **inferred posture from consumed content**. That missing layer matters for contextual targeting, inventory packaging, audience enrichment, reporting, activation controls, and downstream ML classification.

## Review order

If you are reviewing this repository as a standards proposal, start here:

1. `proposal.md`
2. `User Intent Taxonomies/`
3. `implementation.md`
4. `Taxonomy Mappings/`
5. `Examples/`
6. `Supporting Materials/`

## Normative and informative materials

The proposed **normative** artifacts in this repository are:

- the TSV files under `User Intent Taxonomies/`

The **informative** artifacts are:

- `proposal.md`
- `implementation.md`
- `Taxonomy Mappings/`
- `Examples/`
- `Supporting Materials/`

The taxonomy TSVs are the candidate standard artifacts. The other documents explain scope, rationale, implementation patterns, example outputs, and supporting background.

## Repository structure

### `User Intent Taxonomies/`

Canonical taxonomy assets for version `1.0`.

- `User Intent Taxonomy 1.0 - Intent Pattern.tsv`
- `User Intent Taxonomy 1.0 - Intent Domain.tsv`
- `User Intent Taxonomy 1.0 - Intent Modifier.tsv`
- `User Intent Taxonomy 1.0 - Intent Stage.tsv`
- `User Intent Taxonomy 1.0 - Intent Strength.tsv`
- `User Intent Taxonomy 1.0 - Commercial Readiness.tsv`
- `User Intent Taxonomy 1.0 - Actionability.tsv`
- `User Intent Taxonomy 1.0 - Performance Utility.tsv`
- `User Intent Taxonomy 1.0 - Classification Schema.tsv`

This taxonomy is intentionally multi-file. It separates behavior, domain context, qualifiers, readiness, and operational utility so implementers can govern and use each layer independently.

### `Taxonomy Mappings/`

Contains crosswalk artifacts and mapping templates.

- `User Intent Taxonomy 1.0 - External Mapping Template.tsv`
- `User Intent Taxonomy 1.0 - Mapping Principles.md`
- `User Intent Taxonomy 1.0 to IAB Content Taxonomy 3.1.tsv`
- `User Intent Taxonomy 1.0 to IAB Audience Taxonomy 1.1.tsv`
- `User Intent Taxonomy 1.0 to IAB Ad Product Taxonomy 2.0.tsv`

This folder contains first-pass mappings between user intent and other IAB taxonomies such as Content, Audience, and Ad Product.

### `Examples/`

Illustrative sample classifications showing how the taxonomy can be applied to queries or content snippets.

- `sample_classifications.tsv`
- `sample_classifications.jsonl`
- `sample_classifications.md`

### `Supporting Materials/`

Reference and presentation material that supports the proposal but is not the normative taxonomy itself.

- `User_Intent_Taxonomy_Overview.pdf`
- `project_brief.md`
- `notebooklm_storyboard_input.md`
- `user_intent_taxonomy_framework_v0_3_master.xlsx`

## Core design principles

### 1. Separate intent from topic

Content topic and user intent are related but not identical.

Examples:

- `how do electric cars work` can be automotive content with informational intent
- `best hybrid suv for family of 5` can be automotive content with comparison intent
- `best suv lease deals near me` can be automotive content with high transaction readiness

### 2. Separate behavior from domain

The taxonomy keeps `what the user is trying to do` separate from `what category that intent applies to`.

Examples:

- `Comparison Intent` is a behavior pattern
- `Automotive` is a domain
- `Deal Seeking` is a modifier
- `Ready to Act` is a stage

### 3. Separate research from readiness

Commercial investigation and transaction readiness are not the same and should not be treated the same in performance systems.

### 4. Include operational controls

The proposal explicitly includes:

- `Actionability`
- `Performance Utility`
- `Commercial Readiness`

These dimensions are necessary because not every inferred signal should be activated directly.

### 5. Support both B2C and B2B use cases

The current taxonomy is built to cover consumer commerce, local services, finance, insurance, travel, education, real estate, and B2B software and service evaluation.

## What version 1.0 includes

Version `1.0` proposes a modular taxonomy composed of:

- Intent Pattern
- Intent Domain
- Intent Modifier
- Intent Stage
- Intent Strength
- Commercial Readiness
- Actionability
- Performance Utility
- Classification Schema

The intention is to propose this as a new taxonomy family that can sit alongside existing IAB taxonomy folders with its own versioning path.

## Classification scope

The taxonomy is intended to classify **inferred posture from consumed content** across several implementation levels.

Primary classification levels:

- page-level or URL-level context
- query-level input
- snippet- or excerpt-level text
- event-level consumption signals where the consumed content is known

Derived downstream uses:

- user-profile or segment mappings derived from repeated classified signals over time

The key distinction is that the taxonomy primarily standardizes the **immediate or near-immediate inferred posture** of a consumption event or classified record. User-profile uses are supported, but they are downstream aggregations rather than the primary unit of application.

## One worked example

Input:

- `best suv lease deals near me`

Illustrative output:

- Intent Pattern: `Ready to Buy Major Item`
- Intent Domain: `Automotive`
- Intent Modifiers: `Deal Seeking`, `Local`, `Urgency`, `Budget Conscious`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`
- Performance Utility: `High`

This illustrates why the taxonomy is distinct from topic-only classification. A content taxonomy can say the page is automotive. The User Intent Taxonomy can say the user appears close to a lower-funnel automotive action.

## What this repository is trying to prove

This repository is arranged to help reviewers answer five questions quickly:

1. Is there a genuine standards gap that existing IAB taxonomies do not already solve?
2. Is the proposed scope clear and bounded?
3. Is the taxonomy modular, governable, and implementation-friendly?
4. Can it coexist with existing content, audience, and ad product taxonomies?
5. Is there enough practical guidance and example material to evaluate real-world adoption?

## Key documents

- `proposal.md`: standards-facing rationale, scope, use cases, and governance framing
- `implementation.md`: practical guidance for using the taxonomy in ad-tech workflows
- `User Intent Taxonomies/`: normative taxonomy files
- `Taxonomy Mappings/`: mapping assets and templates
- `Examples/`: sample outputs

## Supporting materials

The following files are retained to preserve original detail and presentation material:

- `Supporting Materials/project_brief.md`
- `Supporting Materials/notebooklm_storyboard_input.md`
- `Supporting Materials/User_Intent_Taxonomy_Overview.pdf`
- `Supporting Materials/user_intent_taxonomy_framework_v0_3_master.xlsx`

## Proposal intent

This repository does not claim that the taxonomy is final. It is structured to make expert review easier by separating:

- the normative taxonomy files
- the proposal argument
- the implementation guidance
- the examples
- the supporting background material

That separation should make it easier to discuss the proposal with taxonomy experts, standards participants, SSPs, DSPs, data providers, publishers, and measurement or ML teams.
