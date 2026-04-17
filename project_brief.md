# Project Brief: User Intent Taxonomy

## Project name
User Intent Taxonomy

## One-line summary
A multi-dimensional taxonomy framework for standardizing **user intent inferred from consumed content** for use in **programmatic advertising, contextual targeting, performance activation, reporting, deal packaging, and ML classification**.

---

## The problem

In ad tech, we already have strong classification systems for:

- what content is about
- what audiences users may resemble
- what products or services are being advertised

But we do **not** have a clean standard for answering:

- What is the user likely trying to do right now?
- Are they learning, comparing, planning, requesting a quote, booking, buying, renewing, or seeking support?
- Is the behavior just informational, or does it show commercial investigation or transaction readiness?
- Is the signal suitable for direct activation, or only for reporting and enrichment?

This gap matters because two pages in the same content category can represent very different user intent.

### Example
Both of these may fall under similar broad content topics:

- `how do electric cars work`
- `best suv lease deals near me`

But from a programmatic performance perspective, they are very different:

- one is mostly informational
- the other is close to transaction

Traditional topic taxonomies do not capture that difference clearly enough.

---

## Why existing taxonomies are not enough

Existing standards are still useful and should remain in place.

### Content taxonomy
Helps classify what the page or content is about.

### Audience taxonomy
Helps classify what kind of user or segment the behavior may resemble.

### Ad product taxonomy
Helps classify what kinds of products or services are being marketed.

### The missing layer
What is missing is a standard way to classify the **intent implied by content consumption**.

This project introduces that missing layer.

---

## Core idea

Instead of building one giant taxonomy that mixes behavior, vertical, stage, and actionability, this project separates intent into multiple dimensions.

### The framework dimensions

#### 1. Intent Pattern
What the user is trying to do.

Examples:
- Purchase Intent
- Lead Generation Intent
- Booking and Reservation Intent
- Comparison Intent
- Review and Validation Intent
- Service and Support Intent

#### 2. Intent Domain
What area of commerce or life the intent applies to.

Examples:
- Automotive
- Travel
- Insurance
- Retail and Consumer Goods
- Financial Services
- Education
- Business and B2B Solutions

#### 3. Intent Modifier
Overlays that sharpen or qualify the signal.

Examples:
- Deal Seeking
- Local
- Vendor Focused
- Brand Focused
- Urgency
- Budget Conscious

#### 4. Intent Stage
Where the user appears to be in the journey.

Examples:
- Exploration
- Learning
- Comparison
- Evaluation
- Planning
- Ready to Act
- Acting
- Post Action

#### 5. Intent Strength
How strong the signal appears to be.

Examples:
- Weak
- Moderate
- Strong
- Very Strong or Explicit

#### 6. Commercial Readiness
Whether the behavior is informational, investigative, transaction-ready, or post-transaction.

Examples:
- Non Commercial Informational
- Commercial Investigation
- Transaction Readiness
- Post Transaction

#### 7. Actionability
Whether the signal should be used for activation.

Examples:
- Eligible
- Eligible With Strong Confidence Only
- Reporting Only
- Not Recommended For Activation

#### 8. Performance Utility
How useful the signal is for performance campaign execution.

Examples:
- High
- Medium
- Low
- Primarily Analytical

---

## Key design decisions

### 1. Separate intent pattern from domain
This was a major design choice.

`Comparison` is a behavior pattern.  
`Automotive` is a domain.  

They should not be forced into the same top-level taxonomy layer.

That separation makes the framework:
- easier to govern
- easier to classify
- easier to activate
- easier to report on

### 2. Treat modifiers as overlays, not primary categories
Signals like:
- deal seeking
- local
- brand focused
- vendor focused

cut across many verticals and patterns, so they work better as overlays than as top-level branches.

### 3. Separate investigation from readiness
This framework explicitly distinguishes:
- commercial investigation
- transaction readiness

This is critical for performance campaigns.

### 4. Add actionability
Not every inferred signal should be activated.

Some signals are best used for:
- reporting
- analytics
- contextual packaging
- enrichment
- ML features

### 5. Support both B2C and B2B
The framework is designed for:
- consumer commerce
- local services
- travel
- finance and insurance
- real estate
- education
- telecom
- B2B SaaS
- business technology and services

---

## Why this matters in programmatic advertising

Programmatic systems often need to make decisions with incomplete information.

A clean user intent framework can improve:

- contextual targeting
- inventory packaging
- PMP / deal creation
- audience enrichment
- performance reporting
- creative decisioning
- bid strategy inputs
- ML classification workflows

It helps distinguish:
- topic vs intent
- research vs readiness
- activation-worthy signals vs reporting-only signals

---

## Example classifications

### Example 1
**Input:** `best suv lease deals near me`

Possible output:
- Intent Pattern: Purchase Intent
- Intent Domain: Automotive
- Modifiers: Deal Seeking, Local, Budget Conscious, Urgency
- Intent Stage: Ready to Act
- Commercial Readiness: Transaction Readiness
- Actionability: Eligible
- Performance Utility: High

### Example 2
**Input:** `best crm for small sales team`

Possible output:
- Intent Pattern: Comparison Intent
- Intent Domain: Business and B2B Solutions
- Modifier: Vendor Focused
- Intent Stage: Comparison
- Commercial Readiness: Commercial Investigation
- Actionability: Eligible With Strong Confidence Only
- Performance Utility: Medium

### Example 3
**Input:** `how to file homeowners insurance claim`

Possible output:
- Intent Pattern: Service and Support Intent
- Intent Domain: Insurance
- Intent Stage: Post Action
- Commercial Readiness: Post Transaction
- Actionability: Eligible
- Performance Utility: Medium
- Activation Scope: Contextual only

### Example 4
**Input:** `how do electric cars work`

Possible output:
- Intent Pattern: Research and Learning Intent
- Intent Domain: Automotive
- Intent Stage: Learning
- Commercial Readiness: Non Commercial Informational
- Actionability: Reporting Only
- Performance Utility: Primarily Analytical

---

## Target users

This project is especially relevant for:

- SSPs
- DSPs
- contextual data providers
- publishers
- commerce media platforms
- retail media networks
- measurement providers
- analytics platforms
- data science and ML teams
- standards and taxonomy teams

---

## What is in the repo

The repository contains:

- separate TSV files for each taxonomy dimension
- a master Excel workbook
- a classification schema
- a mapping template
- sample classification examples
- detailed README documentation

The files are intentionally separate because the framework is multi-dimensional and modular.

---

## Practical first use cases

A provider does not need to implement everything at once.

A good starting point is:

- Intent Pattern
- Intent Domain
- Intent Stage
- Commercial Readiness
- Actionability
- Confidence

Good early use cases:
- contextual packaging
- inventory reporting
- enrichment and analytics
- testing derived segments before full activation

---

## What success looks like

If adopted well, this framework helps the ecosystem move from:

**“This page is about automotive.”**

to:

**“This page shows automotive comparison behavior with strong commercial investigation and moderate activation value.”**

or

**“This page shows transaction-ready automotive purchase intent with local and deal-seeking modifiers.”**

That is the core value of the project.

---

## Short positioning statement

User Intent Taxonomy adds the missing **intent layer** to existing ad-tech classification systems by standardizing what users may be trying to do when they consume content.
