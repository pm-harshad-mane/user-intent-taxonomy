# User Intent Taxonomy 1.0 Mapping Principles

## Purpose

This note explains how the first-pass mapping files in this folder should be interpreted.

The goal of the first-pass mapping set is not to claim that User Intent Taxonomy 1.0 can be losslessly reduced into existing IAB taxonomies. The goal is to show:

- where the new taxonomy overlaps cleanly with existing taxonomy families
- where it is complementary rather than redundant
- where a new standard layer is likely necessary

## Core principle

The User Intent Taxonomy should be mapped to existing IAB taxonomies in a way that preserves the differences between:

- content aboutness
- audience segment labeling
- advertised product labeling
- inferred user intent from consumed content

## Mapping relationship types

### Direct

Use `Direct` when the target IAB taxonomy describes substantially the same domain or product concept.

Examples:

- `Automotive` user intent domain to `Automotive` content topic
- `Travel` user intent domain to `Travel` content topic
- `Automotive` user intent domain to `Vehicles` ad product family

### Adjacent

Use `Adjacent` when the target taxonomy provides a nearby concept but not the same semantics.

Examples:

- `Financial Services` user intent domain to `Business and Finance` content topic
- `Purchase Intent` user intent pattern to `Purchase Intent Classification` in audience taxonomy

### No direct equivalent

Use `No direct equivalent` when the target taxonomy does not standardize the same concept.

Examples:

- `Comparison Intent`
- `Ready to Act`
- `Urgency`
- `Transaction Readiness`

These are central reasons for proposing a User Intent taxonomy family in the first place.

## File-specific guidance

### Content mappings

The content mapping file mostly tests **domain/topic overlap**. Content taxonomies are best at aboutness, so user intent patterns and modifiers often do not map directly.

### Audience mappings

The audience mapping file mostly tests **segment adjacency**. Audience taxonomy is useful for interest- or purchase-intent-based segments, but it does not provide a clean page- or query-level language for immediate inferred user posture.

### Ad product mappings

The ad product mapping file mostly tests **product or service overlap**. It is often useful for domain alignment, but it does not capture user-side readiness, comparison, support, or research state.

## Review expectations

The first-pass mapping set should be treated as:

- useful for discussion
- directionally correct
- incomplete by design
- open for industry review and refinement

The safest interpretation is that direct mappings are the starting point for interoperability, while adjacent and no-direct-equivalent rows are the evidence that User Intent should exist as a separate taxonomy family.
