# User Intent Taxonomy

<img width="2752" height="1536" alt="unnamed (6)" src="https://github.com/user-attachments/assets/c4bed028-5026-4c15-bb03-dd7b235c6824" />

**Presentation Deck:** [User Intent Taxonomy Deck](./User_Intent_Taxonomy.pdf) (Download to view)


A taxonomy framework for standardizing **user intent inferred from consumed content**, designed for use in **programmatic advertising, contextual targeting, performance campaign execution, audience enrichment, reporting, deal packaging, and downstream ML classification**.

This repository contains a **multi-dimensional user intent framework** rather than a single flat taxonomy. It separates:

- **Intent Pattern**: what the user is trying to do
- **Intent Domain**: what category or vertical the intent applies to
- **Intent Modifier**: overlays that sharpen intent
- **Intent Stage**: where the user is in the journey
- **Intent Strength**: how strong the inferred intent is
- **Commercial Readiness**: whether the behavior looks informational, investigative, ready-to-transact, or post-transaction
- **Actionability**: whether the signal should be used for activation
- **Performance Utility**: how useful the signal is for campaign execution

The framework was created to address a gap in current ad-tech standards: existing taxonomies usually help classify **what content is about** or **what audience a user resembles**, but do not cleanly standardize **what the user may be trying to do right now**.

---

## Why this repository exists

In programmatic advertising, common classification layers already exist:

- **Content taxonomies** classify the subject matter of content
- **Audience taxonomies** classify users or user cohorts
- **Ad product taxonomies** classify products, services, or commercial entities

Those are useful, but they do not directly answer questions like:

- Is this user **just learning**, or are they **comparing options**?
- Is this page showing **commercial investigation** or **transaction readiness**?
- Is the user likely trying to **buy**, **book**, **request a quote**, **submit a lead**, **renew**, or **get support**?
- Is the signal useful for **activation**, or only for **reporting and enrichment**?

This repository provides a structure to answer those questions consistently.

---

## Design principles

### 1. Separate intent from topic
A user reading content about **automotive** is not necessarily showing the same behavior.

Examples:
- `History of electric vehicles` → topic is automotive, intent may be informational
- `Best SUVs for families` → topic is automotive, intent may be comparison
- `Toyota Highlander lease deals near me` → topic is automotive, intent may be purchase / quote / local / deal-seeking

### 2. Separate intent pattern from vertical
Some categories are better modeled as **behaviors**, while others are better modeled as **domains**.

Examples:
- `Comparison` is a pattern
- `Travel` is a domain
- `Deal Seeking` is a modifier
- `Ready to Act` is a stage

This keeps the framework consistent and more useful for activation.

### 3. Not every signal should be activated
Some inferred intent is suitable for targeting, while some is only useful for:
- reporting
- enrichment
- analytics
- creative strategy
- contextual packaging

That is why the repository includes:
- **Actionability**
- **Performance Utility**

### 4. Separate research from readiness
A key requirement for performance campaigns is to distinguish:
- **Commercial Investigation**
- **Transaction Readiness**

These are not the same and should not be optimized the same way.

### 5. Support both B2C and B2B
The framework supports:
- consumer commerce
- local and service businesses
- finance and insurance
- travel and bookings
- retention and support
- B2B SaaS / software / infrastructure / services

### 6. Keep files modular
The repository intentionally uses multiple files instead of one giant file. Each file represents a separate, reusable taxonomy or schema component.

---

## Repository structure

### Core taxonomy files

#### `intent_pattern_taxonomy.tsv`
Defines the primary **behavioral intent patterns**.

Examples:
- Purchase Intent
- Lead Generation Intent
- Booking and Reservation Intent
- Comparison Intent
- Review and Validation Intent
- Research and Learning Intent
- Service and Support Intent

Use this file when you want to answer:
> What is the user trying to do?

---

#### `intent_domain_taxonomy.tsv`
Defines the **domain / vertical context** for the intent.

Examples:
- Automotive
- Travel
- Insurance
- Financial Services
- Real Estate
- Technology
- Business and B2B Solutions

Use this file when you want to answer:
> What area of commerce or life does this intent relate to?

---

#### `intent_modifier_taxonomy.tsv`
Defines overlays that sharpen or contextualize intent but should not usually be top-level patterns.

Examples:
- Deal Seeking
- Local
- Brand Focused
- Vendor Focused
- Urgency
- Budget Conscious
- Upgrade Oriented
- Switching Oriented

Use this file when you want to answer:
> What additional traits make this intent more actionable or specific?

---

### Companion classification dimensions

#### `intent_stage_taxonomy.tsv`
Defines where the user appears to be in the journey.

Examples:
- Passive
- Exploration
- Learning
- Comparison
- Evaluation
- Planning
- Selection
- Ready to Act
- Acting
- Post Action

Use this file when you want to answer:
> How far along is the user?

---

#### `intent_strength_taxonomy.tsv`
Defines how strong the inferred signal is.

Examples:
- Weak
- Moderate
- Strong
- Very Strong or Explicit

Use this file when you want to answer:
> How confident are we in the intent strength itself?

---

#### `commercial_readiness_taxonomy.tsv`
Separates informational consumption from commercially actionable behavior.

Examples:
- Non Commercial Informational
- Commercial Investigation
- Transaction Readiness
- Post Transaction

Use this file when you want to answer:
> Is the user just learning, evaluating commercially, or close to acting?

---

#### `actionability_taxonomy.tsv`
Defines whether the signal is appropriate for activation.

Examples:
- Eligible
- Eligible With Strong Confidence Only
- Reporting Only
- Not Recommended For Activation

Use this file when you want to answer:
> Should this signal be used in targeting / optimization?

---

#### `performance_utility_taxonomy.tsv`
Defines the likely value of the signal for performance execution.

Examples:
- High
- Medium
- Low
- Primarily Analytical

Use this file when you want to answer:
> How valuable is this signal for campaign execution?

---

### Schema and mapping files

#### `classification_schema.tsv`
Defines a normalized output schema for page-level or user-level classification.

This is the file that ties all the separate dimensions together into one record structure.

Use this when you want to:
- store classifications
- build APIs
- log model output
- persist page-level or user-level intent labels

---

#### `mapping_template.tsv`
A template for mapping the framework to external standards and internal systems.

Use this when you want to:
- map to IAB Content Taxonomy
- map to IAB Audience Taxonomy
- map to IAB Ad Product Taxonomy
- store crosswalks to proprietary taxonomies

---

### Workbook

#### `user_intent_taxonomy_framework_v0_3_master.xlsx`
An Excel workbook containing all major taxonomy files in one place for:
- review
- collaboration
- bulk editing
- sharing with non-technical stakeholders

This is useful for product, strategy, sales, operations, and standards review.

---

## Why we have multiple files

This repository deliberately uses multiple files because the framework is **multi-dimensional**.

A single file would make it harder to:
- reuse individual dimensions independently
- govern changes cleanly
- map dimensions to different systems
- evolve one taxonomy without rewriting everything else
- support different activation use cases

### Example
A campaign system might need only:
- `intent_pattern_taxonomy.tsv`
- `intent_domain_taxonomy.tsv`
- `intent_stage_taxonomy.tsv`
- `actionability_taxonomy.tsv`

A reporting pipeline might use:
- `intent_pattern_taxonomy.tsv`
- `intent_domain_taxonomy.tsv`
- `performance_utility_taxonomy.tsv`
- `mapping_template.tsv`

An ML labeling workflow might emphasize:
- `intent_pattern_taxonomy.tsv`
- `intent_modifier_taxonomy.tsv`
- `commercial_readiness_taxonomy.tsv`
- `intent_strength_taxonomy.tsv`

Keeping files separate makes the framework more modular and practical.

---

## Example: how the framework works

## Example 1: “best suv lease deals near me”

Possible classification:

- **Intent Pattern**: Ready to Buy Major Item
- **Intent Domain**: Automotive
- **Intent Modifiers**:
  - Deal Seeking
  - Local
  - Urgency
  - Budget Conscious
- **Intent Stage**: Ready to Act
- **Intent Strength**: Very Strong or Explicit
- **Commercial Readiness**: Transaction Readiness
- **Actionability**: Eligible
- **Performance Utility**: High

Why:
- `lease deals` suggests pricing and transaction behavior
- `near me` suggests local conversion intent
- the wording is not just informational; it is lower-funnel

---

## Example 2: “best crm for small sales team”

Possible classification:

- **Intent Pattern**: Comparison Intent
- **Intent Domain**: Business and B2B Solutions
- **Intent Modifiers**:
  - Vendor Focused
- **Intent Stage**: Comparison
- **Intent Strength**: Strong
- **Commercial Readiness**: Commercial Investigation
- **Actionability**: Eligible With Strong Confidence Only
- **Performance Utility**: Medium

Why:
- user is comparing vendors
- this is B2B solution evaluation
- it is valuable, but not necessarily immediate transaction intent

---

## Example 3: “how to file an auto insurance claim”

Possible classification:

- **Intent Pattern**: Claim Complaint or Issue Resolution
- **Intent Domain**: Insurance
- **Intent Stage**: Post Action
- **Intent Strength**: Strong
- **Commercial Readiness**: Post Transaction
- **Actionability**: Eligible
- **Performance Utility**: Medium
- **Sensitive Category Flag**: Potentially sensitive
- **Allowed Activation Scope**: Contextual only

Why:
- the user likely already has a policy
- this is service/support behavior, not acquisition
- sensitivity controls may apply

---

## Example 4: “how do electric cars work”

Possible classification:

- **Intent Pattern**: Introductory Learning
- **Intent Domain**: Automotive
- **Intent Stage**: Learning
- **Intent Strength**: Moderate
- **Commercial Readiness**: Non Commercial Informational
- **Actionability**: Reporting Only
- **Performance Utility**: Primarily Analytical

Why:
- topic is automotive, but the behavior is informational
- not enough evidence of purchase or comparison intent

---

## Example 5: “best daycare near me with extended hours”

Possible classification:

- **Intent Pattern**: Provider Comparison
- **Intent Domain**: Parenting and Family
- **Intent Modifiers**:
  - Local
  - Urgency
- **Intent Stage**: Evaluation
- **Intent Strength**: Strong
- **Commercial Readiness**: Commercial Investigation
- **Actionability**: Eligible With Strong Confidence Only
- **Performance Utility**: Medium

Why:
- provider comparison is explicit
- local qualifier strengthens actionability
- service need is clear, but policy and sensitivity review may be needed by platform or market

---

## Example 6: “salesforce pricing enterprise”

Possible classification:

- **Intent Pattern**: Loan or Financing Quote is **not** correct  
  Better classification:
- **Intent Pattern**: Price and Value Comparison or Requesting Custom Estimate (depending on page context)
- **Intent Domain**: Business and B2B Solutions
- **Intent Modifiers**:
  - Vendor Focused
- **Intent Stage**: Evaluation or Ready to Act
- **Intent Strength**: Strong
- **Commercial Readiness**: Transaction Readiness
- **Actionability**: Eligible
- **Performance Utility**: High
- **Lead Gen Relevance**: High

Why:
- pricing pages often indicate lower-funnel B2B evaluation
- for B2B, pricing and demo pages often sit very close to lead generation

---

## Suggested usage patterns

### 1. Contextual targeting
Use:
- Intent Pattern
- Intent Domain
- Intent Modifier
- Commercial Readiness
- Actionability

Example:
Target pages where:
- Intent Pattern is `Purchase Intent` or `Quote and Estimate Intent`
- Domain is `Automotive`
- Commercial Readiness is `Transaction Readiness`
- Actionability is `Eligible`

---

### 2. Deal packaging / PMP creation
Use:
- Intent Pattern
- Intent Domain
- Performance Utility
- Actionability
- Mapping template

Example:
Build a PMP around:
- `Comparison Intent`
- `Business and B2B Solutions`
- `Vendor Focused`
- `Commercial Investigation`
- `Performance Utility = Medium or High`

---

### 3. Reporting and insights
Use:
- Intent Pattern
- Intent Domain
- Stage
- Commercial Readiness
- Performance Utility

Example:
Report how content inventory breaks down by:
- informational vs commercial investigation vs transaction readiness
- upper / mid / lower funnel intent stages
- domain distribution

---

### 4. ML training and labeling
Use:
- Pattern taxonomy
- Domain taxonomy
- Modifier taxonomy
- Stage taxonomy
- Strength taxonomy
- Classification schema

This supports:
- hierarchical labeling
- structured inference output
- consistency across human labels and model predictions

---

## File format conventions

All taxonomy files are TSV-based and use a relational hierarchy style with fields such as:

- `Unique ID`
- `Parent ID`
- `Name`
- `Tier 1`
- `Tier 2`
- `Tier 3`

Additional columns may include:
- descriptions
- default actionability
- performance utility
- sensitive category flags
- B2B / B2C designation
- KPI alignment

This format is intentionally easy to:
- version in Git
- diff in pull requests
- load into spreadsheets
- import into data pipelines
- map into databases

---

## Governance recommendations

If this repository evolves into a shared standard, it is worth adopting governance rules such as:

### Versioning
Use semantic or staged versions:
- `v0.1` exploratory
- `v0.2` normalized naming and schema
- `v0.3` multi-dimensional framework
- future stable releases as `v1.0+`

### Change control
Track changes to:
- taxonomy nodes
- IDs
- descriptions
- deprecations
- mappings

### Stability rules
- avoid reusing retired IDs
- prefer additive changes over destructive renames
- maintain mapping history where possible

### Review lenses
Changes should ideally be reviewed through multiple lenses:
- ad-tech activation
- performance execution
- privacy / policy
- ML labeling consistency
- analytics usability

---

## Recommended next steps for this repo

Possible future additions:

- example page-to-taxonomy mappings
- inference guidelines per node
- positive / negative signal lexicons
- confidence calibration guidance
- sample JSON outputs
- benchmark datasets
- mappings to specific IAB node IDs
- governance and contribution guidelines
- changelog

---

## Suggested repo additions

You may eventually want to add:

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `docs/`
- `examples/`
- `mappings/`
- `schemas/`
- `samples/`

Example layout:

```text
user-intent-taxonomy/
├── README.md
├── CHANGELOG.md
├── intent_pattern_taxonomy.tsv
├── intent_domain_taxonomy.tsv
├── intent_modifier_taxonomy.tsv
├── intent_stage_taxonomy.tsv
├── intent_strength_taxonomy.tsv
├── commercial_readiness_taxonomy.tsv
├── actionability_taxonomy.tsv
├── performance_utility_taxonomy.tsv
├── classification_schema.tsv
├── mapping_template.tsv
├── user_intent_taxonomy_framework_v0_3_master.xlsx
└── examples/
```


---

## What this framework is not

To help programmatic technology providers evaluate the framework correctly, it is important to clarify what this repository does **not** aim to do.

This framework is **not**:

- **A replacement for IAB Content Taxonomy**  
  Content taxonomies classify what content is about. This framework classifies what the user may be trying to do while consuming that content.

- **A replacement for audience taxonomies**  
  Audience taxonomies help describe users, cohorts, or segment eligibility. This framework focuses on inferred intent from content consumption context.

- **A replacement for conversion event schemas**  
  This framework does not replace event tracking such as purchases, leads, bookings, subscriptions, add-to-cart events, or application submissions. It complements those schemas by providing inferred pre-conversion or post-conversion intent signals.

- **A deterministic truth layer**  
  Intent inferred from consumed content is probabilistic. It should be treated as a signal, not as guaranteed user truth.

- **A policy framework**  
  This repository includes sensitivity and activation-related concepts, but it does not define legal, regulatory, or platform policy requirements. Implementers must apply their own privacy, compliance, and policy controls.

- **An identity graph or user identity standard**  
  This framework can be used at page level, URL level, session level, or user-profile level, but it does not define identity resolution, person-level matching, or graph construction.

- **A guarantee of activation eligibility**  
  Even if a classification appears commercially valuable, that does not mean it should automatically be made targetable in every market, platform, or product environment.

---

## Implementation guidance

Below are practical recommendations for providers implementing this framework in SSPs, DSPs, contextual engines, publisher systems, analytics pipelines, or internal data platforms.

### 1. Keep pattern and domain separate
Do not collapse vertical and behavior into one label if you can avoid it.

Preferred:
- Intent Pattern = `Comparison Intent`
- Intent Domain = `Automotive`

Avoid:
- A single custom merged label such as `Automotive Comparison Intent` unless it is only used as a derived segment label.

### 2. Use modifiers as overlays
Modifiers such as:
- `Deal Seeking`
- `Local`
- `Vendor Focused`
- `Brand Focused`
- `Urgency`

should usually sit alongside the primary classification, not replace it.

### 3. Always store confidence
A classification record should include:
- primary intent
- optional secondary intent(s)
- confidence score
- stage
- commercial readiness
- actionability

This makes the signal far more usable in downstream systems.

### 4. Allow primary and secondary intent
Many pages naturally express multiple signals.

Recommended approach:
- **1 primary intent pattern**
- **up to 2 secondary intent patterns**
- **1 primary intent domain**
- **0 to N modifiers**

### 5. Use actionability before activation
Do not expose every inferred intent directly to targeting or bidding systems.

Recommended filtering logic:
- `Eligible` → usable with normal safeguards
- `Eligible With Strong Confidence Only` → usable only with stricter thresholds or corroboration
- `Reporting Only` → analytics, packaging, enrichment
- `Not Recommended For Activation` → no direct activation

### 6. Distinguish research from readiness
A provider should not treat all commercial-looking content as equal.

Examples:
- `best CRM for small business` → likely **Commercial Investigation**
- `HubSpot pricing enterprise` → may indicate **Transaction Readiness**
- `how CRM works` → likely **Non Commercial Informational** or early investigation

### 7. Handle sensitive domains carefully
Signals in healthcare, insurance, financial services, legal, career, family, support communities, or similar areas may require stricter controls.

A practical implementation should support:
- sensitivity flags
- activation restrictions
- contextual-only availability where needed
- reporting-only fallback where appropriate

### 8. Start simple
A first implementation does not need every taxonomy dimension.

A good minimum implementation can begin with:
- Intent Pattern
- Intent Domain
- Intent Stage
- Commercial Readiness
- Actionability
- Confidence Score

Then add modifiers, strength, and performance utility later.

---

## Common examples by vertical

These examples show how the same framework can apply across common programmatic verticals.

### Automotive

**Example query/content:** `best suv lease deals near me`

Possible classification:
- Intent Pattern: `Purchase Intent`
- Intent Domain: `Automotive`
- Modifiers: `Deal Seeking`, `Local`, `Budget Conscious`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`

**Example query/content:** `best hybrid suv for family of 5`

Possible classification:
- Intent Pattern: `Comparison Intent`
- Intent Domain: `Automotive`
- Modifiers: `Brand Focused` may be absent
- Intent Stage: `Comparison`
- Commercial Readiness: `Commercial Investigation`
- Actionability: `Eligible With Strong Confidence Only`

### Travel

**Example query/content:** `cheap flights to las vegas this weekend`

Possible classification:
- Intent Pattern: `Booking and Reservation Intent`
- Intent Domain: `Travel`
- Modifiers: `Deal Seeking`, `Urgency`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`

**Example query/content:** `things to do in napa valley with kids`

Possible classification:
- Intent Pattern: `Planning Intent`
- Intent Domain: `Travel`
- Modifiers: may include `Local` depending on context
- Intent Stage: `Planning`
- Commercial Readiness: `Commercial Investigation`
- Actionability: `Eligible With Strong Confidence Only`

### Finance

**Example query/content:** `best credit cards for travel rewards`

Possible classification:
- Intent Pattern: `Comparison Intent`
- Intent Domain: `Financial Services`
- Intent Stage: `Comparison`
- Commercial Readiness: `Commercial Investigation`
- Actionability: `Eligible With Strong Confidence Only`
- Sensitive Category Flag: `Potentially sensitive`

**Example query/content:** `mortgage refinance rates today`

Possible classification:
- Intent Pattern: `Quote and Estimate Intent`
- Intent Domain: `Real Estate`
- Modifiers: `Urgency`, `Budget Conscious`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`
- Sensitive Category Flag: `Potentially sensitive`

### Insurance

**Example query/content:** `compare auto insurance quotes online`

Possible classification:
- Intent Pattern: `Quote and Estimate Intent`
- Intent Domain: `Insurance`
- Modifiers: `Vendor Focused`, `Budget Conscious`
- Intent Stage: `Comparison` or `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`

**Example query/content:** `how to file homeowners insurance claim`

Possible classification:
- Intent Pattern: `Service and Support Intent`
- Intent Domain: `Insurance`
- Intent Stage: `Post Action`
- Commercial Readiness: `Post Transaction`
- Actionability: `Eligible`
- Allowed Activation Scope: `Contextual only`

### Retail and Commerce

**Example query/content:** `best espresso machine under 300`

Possible classification:
- Intent Pattern: `Comparison Intent`
- Intent Domain: `Retail and Consumer Goods`
- Modifiers: `Budget Conscious`
- Intent Stage: `Evaluation`
- Commercial Readiness: `Commercial Investigation`
- Actionability: `Eligible With Strong Confidence Only`

**Example query/content:** `buy running shoes online free shipping`

Possible classification:
- Intent Pattern: `Purchase Intent`
- Intent Domain: `Retail and Consumer Goods`
- Modifiers: `Deal Seeking`
- Intent Stage: `Acting`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`

### B2B SaaS and enterprise technology

**Example query/content:** `best crm for small sales team`

Possible classification:
- Intent Pattern: `Comparison Intent`
- Intent Domain: `Business and B2B Solutions`
- Modifiers: `Vendor Focused`
- Intent Stage: `Comparison`
- Commercial Readiness: `Commercial Investigation`
- Actionability: `Eligible With Strong Confidence Only`

**Example query/content:** `salesforce demo request`

Possible classification:
- Intent Pattern: `Lead Generation Intent`
- Intent Domain: `Business and B2B Solutions`
- Modifiers: `Vendor Focused`
- Intent Stage: `Acting`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`

### Home services

**Example query/content:** `emergency plumber near me open now`

Possible classification:
- Intent Pattern: `Lead Generation Intent`
- Intent Domain: `Professional Services`
- Modifiers: `Local`, `Urgency`
- Intent Stage: `Ready to Act`
- Commercial Readiness: `Transaction Readiness`
- Actionability: `Eligible`

### Education

**Example query/content:** `best online mba programs`

Possible classification:
- Intent Pattern: `Comparison Intent`
- Intent Domain: `Education`
- Intent Stage: `Comparison`
- Commercial Readiness: `Commercial Investigation`
- Actionability: `Eligible With Strong Confidence Only`

### Telecom

**Example query/content:** `best family mobile plans`

Possible classification:
- Intent Pattern: `Comparison Intent`
- Intent Domain: `Telecom and Utilities`
- Modifiers: `Budget Conscious`
- Intent Stage: `Evaluation`
- Commercial Readiness: `Commercial Investigation`
- Actionability: `Eligible With Strong Confidence Only`

---

## Recommended activation rules

These are suggested operational rules for using the framework in programmatic systems.

### Rule 1: prioritize lower-funnel patterns
Patterns such as:
- `Purchase Intent`
- `Lead Generation Intent`
- `Booking and Reservation Intent`
- `Quote and Estimate Intent`
- `Retention and Renewal Intent`

are generally stronger candidates for activation than:
- `Research and Learning Intent`
- `Passive or Ambiguous Intent`

### Rule 2: combine dimensions before targeting
Do not activate based on a single field alone when stronger combinations are available.

Preferred activation logic example:
- Intent Pattern = `Purchase Intent`
- Intent Domain = `Automotive`
- Commercial Readiness = `Transaction Readiness`
- Actionability = `Eligible`
- Confidence Score >= threshold

### Rule 3: use stricter thresholds for mid-funnel patterns
Patterns like:
- `Comparison Intent`
- `Review and Validation Intent`
- `Planning Intent`
- `Research and Learning Intent`

should usually require:
- stronger confidence
- strong modifier support
- domain relevance
- or packaging/reporting use instead of direct activation

### Rule 4: modifiers can raise or sharpen actionability
Examples:
- `Local`
- `Urgency`
- `Deal Seeking`
- `Vendor Focused`

may make a page more operationally useful, especially when paired with:
- quote
- booking
- provider comparison
- purchase

### Rule 5: sensitive domains need independent safeguards
Even if a page scores as:
- strong
- lower funnel
- actionable

that does **not** automatically mean it should be openly targetable across all systems or markets.

### Rule 6: default to reporting when signals are weak
If the output is:
- low confidence
- passive
- ambiguous
- informational only

default use should be:
- reporting
- enrichment
- analytics
- contextual insight

instead of direct activation.

---

## Data model examples

Below are a few concrete examples of how providers can store or expose classifications.

### Example 1: TSV-style row

```tsv
page_or_entity_id	primary_intent_pattern_id	primary_intent_pattern_name	intent_domain_id	intent_domain_name	intent_modifier_ids	intent_stage_id	commercial_readiness_id	actionability_id	performance_utility_id	confidence_score
page-001	IP-1220	Ready to Buy Major Item	ID-2000	Automotive	IM-1000|IM-2000|IM-5000	IS-8000	CR-3000	AC-1000	PU-1000	0.94
```

### Example 2: JSON record

```json
{
  "page_or_entity_id": "page-001",
  "primary_intent_pattern_id": "IP-1220",
  "primary_intent_pattern_name": "Ready to Buy Major Item",
  "secondary_intent_pattern_ids": ["IP-6220"],
  "secondary_intent_pattern_names": ["Price and Value Comparison"],
  "intent_domain_id": "ID-2000",
  "intent_domain_name": "Automotive",
  "intent_modifier_ids": ["IM-1000", "IM-2000", "IM-5000"],
  "intent_modifier_names": ["Deal Seeking", "Local", "Urgency"],
  "intent_stage_id": "IS-8000",
  "intent_stage_name": "Ready to Act",
  "commercial_readiness_id": "CR-3000",
  "commercial_readiness_name": "Transaction Readiness",
  "actionability_id": "AC-1000",
  "actionability_name": "Eligible",
  "performance_utility_id": "PU-1000",
  "performance_utility_name": "High",
  "confidence_score": 0.94
}
```

### Example 3: Segment label example

A provider may derive internal or external segment labels such as:

- `intent:auto_purchase_transaction_ready`
- `intent:travel_booking_deal_seeking`
- `intent:b2b_comparison_vendor_focused`
- `intent:insurance_quote_budget_conscious`

These derived labels should still map back to the normalized framework fields.

### Example 4: Reporting dimension example

A reporting table may roll up inventory or traffic by:

- Intent Pattern
- Intent Domain
- Funnel Class
- Commercial Readiness
- Actionability
- Performance Utility

Example report questions:
- What percentage of automotive inventory is transaction-ready?
- How much travel inventory is planning vs booking?
- Which B2B pages are comparison-heavy but not yet ready to act?
- How much inventory is high utility but reporting-only?

---

## FAQ

### Why not keep everything in one taxonomy?
Because intent behavior, domain, stage, modifiers, and actionability are different dimensions. Combining them into one giant tree creates overlap, inconsistency, and poor operational usability.

### Why separate intent pattern and intent domain?
Because behavior and vertical are not the same thing. `Comparison Intent` is a behavioral pattern. `Automotive` is a domain. Keeping them separate makes the framework more consistent and easier to activate and report on.

### Why are some concepts modeled as modifiers instead of top-level categories?
Signals like `Deal Seeking`, `Local`, `Brand Focused`, and `Vendor Focused` often cut across multiple domains and intent patterns. They work better as overlays than as peer top-level categories.

### Why do we need both commercial readiness and intent stage?
Because they answer different questions.

- **Intent Stage** answers: where is the user in the journey?
- **Commercial Readiness** answers: how commercially actionable is the behavior?

A user may be in `Comparison` stage but still only show `Commercial Investigation`, not `Transaction Readiness`.

### Why do we need actionability if we already have confidence?
Confidence answers how certain the classifier is. Actionability answers whether the signal should actually be used for activation. A classification can be high confidence but still be reporting-only or restricted.

### What is the difference between actionability and performance utility?
- **Actionability** says whether a signal should be activated
- **Performance Utility** says how valuable that signal is likely to be for performance execution

A signal may be eligible but still low utility, or high utility but eligible only with strong confidence.

### Can one page have multiple intents?
Yes. A page can have one primary intent pattern and one or more secondary intent patterns. Many pages naturally mix signals such as comparison, review, and deal-seeking.

### Should every classified page be targetable?
No. Some signals are better used for:
- reporting
- packaging
- enrichment
- analytics
- model features

rather than direct targeting.

### How should B2B providers use this framework?
Use the same intent patterns as B2C, but pair them with B2B-oriented domains such as:
- Software and SaaS
- Infrastructure and Data
- Business services
- Finance, HR, and operations software

### How should sensitive categories be handled?
Sensitive categories should be controlled separately using:
- sensitive category flags
- allowed activation scope
- market or platform restrictions
- contextual-only or reporting-only fallbacks where needed

### What is the minimum viable implementation?
A lightweight starting point can use:
- Intent Pattern
- Intent Domain
- Intent Stage
- Commercial Readiness
- Actionability
- Confidence Score

### What is a strong first use case?
A strong first use case is:
- contextual packaging
- reporting
- analytics
- enrichment

before moving to direct activation or bid strategy use.


---

## Summary

This repository is meant to provide a practical and extensible framework for standardizing **user intent inferred from content consumption**.

It is especially useful where teams need to move beyond:
- topic classification
- audience labeling
- broad contextual categories

and toward:
- actionable intent understanding
- performance-aware targeting
- clear distinctions between research and readiness
- modular, governed taxonomy design

