# Probable Feedback and Questions on the User Intent Taxonomy Proposal

This document captures the kinds of critical feedback, objections, and hard questions that standards participants, taxonomy maintainers, and ad-industry practitioners are likely to raise when evaluating the proposal to add a User Intent Taxonomy family alongside existing IAB taxonomy families.

The goal is not to dismiss these concerns. The goal is to surface them early so the proposal, implementation guidance, and mappings can be strengthened before formal review.

## 1. Need and problem definition

### "Why is a new taxonomy family needed at all?"

Reviewers may argue that the proposal has not yet proven that the problem cannot be solved by existing `Content`, `Audience`, and `Ad Product` taxonomies plus implementation guidance.

### "Is this a taxonomy problem or a modeling problem?"

Some participants may say that "intent" is better handled by proprietary scoring models, contextual classifiers, or buyer-specific analytics layers rather than by an industry taxonomy.

### "What operational failure exists today that this taxonomy fixes?"

Standards reviewers may ask for concrete examples of current ambiguity, interoperability failures, or reporting fragmentation that cannot be resolved with existing IAB assets.

### "Is the proposal solving a broad industry need, or a single company's internal architecture problem?"

Participants may question whether this taxonomy is generally useful across publishers, SSPs, DSPs, data providers, and measurement vendors, or whether it mostly reflects one implementation perspective.

## 2. Overlap with existing IAB taxonomies

### "How is this not just an extension of Content Taxonomy?"

This is likely to be one of the first objections. Reviewers may argue that if intent is inferred from consumed content, then it is simply a more refined content classification problem.

### "How is this not a subset of Audience Taxonomy purchase-intent segments?"

Because IAB Audience Taxonomy already includes interest and purchase-intent style concepts, participants may question whether this proposal duplicates segment language that already exists.

### "How is this different from Ad Product Taxonomy?"

If a user appears to be researching flights, cars, insurance, or software, reviewers may say that Ad Product already covers the commercial object of interest and that another layer is unnecessary.

### "Why does this require a new family instead of new mapping guidance?"

Some participants may prefer a lighter-weight answer: keep current taxonomies unchanged and publish best practices on how to infer user posture from combinations of topic, audience, and product labels.

## 3. Scope and classification boundaries

### "What exactly is the unit of classification?"

Reviewers may press on whether the taxonomy is intended for pages, URLs, search queries, snippets, sessions, user events, or user profiles. If the answer is "all of the above," they may see that as underspecified.

### "Is this event-level, content-level, or user-level?"

Because the proposal allows derived user-profile use, participants may worry that the boundary between immediate event posture and stable user characterization is still too loose.

### "What is in scope, and what is explicitly out of scope?"

Experts will likely ask for crisp exclusions such as:
- identity and demographic inference
- policy enforcement
- legal determinations
- medical, financial, or insurance eligibility inference
- long-term consumer propensity modeling

### "Is this intended to be normative for activation decisions?"

Participants may ask whether the taxonomy is just descriptive metadata or whether platforms are expected to use it directly in targeting, optimization, and exclusion logic.

## 4. Semantics and taxonomy design

### "Is 'intent' the right word?"

Some reviewers may argue that the proposal is not really measuring intent, but inferred task posture, content consumption context, or near-term behavioral likelihood. They may view the word "intent" as overstated.

### "Are the dimensions independent enough?"

The proposal uses multiple dimensions such as `Intent Pattern`, `Domain`, `Modifier`, `Stage`, `Strength`, `Commercial Readiness`, `Actionability`, and `Performance Utility`. Reviewers may question whether some of these dimensions overlap too much to be worth standardizing separately.

### "Why is this multi-file instead of a single taxonomy?"

Some participants may see the modular structure as elegant, while others may see it as harder to adopt, govern, and implement consistently.

### "How were these dimensions chosen?"

Experts may ask whether the eight dimensions came from industry research, implementation evidence, model performance requirements, or editorial judgment.

### "Are the labels precise enough for multi-party interoperability?"

Critical reviewers may ask whether labels like `High Intent`, `Vendor Focused`, `Researching Options`, `Urgency`, or `Comparison Shopping` will be interpreted consistently across companies.

### "What prevents classification drift?"

Participants may worry that different vendors will map the same content to different stages, strengths, or readiness levels, making the standard difficult to compare across implementations.

## 5. Evidence and validation

### "What empirical evidence supports the taxonomy design?"

Reviewers may ask for evidence that the dimensions improve targeting, reporting, or interoperability in practice rather than sounding conceptually useful.

### "How was the taxonomy validated?"

They may want to know:
- how many real examples were tested
- which verticals were reviewed
- whether multiple annotators were used
- what agreement rates looked like
- whether taxonomy revisions were driven by observed ambiguity

### "Where are the edge cases and failure cases?"

Skeptical participants may ask for examples where the taxonomy struggles, such as mixed-intent pages, editorial content with weak commercial posture, or high-sensitivity informational content.

### "Can independent implementers reproduce the same output?"

A standards group may ask whether the proposal is implementable in a way that yields sufficiently consistent results across classifiers, human reviewers, and downstream systems.

## 6. Sensitive categories, privacy, and policy risk

### "Does this increase the risk of sensitive inference?"

Because the taxonomy covers areas like health care, insurance, education, careers, legal services, parenting, and finance, participants may worry that it enables sensitive segmentation or targeting under a new label.

### "How does this interact with regulated or restricted use cases?"

Reviewers may ask how the taxonomy should be handled when intent signals touch:
- health conditions or treatment seeking
- debt or financial distress
- legal problems
- employment vulnerability
- family planning or child-related issues

### "Are the safeguards strong enough?"

Some participants may say that the current safeguards are still too high-level and need more operational guidance for activation restrictions, aggregation thresholds, retention limits, or prohibited uses.

### "Does user-profile derivation create a privacy problem?"

Even if the taxonomy is described as event-first, reviewers may focus on the derived-profile use case and ask whether repeated event aggregation effectively recreates a sensitive audience taxonomy.

## 7. Mapping and interoperability

### "If mappings are weak, why should this be standardized?"

Because many mappings to existing IAB taxonomies are `Adjacent` or `No direct equivalent`, some reviewers may argue that the proposal is too detached from current infrastructure.

### "Are the mappings authoritative or illustrative?"

Participants may ask whether the current mapping tables are normative, best-effort, or only proposal-stage examples.

### "Why are there so few high-confidence Audience mappings?"

This question is especially likely if reviewers expect strong alignment to user-segment vocabularies and instead see many blanks or weak correspondences.

### "Will implementers need to support all dimensions and all mappings?"

Adoption may be resisted if vendors believe they must overhaul schemas, pipelines, and workflows to support a large multi-dimensional standard.

## 8. Implementation burden and market adoption

### "Is this too complicated for broad adoption?"

Participants may worry that the taxonomy is too detailed for publishers, DSPs, SSPs, and data vendors to operationalize consistently.

### "What is the minimum viable implementation?"

Reviewers may ask whether the proposal can be adopted incrementally, for example with only `Intent Pattern`, `Domain`, and `Stage`, rather than the full dimensional system.

### "What does adoption look like in OpenRTB or AdCOM terms?"

Standards-focused participants may ask exactly where these values would live, how they would be transmitted, and whether the proposal expects changes to existing protocol fields.

### "Who will maintain this taxonomy?"

Reviewers may ask about governance, editorial ownership, release cadence, deprecation policy, and who decides when a label is added, split, or retired.

### "What is the expected upgrade path?"

They may ask how major and minor versioning will work, especially if implementers pin to IDs and mappings.

## 9. Commercial and competitive concerns

### "Will large platforms implement this the same way as smaller vendors?"

Some participants may worry that the taxonomy is easier for companies with strong ML infrastructure and harder for smaller ecosystem participants to adopt.

### "Does this advantage contextual vendors over other participants?"

Because the proposal is strongly tied to consumed-content inference, some reviewers may perceive it as favoring contextual classification providers or certain measurement approaches.

### "Could this create false precision in activation?"

Buyers and sellers may worry that standardized labels such as `High Intent` will be treated as more deterministic than they really are.

## 10. Editorial and standards-process questions

### "Is the proposal too early?"

Participants may ask whether the taxonomy should mature through more private testing, implementation pilots, or field validation before being considered for standardization.

### "What is the change-control model?"

Reviewers may expect explicit rules for:
- adding new nodes
- deprecating nodes
- revising definitions
- preserving ID stability
- handling backward compatibility

### "Which parts are normative and which are informative?"

If this is not obvious, standards participants may struggle to evaluate the proposal cleanly.

### "What would constitute success or failure for this taxonomy?"

Skeptical reviewers may ask what adoption, consistency, or interoperability outcomes would justify the taxonomy becoming an IAB-maintained standard.

## 11. Tough questions that may come up in live discussion

These are the kinds of direct questions a skeptical reviewer may ask in a working-group setting:

- Why should the industry standardize inferred intent rather than leave it to implementation-specific models?
- Why is this not simply a recommendation to combine Content Taxonomy with Audience segments and proprietary scores?
- If two vendors classify the same page differently on `Stage` or `Strength`, what problem has the standard actually solved?
- What evidence shows that buyers and sellers need a common intent vocabulary badly enough to justify a new taxonomy family?
- What prevents this from becoming an indirect sensitive-attribute system?
- Why should the IAB maintain this instead of individual vendors publishing their own intent ontologies?
- What are the first three real workflows that become easier if this is standardized?
- Which dimensions are essential, and which are optional?
- If only half the ecosystem adopts it, does it still deliver interoperable value?
- What would you remove from the current proposal if reviewers conclude it is too broad?

## 12. Areas most likely to need stronger support before formal review

Based on the current package, the parts most likely to attract scrutiny are:

- empirical validation and annotation methodology
- implementation consistency across independent classifiers
- sensitive-category safeguards at the profile-derivation level
- exact boundaries with `Audience Taxonomy`
- minimum viable implementation guidance
- governance and versioning details
- stronger examples of industry workflows that current taxonomies do not handle cleanly

## 13. Recommended use of this document

This file can be used in three ways:

- As a pre-review checklist before sharing the proposal with external experts.
- As a basis for strengthening `proposal.md`, `implementation.md`, and the mapping files.
- As preparation material for live standards discussions, where the hardest questions are likely to focus on overlap, safety, evidence, and implementation burden.
