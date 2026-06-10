# Project Brief: User Intent Taxonomy Proposal

## Project name
User Intent Taxonomy

## One-line summary
A proposed taxonomy family for standardizing **inferred posture from consumed content** across contextual targeting, inventory packaging, reporting, audience enrichment, and downstream ML workflows.

## Proposal summary

This repository is structured as a standards-facing proposal for adding **User Intent Taxonomies** as a new taxonomy family alongside existing IAB taxonomy families.

The proposal is intentionally additive:

- **Content taxonomy** describes what content is about
- **Audience taxonomy** describes the segment or user attribute being labeled
- **Ad product taxonomy** describes what product or service is being advertised
- **User intent taxonomy** describes what the user appears to be trying to do based on the content they are consuming

The core claim is that the industry still lacks a clean shared layer for classifying the **immediate or near-immediate inferred posture** implied by a page, query, snippet, or other observed content-consumption signal.

## The problem

Ad-tech systems can already classify:

- page aboutness
- audience segment resemblance
- advertised product family

What they do not standardize well is the likely user posture implied by the consumed content.

That gap matters because two records in the same topic can have very different operational meaning.

Examples:

- `how do electric cars work`
- `best suv lease deals near me`

Both may map to automotive content. They do not represent the same likely user posture.

Without an explicit intent layer, implementers are left to infer with proprietary logic:

- whether the user is learning, comparing, planning, booking, or seeking support
- whether the signal reflects commercial investigation or transaction readiness
- whether the signal should be used for activation, reporting, enrichment, or not at all

## Why this is not just another content taxonomy

The proposal is designed to classify **what the consumed content suggests the user may be trying to do right now**, not only what the content is about.

The distinction is:

- topic is not the same as intent
- behavior is not the same as domain
- research is not the same as readiness
- event-level posture is not the same as stable audience identity

## Proposed taxonomy structure

Version `1.0` is intentionally modular. The canonical normative assets live under `../User Intent Taxonomies/`.

The taxonomy family currently includes:

- `User Intent Taxonomy 1.0 - Intent Pattern.tsv`
- `User Intent Taxonomy 1.0 - Intent Domain.tsv`
- `User Intent Taxonomy 1.0 - Intent Modifier.tsv`
- `User Intent Taxonomy 1.0 - Intent Stage.tsv`
- `User Intent Taxonomy 1.0 - Intent Strength.tsv`
- `User Intent Taxonomy 1.0 - Commercial Readiness.tsv`
- `User Intent Taxonomy 1.0 - Actionability.tsv`
- `User Intent Taxonomy 1.0 - Performance Utility.tsv`
- `User Intent Taxonomy 1.0 - Classification Schema.tsv`

This design keeps behavior, domain, modifiers, readiness, and operational controls separate so they can be governed and implemented independently.

## Current repository layout

The repository is now organized as a proposal package:

- `../proposal.md`
- `../implementation.md`
- `../User Intent Taxonomies/`
- `../Taxonomy Mappings/`
- `../Examples/`
- `../Supporting Materials/`

### Normative artifacts

The candidate standard artifacts are the TSV files under:

- `../User Intent Taxonomies/`

### Informative artifacts

The explanatory and support material includes:

- `../proposal.md`
- `../implementation.md`
- `../Taxonomy Mappings/`
- `../Examples/`
- `../Supporting Materials/`

## What the taxonomy covers

The proposal supports classification of **inferred posture from consumed content** at:

- page level
- URL level
- query level
- snippet or excerpt level
- event level where the consumed content is known

It also supports:

- derived user-profile or segment mappings built from repeated classified signals over time

The important boundary is that the taxonomy primarily standardizes **event-level or content-level inferred posture**. User-profile use is supported as a downstream aggregation, not as the only primary unit of classification.

## Main dimensions

### Intent Pattern
What the user appears to be trying to do.

Examples:

- Research and Learning Intent
- Comparison Intent
- Lead Generation Intent
- Booking and Reservation Intent
- Ready to Buy Major Item
- Service and Support Intent

### Intent Domain
What area of life or commerce the inferred posture relates to.

Examples:

- Automotive
- Travel
- Insurance
- Financial Services
- Education
- Retail and Consumer Goods
- Business and B2B Solutions

### Intent Modifier
What traits sharpen the signal.

Examples:

- Deal Seeking
- Local
- Brand Focused
- Vendor Focused
- Urgency
- Budget Conscious

### Intent Stage
How far along the user appears to be.

Examples:

- Learning
- Comparison
- Evaluation
- Planning
- Ready to Act
- Acting
- Post Action

### Commercial Readiness
How commercially close the signal appears to be to action.

Examples:

- Non Commercial Informational
- Commercial Investigation
- Transaction Readiness
- Post Transaction

### Actionability and Performance Utility
Whether the signal should be used for activation and how useful it is for performance workflows.

## Why this matters

If standardized well, the taxonomy can make it easier to:

- distinguish informational from lower-funnel commercial posture within the same topic
- package inventory based on likely posture rather than topic alone
- support reporting by intent stage and readiness
- create more consistent ML labels across systems
- enrich audience or profile models with repeated event-level signals
- apply more explicit operational controls to sensitive or low-confidence cases

## Current supporting assets

The repository also includes:

- first-pass mappings under `../Taxonomy Mappings/`
- sample outputs under `../Examples/`
- supporting presentation and workbook material in this folder

These are intended to help reviewers assess both the conceptual case and the implementation shape.

## Likely reviewer concerns

Reviewers are likely to focus on:

- overlap with existing IAB taxonomy families
- whether "intent" is the right term
- boundaries between event-level posture and audience labeling
- implementation consistency across vendors
- sensitive-category and activation safeguards
- governance and versioning

The current package is structured to make those questions easier to review explicitly rather than burying them inside one large taxonomy file.

## Suggested review order

For a first review, use this order:

1. `../proposal.md`
2. `../User Intent Taxonomies/`
3. `../implementation.md`
4. `../Taxonomy Mappings/`
5. `../Examples/`
6. `../feedback.md`
7. `../Supporting Materials/`
