# NotebookLM Storyboard Input: User Intent Taxonomy

## Purpose of this document
Use this document to generate:
- an explanation infographic
- a short explainer video
- executive-friendly summaries
- clear narrative assets for ad-tech and programmatic audiences

This document focuses on **story**, **structure**, and **visual explanation**, not just taxonomy detail.

---

## Core message

The ad-tech ecosystem already classifies:
- what content is about
- what audiences users may resemble
- what products are being advertised

But it still lacks a standard way to classify:

**What the user may be trying to do right now based on the content they are consuming.**

This project fills that gap with a multi-dimensional **User Intent Taxonomy**.

---

## The problem in one visual sentence

**Topic does not equal intent.**

Two pages may both be about the same topic, but imply very different user intent.

### Simple example
- `how do electric cars work`
- `best suv lease deals near me`

Both may be related to automotive content.

But they represent very different intent:

- learning
- versus near-transaction purchase behavior

That difference matters a lot in:
- contextual targeting
- performance activation
- deal packaging
- reporting
- creative strategy

---

## Before vs after narrative

### Before
Ad-tech systems often rely mainly on:
- content topic
- audience segment
- product category

This helps answer:
- what the page is about
- what kind of user it may resemble
- what kind of advertiser might fit

But it does not clearly answer:
- is the user learning?
- comparing?
- booking?
- buying?
- renewing?
- seeking support?

### After
With a User Intent Taxonomy, systems can say things like:

- `Comparison Intent` + `Automotive`
- `Purchase Intent` + `Automotive` + `Deal Seeking` + `Local`
- `Lead Generation Intent` + `Business and B2B Solutions`
- `Service and Support Intent` + `Insurance`

That is much more useful operationally.

---

## The big idea

Do **not** force everything into one giant taxonomy.

Instead, separate intent into multiple dimensions.

### The 8 dimensions

1. **Intent Pattern**  
   What the user is trying to do

2. **Intent Domain**  
   What category or vertical the intent applies to

3. **Intent Modifier**  
   Overlays that sharpen the signal

4. **Intent Stage**  
   Where the user is in the journey

5. **Intent Strength**  
   How strong the signal is

6. **Commercial Readiness**  
   Whether the behavior is informational, investigative, or transaction-ready

7. **Actionability**  
   Whether the signal should be activated

8. **Performance Utility**  
   How useful the signal is for performance execution

---

## Why the framework is designed this way

### Design decision 1: separate pattern from domain
`Comparison` is not the same thing as `Automotive`.

One is behavior.  
One is vertical.

Separating them makes the framework:
- cleaner
- more scalable
- more explainable
- more activation-friendly

### Design decision 2: treat overlays as modifiers
Signals like:
- deal seeking
- local
- urgency
- vendor focused

should not usually be top-level categories.

They sharpen the signal, but they are not the main behavior.

### Design decision 3: separate investigation from readiness
This is one of the most important performance concepts.

There is a big difference between:
- researching a category
- and being ready to transact

The framework makes that explicit.

### Design decision 4: not every signal should be activated
Some intent is highly useful for targeting.

Some should be used only for:
- reporting
- packaging
- enrichment
- analytics

That is why the framework includes:
- actionability
- performance utility

---

## Suggested infographic structure

## Panel 1: The problem
Headline:
**Why topic alone is not enough**

Visual:
Two cards side by side:
- `how do electric cars work`
- `best suv lease deals near me`

Both labeled:
- Topic: Automotive

Then show how intent differs:
- Learning
- Purchase / transaction readiness

Key message:
**Same topic, very different intent**

---

## Panel 2: What is missing today
Headline:
**Existing taxonomies classify content, audience, and products — but not intent**

Visual:
Three existing layers:
- Content
- Audience
- Ad Product

Then a highlighted missing fourth layer:
- User Intent

Key message:
**Intent is the missing operational layer**

---

## Panel 3: The new framework
Headline:
**A multi-dimensional approach to user intent**

Visual:
8 blocks or a wheel showing:
- Intent Pattern
- Intent Domain
- Modifier
- Stage
- Strength
- Commercial Readiness
- Actionability
- Performance Utility

Key message:
**Intent needs more than one dimension**

---

## Panel 4: Before vs after
Headline:
**From broad topic classification to actionable intent understanding**

Visual:
Before:
- Automotive

After:
- Comparison Intent
- Automotive
- Commercial Investigation
- Eligible With Strong Confidence Only

Another example:
- Purchase Intent
- Automotive
- Deal Seeking
- Local
- Transaction Readiness
- Eligible

Key message:
**The framework turns broad context into operationally useful signals**

---

## Panel 5: Example use cases
Headline:
**Where this helps in programmatic advertising**

Visual icons or short callouts:
- Contextual targeting
- Deal packaging
- Reporting
- Audience enrichment
- Creative alignment
- ML labeling

Key message:
**This is useful across activation, reporting, and modeling**

---

## Panel 6: Safety and control
Headline:
**Not every inferred signal should be activated**

Visual:
A simple ladder:
- Eligible
- Eligible with strong confidence only
- Reporting only
- Not recommended for activation

Key message:
**Actionability is a core design feature**

---

## Suggested short explainer video structure

## Video length
Aim for:
- 2 to 4 minutes

## Tone
- strategic
- clear
- modern
- ad-tech literate
- not overly academic

## Audience
- SSP product teams
- DSP teams
- contextual data providers
- publishers
- programmatic strategists
- taxonomy / standards teams

---

## Video outline

### Scene 1: The problem
Voiceover idea:
“Programmatic advertising has good standards for classifying content, audiences, and products. But it still lacks a standard way to classify what a user may be trying to do when they consume content.”

Visual:
Content, Audience, Ad Product boxes appear.

Then a question mark:
“What is the user trying to do?”

---

### Scene 2: Topic is not intent
Voiceover idea:
“Two pages may share the same topic, but reflect very different user intent. One may be educational. Another may show clear transaction readiness.”

Visual:
Automotive example:
- `how do electric cars work`
- `best suv lease deals near me`

Then highlight:
- Learning
- Purchase
- Local
- Deal Seeking
- Ready to Act

---

### Scene 3: The framework
Voiceover idea:
“To solve this, the project introduces a multi-dimensional User Intent Taxonomy.”

Visual:
Animate the 8 dimensions:
- Pattern
- Domain
- Modifier
- Stage
- Strength
- Commercial Readiness
- Actionability
- Performance Utility

---

### Scene 4: Why multiple files exist
Voiceover idea:
“The framework is modular by design. Each taxonomy dimension is kept separate so providers can adopt only what they need, while preserving consistency and flexibility.”

Visual:
Repo-style file stack:
- intent_pattern_taxonomy.tsv
- intent_domain_taxonomy.tsv
- intent_modifier_taxonomy.tsv
- intent_stage_taxonomy.tsv
- and so on

Then show them combining into one classification output.

---

### Scene 5: Example outputs
Voiceover idea:
“Instead of just labeling content as automotive or travel, systems can now describe whether the user is comparing, planning, buying, booking, renewing, or seeking support.”

Visual:
A few examples:
- Automotive purchase
- Travel booking
- Insurance quote
- B2B demo request

---

### Scene 6: Practical value
Voiceover idea:
“This makes the framework useful for contextual targeting, deal packaging, reporting, enrichment, creative strategy, and machine learning.”

Visual:
Icons for:
- targeting
- PMP / deal packaging
- analytics
- enrichment
- ML

---

### Scene 7: Safe activation
Voiceover idea:
“Not every inferred signal should be activated. That is why the framework includes actionability, commercial readiness, and performance utility as first-class dimensions.”

Visual:
Show filtering:
- raw classified signal
- policy / confidence / actionability check
- activate or report only

---

### Scene 8: Closing
Voiceover idea:
“User Intent Taxonomy adds the missing intent layer to existing ad-tech classification systems, helping teams move from broad topic understanding to more operationally useful intent understanding.”

Visual:
Final summary:
- Topic
- Audience
- Product
- Intent

Then lockup:
**User Intent Taxonomy**

---

## Must-cover talking points

NotebookLM should make sure these points are included:

- this is complementary to existing taxonomies, not a replacement
- the framework separates behavior from vertical
- modifiers sharpen signals but are not top-level patterns
- commercial investigation and transaction readiness are different
- actionability matters because not every signal should be targeted
- the framework supports both B2C and B2B
- multiple files exist because the model is multi-dimensional and modular

---

## Good example set to mention

Use examples from:
- Automotive
- Travel
- Retail
- Insurance
- Financial services
- B2B SaaS
- Home services

Suggested examples:
- `best suv lease deals near me`
- `cheap flights to las vegas this weekend`
- `buy running shoes online free shipping`
- `compare auto insurance quotes online`
- `salesforce demo request`
- `emergency plumber near me open now`

---

## Visual style suggestions

Recommend visuals that are:
- clean
- simple
- presentation-friendly
- not cluttered
- modern B2B / ad-tech style
- white or light background
- minimal accent colors
- strong iconography
- clear before-vs-after comparisons

Good visual metaphors:
- stacked layers
- missing puzzle piece
- multi-axis classification
- filters and overlays
- journey stages
- activation gating

---

## Final summary statement

This project adds a standardized user intent layer to the ad-tech ecosystem, helping providers distinguish not just what content is about, but what the user may be trying to do when consuming it.
