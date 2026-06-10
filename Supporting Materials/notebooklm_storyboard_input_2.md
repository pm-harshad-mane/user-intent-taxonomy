# NotebookLM Storyboard Input 2: User Intent Taxonomy Proposal Package

## Purpose of this document

Use this document to generate:

- a sharper explainer narrative for standards reviewers
- a presentation storyboard for ad-tech and taxonomy experts
- executive summaries that reflect the current repository structure
- visuals that explain why User Intent should be evaluated as a new taxonomy family

This version is aligned to the current repository layout and proposal language.

## What this repository is now

This repository is not just a concept note. It is organized as a proposal package for adding **User Intent Taxonomies** as a new taxonomy family alongside existing IAB taxonomy families.

The current package is structured in layers:

- `README.md` explains the proposal at a high level
- `proposal.md` makes the standards-facing case
- `implementation.md` explains operational use
- `User Intent Taxonomies/` contains the candidate normative TSV files
- `Taxonomy Mappings/` contains first-pass crosswalks to existing IAB taxonomy families
- `Examples/` contains illustrative output records
- `Supporting Materials/` preserves background material and presentation assets
- `feedback.md` captures likely criticisms and skeptical review questions

## Core message

The ad industry already standardizes:

- what content is about
- what audience segment or user attribute is being labeled
- what product or service is being advertised

But it still does not standardize one important layer:

**What the consumed content suggests the user may be trying to do right now.**

This proposal introduces that missing layer as a structured, multi-file taxonomy family.

## The shortest possible explanation

**Topic is not the same as intent.**

Two pages may be about the same domain but imply very different user posture.

Example:

- `how do electric cars work`
- `best suv lease deals near me`

Both may be automotive content.

But they imply different posture:

- learning
- comparison
- transaction readiness

That distinction matters in:

- contextual targeting
- inventory packaging
- PMP creation
- reporting
- activation controls
- audience enrichment
- ML classification

## The proposal in one sentence

The proposal is for a taxonomy family that classifies **inferred posture from consumed content**, primarily at the page, query, snippet, or event level, while also supporting **derived user-profile mappings** built from repeated classified signals.

## The key distinction from existing taxonomy families

### Content taxonomy
Answers:

> What is the content about?

### Audience taxonomy
Answers:

> What segment or user attribute is being described?

### Ad product taxonomy
Answers:

> What product or service is being advertised?

### User intent taxonomy
Answers:

> What does the consumed content suggest the user may be trying to do right now?

## The big design idea

Do not force behavior, topic, stage, readiness, and activation controls into one giant hierarchy.

Instead, represent user intent as a **multi-dimensional record**.

## The version 1.0 taxonomy dimensions

1. **Intent Pattern**
What the user appears to be trying to do

2. **Intent Domain**
What area of life or commerce the behavior applies to

3. **Intent Modifier**
What traits sharpen the signal

4. **Intent Stage**
Where the user appears to be in the journey

5. **Intent Strength**
How strong the inferred signal appears to be

6. **Commercial Readiness**
Whether the posture is informational, commercially investigative, transaction-ready, or post-transaction

7. **Actionability**
Whether the signal should be used in activation

8. **Performance Utility**
How useful the signal is for performance execution or analytics

9. **Classification Schema**
How the record is represented in a normalized output

## Why this is designed as multiple TSVs

This proposal intentionally separates:

- behavior from domain
- posture from topic
- readiness from generic funnel labels
- operational controls from semantic labels

That modular design is part of the governance case. It allows independent evolution, cleaner mappings, and more explicit implementation choices.

## The review story

If presenting this proposal to ad-industry experts, the narrative should move in this order:

### 1. Show the gap

Current taxonomy families are useful, but none of them directly standardize inferred posture from consumed content.

### 2. Show why that gap matters

Without a shared language for posture, different participants use inconsistent or proprietary logic for:

- research vs readiness
- comparison vs purchase
- support vs acquisition
- reporting-only vs activation-worthy signals

### 3. Show the proposed answer

Introduce User Intent as a modular taxonomy family rather than a topic extension.

### 4. Show that the proposal is bounded

Make clear that this is not:

- a replacement for content taxonomy
- a replacement for audience taxonomy
- a replacement for ad product taxonomy
- an identity system
- a policy engine

### 5. Show that safeguards are built in

Point out:

- `Actionability`
- `Commercial Readiness`
- sensitivity flags in domains
- profile derivation treated more conservatively than one-off event labeling

### 6. Show that the package is implementation-ready

Highlight:

- normative TSVs
- classification schema
- first-pass mappings
- examples
- implementation guidance

## Suggested storyboard structure

## Panel 1: The missing layer

Headline:
**The industry classifies topic, audience, and product. It does not yet standardize user posture.**

Visual:

Three existing layers:

- Content
- Audience
- Ad Product

And a highlighted fourth layer:

- User Intent

Key message:

**User intent is the missing interoperable layer.**

## Panel 2: Topic is not intent

Headline:
**Two records can share a topic and still imply different user posture**

Visual:

Two example cards:

- `how do electric cars work`
- `best suv lease deals near me`

Both tagged:

- Domain: Automotive

Then show the difference:

- Research and Learning Intent
- Ready to Buy Major Item

Key message:

**Topic alone hides commercial and behavioral differences that matter operationally.**

## Panel 3: The new taxonomy family

Headline:
**A modular framework for inferred posture from consumed content**

Visual:

Nine tiles or a circular framework:

- Intent Pattern
- Intent Domain
- Intent Modifier
- Intent Stage
- Intent Strength
- Commercial Readiness
- Actionability
- Performance Utility
- Classification Schema

Key message:

**Intent becomes clearer when behavior, domain, readiness, and operational controls are separated.**

## Panel 4: How it complements existing taxonomies

Headline:
**User Intent works with Content, Audience, and Ad Product, not instead of them**

Visual:

A one-page comparison table using these columns:

- Taxonomy family
- Primary question answered
- Typical unit of application
- What it is best at

Suggested row summaries:

- Content: aboutness
- Audience: segment or user attribute labeling
- Ad Product: advertised offer classification
- User Intent: immediate or near-immediate inferred posture

Key message:

**This is an additive taxonomy family with a different semantic job.**

## Panel 5: Practical outputs

Headline:
**A classified record can be more useful than a topic label alone**

Visual example:

Input:

- `best suv lease deals near me`

Illustrative record:

- Intent Pattern: `Ready to Buy Major Item`
- Intent Domain: `Automotive`
- Intent Modifiers: `Deal Seeking`, `Local`, `Urgency`, `Budget Conscious`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`
- Performance Utility: `High`

Key message:

**The taxonomy expresses posture, not just subject matter.**

## Panel 6: Derived user-profile use

Headline:
**User-profile use is possible, but only as a downstream aggregation**

Visual:

Several event-level records over time feeding into a derived audience-style profile signal.

Events:

- electric vehicle comparison article
- SUV financing calculator
- local dealer search
- lease offers page

Derived interpretation:

- repeated automotive lower-funnel behavior

Key message:

**The taxonomy is event-first, but repeated classified signals can support profile or segment mappings.**

## Panel 7: Safeguards

Headline:
**Useful does not mean unrestricted**

Visual:

Boxes labeled:

- Sensitive domains
- Actionability controls
- Reporting-only use
- Strong-confidence thresholds
- Platform policy still applies

Key message:

**A valid taxonomy label is not an automatic activation decision.**

## Panel 8: Why this is proposal-ready

Headline:
**This is structured as a standards proposal, not just a conceptual framework**

Visual:

Repository map:

- `proposal.md`
- `User Intent Taxonomies/`
- `implementation.md`
- `Taxonomy Mappings/`
- `Examples/`
- `feedback.md`

Key message:

**The package includes the normative assets, implementation guidance, examples, mappings, and reviewer-prep materials needed for serious evaluation.**

## Suggested voice and framing

Use language that feels:

- standards-oriented
- precise
- skeptical-reader friendly
- operational rather than promotional

Avoid framing that sounds like:

- a product pitch
- a proprietary scoring system
- a replacement for existing IAB taxonomies

Prefer framing that sounds like:

- a bounded interoperability proposal
- a missing semantic layer
- a modular classification standard

## Important reviewer concerns to acknowledge directly

Any generated summary or storyboard should explicitly acknowledge likely concerns:

- Is a new taxonomy family really necessary?
- Is "intent" the right term?
- How is this different from Audience Taxonomy purchase-intent segments?
- How are sensitive domains handled?
- Can different vendors classify consistently?
- Is user-profile derivation sufficiently constrained?
- What is the minimum viable implementation?

These concerns should appear as part of the narrative, not be hidden.

## Recommended repo files to cite in summaries

When generating derivative assets, treat these files as the primary current sources:

- `../README.md`
- `../proposal.md`
- `../implementation.md`
- `../feedback.md`
- `../User Intent Taxonomies/`
- `../Taxonomy Mappings/`
- `../Examples/`

Use the older supporting files in this folder as historical or presentation context, not as the primary description of the current package.
