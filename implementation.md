# Implementation Guidance

## Purpose

This document explains how the proposed User Intent Taxonomies can be used in practical ad-tech, analytics, and ML workflows.

It is written to support evaluation by implementers, not just taxonomy reviewers.

## What this taxonomy is for

The taxonomy is intended to classify **inferred posture from consumed content**.

It supports several application levels:

- page-level classification
- URL-level classification
- query-level classification
- snippet- or excerpt-level classification
- event-level classification where the consumed content is known
- derived user-profile or segment mappings based on repeated classified signals

The key distinction is that the taxonomy primarily standardizes the **immediate or near-immediate inferred posture** of a content-consumption event or classified record. User-profile uses are supported, but they are downstream aggregations rather than the primary unit of application.

It is most useful when an implementer needs to answer:

- what the user appears to be trying to do
- how commercially meaningful the signal is
- whether the signal is suitable for activation
- how valuable the signal is for performance execution

## Recommended usage model

Use the taxonomy as a **multi-dimensional record**, not as a single label.

Recommended record components:

- `page_or_entity_id`
- `input_text`
- `primary_intent_pattern_id`
- `secondary_intent_pattern_ids`
- `intent_domain_id`
- `intent_modifier_ids`
- `intent_stage_id`
- `intent_strength_id`
- `commercial_readiness_id`
- `actionability_id`
- `performance_utility_id`
- `confidence_score`
- optional mapping fields
- optional rationale

The normative field list is defined in:

- `User Intent Taxonomies/User Intent Taxonomy 1.0 - Classification Schema.tsv`

## The taxonomy dimensions

### Intent Pattern

Answers:

> What is the user trying to do?

Examples:

- Purchase Intent
- Lead Generation Intent
- Booking and Reservation Intent
- Comparison Intent
- Research and Learning Intent
- Service and Support Intent

### Intent Domain

Answers:

> What area of commerce or life does the intent relate to?

Examples:

- Automotive
- Travel
- Insurance
- Financial Services
- Education
- Professional Services
- Business and B2B Solutions

### Intent Modifier

Answers:

> What traits sharpen or qualify the signal?

Examples:

- Deal Seeking
- Local
- Brand Focused
- Vendor Focused
- Urgency
- Budget Conscious

### Intent Stage

Answers:

> How far along is the user?

Examples:

- Learning
- Comparison
- Evaluation
- Planning
- Ready to Act
- Acting
- Post Action

### Intent Strength

Answers:

> How strong is the inferred signal?

Examples:

- Weak
- Moderate
- Strong
- Very Strong or Explicit

### Commercial Readiness

Answers:

> Is the user consuming information, investigating commercially, close to transacting, or already post-transaction?

Examples:

- Non Commercial Informational
- Commercial Investigation
- Transaction Readiness
- Post Transaction

### Actionability

Answers:

> Should this signal be used in activation?

Examples:

- Eligible
- Eligible With Strong Confidence Only
- Reporting Only
- Not Recommended For Activation

### Performance Utility

Answers:

> How valuable is the signal for campaign execution?

Examples:

- High
- Medium
- Low
- Primarily Analytical

## How to use with other taxonomy families

The taxonomy should be used alongside, not instead of, other standardized layers.

### With content taxonomy

Use content taxonomy to describe page aboutness and user intent taxonomy to describe likely user posture.

Example:

- Content: Automotive
- User Intent Pattern: Comparison Intent
- User Intent Stage: Comparison
- Commercial Readiness: Commercial Investigation

### With audience taxonomy

Use audience taxonomy when labeling segment definitions or user attributes. Use user intent taxonomy when labeling the immediate posture inferred from observed consumption.

User-profile and audience-style use cases are still in scope, but they should usually be built by aggregating repeated user intent classifications rather than by collapsing a single page or query into a stable audience label.

### With ad product taxonomy

Use ad product taxonomy to classify the advertised offer. Use user intent taxonomy to classify the commercial posture implied by the environment or consumption behavior.

## Comparison table

| Taxonomy family | Primary question answered | Typical unit of application | What it is best at | What it does not do well on its own |
| --- | --- | --- | --- | --- |
| Content | What is the content about? | Page, URL, article, video, section | Topic and aboutness classification | Immediate user posture, readiness, comparison state, urgency |
| Audience | What segment or user attribute is being described? | Audience segment, user cohort, profile | Segment definition, affinity, demographic or purchase-intent audience labeling | Event-level posture from one observed consumption moment |
| Ad Product | What product or service is being advertised? | Advertised offer, demand-side product classification | Offer and commercial product-family labeling | User-side research, evaluation, transaction readiness, or support state |
| User Intent | What does the consumed content suggest the user may be trying to do right now? | Query, page, snippet, event, and derived profile mappings | Behavioral posture, journey stage, readiness, actionability, performance utility | Replacing topic, audience, or advertised product classification |

## Recommended implementation patterns

### 1. Contextual targeting

Useful dimensions:

- Intent Pattern
- Intent Domain
- Intent Modifier
- Commercial Readiness
- Actionability

Example:

- `Automotive`
- `Ready to Buy Major Item`
- `Deal Seeking`
- `Local`
- `Transaction Readiness`
- `Eligible`

### 2. Inventory packaging and PMP creation

Useful dimensions:

- Intent Pattern
- Intent Domain
- Commercial Readiness
- Performance Utility
- Actionability

Example package concepts:

- Travel planning inventory
- Automotive comparison inventory
- High-readiness local service inventory

### 3. Reporting and insights

Useful dimensions:

- Intent Pattern
- Intent Domain
- Intent Stage
- Commercial Readiness
- Performance Utility

Reporting examples:

- share of inventory by informational vs commercial investigation vs transaction readiness
- share of inventory by upper vs lower funnel intent
- performance by modifier such as urgency or deal seeking

### 4. ML training and labeling

Useful dimensions:

- primary intent pattern
- secondary intent patterns
- domain
- modifiers
- stage
- readiness
- actionability
- confidence score

The multi-dimensional format is better suited to labeling pipelines than collapsing the task into a single class.

### 5. Derived user-profile and segment construction

Useful dimensions:

- repeated primary intent patterns over time
- repeated domains over time
- modifier frequency
- stage transitions
- commercial readiness distribution
- actionability thresholds
- confidence-weighted aggregation

Recommended principle:

- derive user-profile outputs from **multiple classified events**, not from a single page or query in isolation

Concrete examples:

- repeated `Comparison Intent` plus `Automotive` plus `Commercial Investigation` can support an automotive-intender profile feature
- repeated `Demo Request`, `Comparison Intent`, and `Business and B2B Solutions` can support a B2B software-buying committee signal
- repeated `Claim Complaint or Issue Resolution` or `Post Transaction` should usually be treated differently from acquisition-oriented profiles

## Example classifications

### Example 1

Input:

- `best suv lease deals near me`

Possible classification:

- Intent Pattern: Ready to Buy Major Item
- Intent Domain: Automotive
- Intent Modifiers: Deal Seeking, Local, Urgency, Budget Conscious
- Intent Stage: Ready to Act
- Intent Strength: Very Strong or Explicit
- Commercial Readiness: Transaction Readiness
- Actionability: Eligible
- Performance Utility: High

### Example 2

Input:

- `best crm for small sales team`

Possible classification:

- Intent Pattern: Comparison Intent
- Intent Domain: Business and B2B Solutions
- Intent Modifier: Vendor Focused
- Intent Stage: Comparison
- Intent Strength: Strong
- Commercial Readiness: Commercial Investigation
- Actionability: Eligible With Strong Confidence Only
- Performance Utility: Medium

### Example 3

Input:

- `how to file homeowners insurance claim`

Possible classification:

- Intent Pattern: Claim Complaint or Issue Resolution
- Intent Domain: Insurance
- Intent Stage: Post Action
- Intent Strength: Strong
- Commercial Readiness: Post Transaction
- Actionability: Eligible
- Performance Utility: Medium

### Example 4

Input:

- `how do electric cars work`

Possible classification:

- Intent Pattern: Introductory Learning
- Intent Domain: Automotive
- Intent Stage: Learning
- Intent Strength: Moderate
- Commercial Readiness: Non Commercial Informational
- Actionability: Reporting Only
- Performance Utility: Primarily Analytical

## Worked example: user-profile derivation

This example shows how repeated event-level classifications can be aggregated into a profile-style output without treating any one page as a stable user attribute.

### Observed classified events

Event 1:

- Input: `best hybrid suv for family of 5`
- Intent Pattern: `Comparison Intent`
- Intent Domain: `Automotive`
- Intent Stage: `Comparison`
- Commercial Readiness: `Commercial Investigation`
- Confidence: `0.86`

Event 2:

- Input: `best suv lease deals near me`
- Intent Pattern: `Ready to Buy Major Item`
- Intent Domain: `Automotive`
- Intent Modifiers: `Deal Seeking`, `Local`, `Urgency`, `Budget Conscious`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Confidence: `0.94`

Event 3:

- Input: `toyota highlander lease specials`
- Possible Intent Pattern: `Ready to Buy Major Item`
- Intent Domain: `Automotive`
- Intent Modifiers: `Deal Seeking`, `Brand Focused`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`

### Derived profile-style interpretation

Possible aggregated interpretation:

- repeated automotive demand signals
- progression from comparison to ready-to-act behavior
- strong lower-funnel automotive purchase posture
- price/value sensitivity
- likely suitability for an automotive in-market or automotive-intender derived segment

### Why this matters

This workflow preserves the distinction between:

- event-level classification
- profile-level aggregation

That distinction is important because the taxonomy is not claiming that one automotive page view creates a stable user profile. It provides the standardized language needed so repeated classified events can be aggregated consistently and transparently.

## Sensitive category and activation guidance

This taxonomy should not be interpreted as automatic permission to activate every signal.

Implementers should review:

- local law
- platform policy
- contractual restrictions
- company policy
- geography-specific regulatory requirements

Signals involving finance, insurance, health, education, family or child-related topics, or other sensitive areas may need more restrictive treatment.

Suggested principles:

- use `Actionability` to constrain activation
- use `Commercial Readiness` to separate learning from lower-funnel behavior
- use domain-level sensitivity indicators where appropriate
- require stronger confidence for higher-risk categories

## Mapping guidance

This repository includes:

- `Taxonomy Mappings/User Intent Taxonomy 1.0 - External Mapping Template.tsv`
- `Taxonomy Mappings/User Intent Taxonomy 1.0 - Mapping Principles.md`
- `Taxonomy Mappings/User Intent Taxonomy 1.0 to IAB Content Taxonomy 3.1.tsv`
- `Taxonomy Mappings/User Intent Taxonomy 1.0 to IAB Audience Taxonomy 1.1.tsv`
- `Taxonomy Mappings/User Intent Taxonomy 1.0 to IAB Ad Product Taxonomy 2.0.tsv`

These files support mappings to:

- IAB Content taxonomy
- IAB Audience taxonomy
- IAB Ad Product taxonomy
- proprietary internal classifications

## File format conventions

The taxonomy files use TSV format and relational hierarchy columns such as:

- `Unique ID`
- `Parent ID`
- `Name`
- `Tier 1`
- `Tier 2`
- `Tier 3`

Additional columns vary by file and may include:

- descriptions
- KPI alignment
- actionability defaults
- performance utility
- sensitivity flags

## What implementers should evaluate first

1. Does the taxonomy help distinguish intent states that your current systems flatten together?
2. Can your pipeline support multi-dimensional classification instead of one label?
3. Which dimensions should be activated, and which should remain reporting-only?
4. Which existing taxonomies should be mapped first for your workflow?

## Related materials

For additional context, see:

- `proposal.md`
- `Examples/`
- `Supporting Materials/project_brief.md`
- `Supporting Materials/User_Intent_Taxonomy_Overview.pdf`
