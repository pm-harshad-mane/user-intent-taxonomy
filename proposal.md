# Proposal: Add User Intent Taxonomies as a New IAB Taxonomy Family

## Proposal summary

This repository proposes a new taxonomy family, **User Intent Taxonomies**, to classify the likely posture inferred from the content a user is consuming.

The proposal is intentionally positioned as an addition to existing IAB taxonomy families, not a replacement for them.

The proposed taxonomy answers a different question than existing layers:

- **Content taxonomy**: what is the content about?
- **Audience taxonomy**: what kind of audience segment or attribute is being described?
- **Ad product taxonomy**: what product or service is being advertised?
- **User intent taxonomy**: what does the consumed content suggest the user may be trying to do right now?

## Definition

For this proposal, **user intent** means:

> the likely action posture or decision posture inferred from a piece of consumed content, a query, or another observed consumption signal

This proposal is not trying to infer stable identity traits. It is trying to standardize the language for the **state implied by observed consumption behavior**.

## The problem

Programmatic systems often distinguish content, audience, and product well enough to support targeting, reporting, and safety controls. What they still do not standardize cleanly is the **posture implied by content consumption**.

That gap matters because two pages within the same topic can imply very different commercial value.

Examples:

- `how do electric cars work`
- `best suv lease deals near me`

Both may be automotive content. They do not represent the same user intent.

Without an explicit intent layer, implementers are forced to infer:

- whether the user is learning or comparing
- whether the behavior suggests commercial investigation
- whether the signal is close enough to action to support activation
- whether the signal is useful for targeting, reporting, packaging, or only enrichment

## Why existing taxonomies are not enough

Existing IAB taxonomies remain necessary. This proposal does not duplicate them.

### Content taxonomy is not enough

Content taxonomy captures aboutness. It does not distinguish whether a user is learning, comparing providers, requesting a quote, planning a trip, or seeking support.

### Audience taxonomy is not enough

Audience taxonomy helps label segments or attributes. It does not provide a precise event- or page-level language for the immediate inferred intent from consumption.

### Ad product taxonomy is not enough

Ad product taxonomy describes what is being advertised. It does not describe the user-side commercial posture implied by the page or query.

## Proposed scope

The proposal covers standardized classification of **inferred posture from consumed content** for page-level, query-level, and content-derived use cases in digital advertising and adjacent systems.

### Intended units of classification

The proposed taxonomy is intended to support:

- page-level classification
- URL-level classification
- query-level classification
- snippet- or excerpt-level classification
- event-level content-consumption classification where the consumed content is known
- derived user-profile or segment mappings based on repeated classified signals

### Important distinction

The taxonomy is primarily designed for **event-level or content-level inferred posture**, not for long-lived user-profile labeling alone.

User-profile and audience-segment uses are in scope as **derived uses**. They should be constructed from repeated classified signals rather than treated as replacements for page-level or query-level labels.

### In scope

- behavioral intent patterns
- commercial or life domain context for the intent
- intent-sharpening modifiers
- journey stage
- intent strength
- commercial readiness
- actionability for activation
- performance utility for execution and reporting

### Out of scope

- replacing the content taxonomy
- replacing the audience taxonomy
- replacing the ad product taxonomy
- legal or policy adjudication by itself
- deterministic identity or user-profile claims
- prescribing platform-specific policy outcomes

## Why this should be a new taxonomy family

This proposal should be evaluated as a new taxonomy family rather than:

- a content taxonomy extension
- an audience taxonomy appendix
- an ad product taxonomy subclass

### Why not a content taxonomy extension

Content taxonomy is fundamentally about **what the content is about**. User intent taxonomy is about **what the user appears to be trying to do**. Treating behavioral posture as a topic branch would mix two different semantics into one hierarchy.

### Why not an audience taxonomy appendix

Audience taxonomy is useful for segment definition and user-attribute style labeling. This proposal is meant to standardize the immediate posture implied by observed content consumption and then support downstream user-profile aggregation.

### Why not an ad product taxonomy extension

Ad product taxonomy classifies the offer or product being advertised. User intent taxonomy classifies the consumer-side or business-buyer-side posture implied by the content being consumed.

The proposal therefore fills a different interoperability gap and is more coherent as its own taxonomy family.

## Design principles

### 1. Keep behavior separate from topic

`Comparison Intent` and `Automotive` should not live in the same category branch because one is a behavior and the other is a domain.

### 2. Keep the taxonomy modular

The proposal uses multiple related TSV files instead of one giant taxonomy. This improves governance, reuse, and interoperability.

### 3. Distinguish research from readiness

`Commercial Investigation` and `Transaction Readiness` are materially different states for activation, packaging, and reporting.

### 4. Include operational layers

The taxonomy does not stop at semantic labeling. It includes:

- `Actionability`
- `Performance Utility`
- `Commercial Readiness`

These dimensions make the taxonomy more useful in practical ad-tech systems.

### 5. Support both B2C and B2B

The proposal is meant to work across:

- retail and commerce
- local services
- travel
- education
- real estate
- finance and insurance
- business software and service evaluation

## Proposed taxonomy family

Version `1.0` is organized as the following normative files:

- `User Intent Taxonomy 1.0 - Intent Pattern.tsv`
- `User Intent Taxonomy 1.0 - Intent Domain.tsv`
- `User Intent Taxonomy 1.0 - Intent Modifier.tsv`
- `User Intent Taxonomy 1.0 - Intent Stage.tsv`
- `User Intent Taxonomy 1.0 - Intent Strength.tsv`
- `User Intent Taxonomy 1.0 - Commercial Readiness.tsv`
- `User Intent Taxonomy 1.0 - Actionability.tsv`
- `User Intent Taxonomy 1.0 - Performance Utility.tsv`
- `User Intent Taxonomy 1.0 - Classification Schema.tsv`

## Intended use cases

### Contextual targeting

Allow sellers, data providers, and buyers to distinguish informational content from commercial investigation and transaction-ready content within the same topic.

### Inventory packaging and PMP creation

Package inventory based not just on topic, but on inferred intent posture.

Examples:

- travel planning inventory
- automotive comparison inventory
- high-readiness local service inventory

### Reporting and analytics

Support distribution analysis across:

- informational vs commercial investigation vs transaction readiness
- early vs lower funnel behavior
- domain-specific intent patterns

### Audience enrichment and modeling

Use taxonomy outputs as standardized features or labels in downstream segmentation and modeling systems.

This includes derived user-profile and audience-style mappings built from repeated classified signals rather than one-off page classifications alone.

### Creative and performance strategy

Adjust messaging, bidding, and creative based on comparison, quote-seeking, deal-seeking, urgency, or support behavior.

## Why this belongs in an IAB taxonomy family

A taxonomy becomes worth standardizing when multiple participants need a common language for the same concept. This proposal is aimed at exactly that need.

Potential stakeholders include:

- publishers
- SSPs
- DSPs
- data providers
- commerce media platforms
- retail media networks
- measurement providers
- ML and classification teams

The taxonomy is useful because it can be used with existing IAB taxonomies rather than instead of them.

## Sensitive-category and activation safeguards

This proposal intentionally includes domains and use cases that can become sensitive in real deployment, including:

- finance
- insurance
- health care
- careers
- education
- parenting and family
- legal and compliance

The proposal therefore has to be interpreted with operational safeguards.

### Safeguard principles

1. The taxonomy is a classification language, not a policy override.
2. A valid taxonomy label does not automatically mean a signal should be activated.
3. Sensitive-domain use cases may require contextual-only use, stronger confidence thresholds, or reporting-only treatment.
4. User-profile derivation from repeated signals should be handled more conservatively than one-off contextual labeling.
5. Platform policy, law, contract terms, and geography-specific restrictions remain authoritative.

### Why safeguards are part of the proposal

The proposal includes:

- `Commercial Readiness`
- `Actionability`
- domain sensitivity flags

Those fields are part of the governance case for why this taxonomy can be evaluated responsibly rather than as an unconstrained targeting system.

## Governance and versioning

The proposal should follow a major/minor versioning approach:

- **major versions** for structural breaking changes
- **minor versions** for additive improvements that do not change core hierarchy semantics

Suggested initial version:

- `User Intent Taxonomy 1.0`

Suggested change classes:

- taxonomy row additions: minor
- description clarifications: minor
- hierarchy changes that alter meaning or compatibility: major
- schema field additions that are optional: minor
- schema changes that break implementers: major

## Review questions for industry experts

The proposal is structured to help reviewers focus on the most important questions:

1. Is the taxonomy solving a genuine interoperability problem?
2. Are the boundaries between user intent, content aboutness, audience, and ad product sufficiently clear?
3. Is the multi-file structure the right governance model?
4. Are the activation-related dimensions appropriate for an IAB taxonomy family?
5. Which mappings to existing IAB taxonomies would be most valuable first?

## Suggested path to industry review

### Phase 1: concept and scope review

Validate that the missing layer is real and that the proposed scope is properly bounded.

### Phase 2: taxonomy review

Review the actual TSV structures, hierarchy choices, naming conventions, and versioning approach.

### Phase 3: mapping and implementation review

Evaluate interoperability with content, audience, and ad product workflows.

### Phase 4: pilot implementation feedback

Collect real implementation feedback from publishers, SSPs, DSPs, contextual vendors, and data science teams.

## Included in this repository

This proposal repository includes:

- normative taxonomy files
- a classification schema
- first-pass mappings to existing IAB taxonomy families
- example classifications
- an external mapping template
- implementation guidance
- supporting materials preserved from the original working repository

The goal is to make expert review efficient without losing the detailed taxonomy work already completed.
