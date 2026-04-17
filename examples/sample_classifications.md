# Sample Classifications

This document provides human-readable sample classifications for the User Intent Taxonomy framework.

Each example shows how a piece of content or query can be classified across multiple dimensions such as intent pattern, domain, modifiers, stage, commercial readiness, actionability, and performance utility.

---

## Example 1

**Input text:** `best suv lease deals near me`

- **Page or Entity ID:** ex-001
- **Primary Intent Pattern:** Ready to Buy Major Item (IP-1220)
- **Secondary Intent Patterns:** Price and Value Comparison (IP-6220); Checking Price Range (IP-5110)
- **Intent Domain:** Automotive (ID-2000)
- **Intent Modifiers:** Deal Seeking (IM-1000); Local (IM-2000); Urgency (IM-5000); Budget Conscious (IM-6000)
- **Intent Stage:** Ready to Act (IS-8000)
- **Intent Strength:** Very Strong or Explicit (IG-4000)
- **Commercial Readiness:** Transaction Readiness (CR-3000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** High (PU-1000)
- **Primary KPI Alignment:** Lead
- **Lead Gen Relevance:** High
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.94

This example indicates **Ready to Buy Major Item** in the **Automotive** domain with local intent signals, urgency, price/value sensitivity. It is classified as **Transaction Readiness** and **Eligible**.

---

## Example 2

**Input text:** `best hybrid suv for family of 5`

- **Page or Entity ID:** ex-002
- **Primary Intent Pattern:** Comparison Intent (IP-6000)
- **Secondary Intent Patterns:** Researching Major Purchase (IP-1210)
- **Intent Domain:** Automotive (ID-2000)
- **Intent Modifiers:** None
- **Intent Stage:** Comparison (IS-4000)
- **Intent Strength:** Strong (IG-3000)
- **Commercial Readiness:** Commercial Investigation (CR-2000)
- **Actionability:** Eligible With Strong Confidence Only (AC-2000)
- **Performance Utility:** Medium (PU-2000)
- **Primary KPI Alignment:** Engagement
- **Lead Gen Relevance:** Medium
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.86

This example indicates **Comparison Intent** in the **Automotive** domain. It is classified as **Commercial Investigation** and **Eligible With Strong Confidence Only**.

---

## Example 3

**Input text:** `cheap flights to las vegas this weekend`

- **Page or Entity ID:** ex-003
- **Primary Intent Pattern:** Flight Booking (IP-3110)
- **Secondary Intent Patterns:** Checking Price Range (IP-5110)
- **Intent Domain:** Travel (ID-3000)
- **Intent Modifiers:** Deal Seeking (IM-1000); Urgency (IM-5000)
- **Intent Stage:** Ready to Act (IS-8000)
- **Intent Strength:** Very Strong or Explicit (IG-4000)
- **Commercial Readiness:** Transaction Readiness (CR-3000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** High (PU-1000)
- **Primary KPI Alignment:** Booking
- **Lead Gen Relevance:** Low
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.93

This example indicates **Flight Booking** in the **Travel** domain with urgency, price/value sensitivity. It is classified as **Transaction Readiness** and **Eligible**.

---

## Example 4

**Input text:** `things to do in napa valley with kids`

- **Page or Entity ID:** ex-004
- **Primary Intent Pattern:** Trip Planning (IP-9210)
- **Secondary Intent Patterns:** None
- **Intent Domain:** Travel (ID-3000)
- **Intent Modifiers:** None
- **Intent Stage:** Planning (IS-6000)
- **Intent Strength:** Strong (IG-3000)
- **Commercial Readiness:** Commercial Investigation (CR-2000)
- **Actionability:** Eligible With Strong Confidence Only (AC-2000)
- **Performance Utility:** Medium (PU-2000)
- **Primary KPI Alignment:** Booking
- **Lead Gen Relevance:** Low
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.82

This example indicates **Trip Planning** in the **Travel** domain. It is classified as **Commercial Investigation** and **Eligible With Strong Confidence Only**.

---

## Example 5

**Input text:** `best credit cards for travel rewards`

- **Page or Entity ID:** ex-005
- **Primary Intent Pattern:** Comparison Intent (IP-6000)
- **Secondary Intent Patterns:** None
- **Intent Domain:** Financial Services (ID-8000)
- **Intent Modifiers:** None
- **Intent Stage:** Comparison (IS-4000)
- **Intent Strength:** Strong (IG-3000)
- **Commercial Readiness:** Commercial Investigation (CR-2000)
- **Actionability:** Eligible With Strong Confidence Only (AC-2000)
- **Performance Utility:** Medium (PU-2000)
- **Primary KPI Alignment:** Lead
- **Lead Gen Relevance:** Medium
- **Sensitive Category Flag:** Potentially sensitive
- **Allowed Activation Scope:** Contextual only
- **Confidence Score:** 0.84

This example indicates **Comparison Intent** in the **Financial Services** domain. It is classified as **Commercial Investigation** and **Eligible With Strong Confidence Only**.

---

## Example 6

**Input text:** `mortgage refinance rates today`

- **Page or Entity ID:** ex-006
- **Primary Intent Pattern:** Loan or Financing Quote (IP-5220)
- **Secondary Intent Patterns:** Checking Price Range (IP-5110)
- **Intent Domain:** Real Estate (ID-A000)
- **Intent Modifiers:** Urgency (IM-5000); Budget Conscious (IM-6000)
- **Intent Stage:** Ready to Act (IS-8000)
- **Intent Strength:** Very Strong or Explicit (IG-4000)
- **Commercial Readiness:** Transaction Readiness (CR-3000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** High (PU-1000)
- **Primary KPI Alignment:** Lead
- **Lead Gen Relevance:** High
- **Sensitive Category Flag:** Potentially sensitive
- **Allowed Activation Scope:** Contextual only
- **Confidence Score:** 0.91

This example indicates **Loan or Financing Quote** in the **Real Estate** domain with urgency, price/value sensitivity. It is classified as **Transaction Readiness** and **Eligible**.

---

## Example 7

**Input text:** `compare auto insurance quotes online`

- **Page or Entity ID:** ex-007
- **Primary Intent Pattern:** Insurance Quote (IP-5210)
- **Secondary Intent Patterns:** Service Provider Comparison (IP-6210)
- **Intent Domain:** Insurance (ID-9000)
- **Intent Modifiers:** Vendor Focused (IM-4000); Budget Conscious (IM-6000)
- **Intent Stage:** Ready to Act (IS-8000)
- **Intent Strength:** Very Strong or Explicit (IG-4000)
- **Commercial Readiness:** Transaction Readiness (CR-3000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** High (PU-1000)
- **Primary KPI Alignment:** Quote
- **Lead Gen Relevance:** High
- **Sensitive Category Flag:** Potentially sensitive
- **Allowed Activation Scope:** Contextual only
- **Confidence Score:** 0.92

This example indicates **Insurance Quote** in the **Insurance** domain with price/value sensitivity, provider or brand specificity. It is classified as **Transaction Readiness** and **Eligible**.

---

## Example 8

**Input text:** `how to file homeowners insurance claim`

- **Page or Entity ID:** ex-008
- **Primary Intent Pattern:** Claim Complaint or Issue Resolution (IP-C220)
- **Secondary Intent Patterns:** None
- **Intent Domain:** Insurance (ID-9000)
- **Intent Modifiers:** None
- **Intent Stage:** Post Action (IS-A000)
- **Intent Strength:** Strong (IG-3000)
- **Commercial Readiness:** Post Transaction (CR-4000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** Medium (PU-2000)
- **Primary KPI Alignment:** Support Resolution
- **Lead Gen Relevance:** Low
- **Sensitive Category Flag:** Potentially sensitive
- **Allowed Activation Scope:** Contextual only
- **Confidence Score:** 0.89

This example indicates **Claim Complaint or Issue Resolution** in the **Insurance** domain. It is classified as **Post Transaction** and **Eligible**.

---

## Example 9

**Input text:** `best espresso machine under 300`

- **Page or Entity ID:** ex-009
- **Primary Intent Pattern:** Feature Comparison (IP-6120)
- **Secondary Intent Patterns:** Checking Price Range (IP-5110)
- **Intent Domain:** Retail and Consumer Goods (ID-1000)
- **Intent Modifiers:** Budget Conscious (IM-6000)
- **Intent Stage:** Evaluation (IS-5000)
- **Intent Strength:** Strong (IG-3000)
- **Commercial Readiness:** Commercial Investigation (CR-2000)
- **Actionability:** Eligible With Strong Confidence Only (AC-2000)
- **Performance Utility:** Medium (PU-2000)
- **Primary KPI Alignment:** Purchase
- **Lead Gen Relevance:** Low
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.83

This example indicates **Feature Comparison** in the **Retail and Consumer Goods** domain with price/value sensitivity. It is classified as **Commercial Investigation** and **Eligible With Strong Confidence Only**.

---

## Example 10

**Input text:** `buy running shoes online free shipping`

- **Page or Entity ID:** ex-010
- **Primary Intent Pattern:** Everyday Item Purchase (IP-1110)
- **Secondary Intent Patterns:** None
- **Intent Domain:** Retail and Consumer Goods (ID-1000)
- **Intent Modifiers:** Deal Seeking (IM-1000)
- **Intent Stage:** Acting (IS-9000)
- **Intent Strength:** Very Strong or Explicit (IG-4000)
- **Commercial Readiness:** Transaction Readiness (CR-3000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** High (PU-1000)
- **Primary KPI Alignment:** Purchase
- **Lead Gen Relevance:** Low
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.95

This example indicates **Everyday Item Purchase** in the **Retail and Consumer Goods** domain with price/value sensitivity. It is classified as **Transaction Readiness** and **Eligible**.

---

## Example 11

**Input text:** `best crm for small sales team`

- **Page or Entity ID:** ex-011
- **Primary Intent Pattern:** Comparison Intent (IP-6000)
- **Secondary Intent Patterns:** Deep Research Learning (IP-8120); Looking for Solution Types (IP-8310)
- **Intent Domain:** Business and B2B Solutions (ID-J000)
- **Intent Modifiers:** Vendor Focused (IM-4000)
- **Intent Stage:** Comparison (IS-4000)
- **Intent Strength:** Strong (IG-3000)
- **Commercial Readiness:** Commercial Investigation (CR-2000)
- **Actionability:** Eligible With Strong Confidence Only (AC-2000)
- **Performance Utility:** Medium (PU-2000)
- **Primary KPI Alignment:** Lead
- **Lead Gen Relevance:** High
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.87

This example indicates **Comparison Intent** in the **Business and B2B Solutions** domain with provider or brand specificity. It is classified as **Commercial Investigation** and **Eligible With Strong Confidence Only**.

---

## Example 12

**Input text:** `salesforce demo request`

- **Page or Entity ID:** ex-012
- **Primary Intent Pattern:** Demo Request (IP-2310)
- **Secondary Intent Patterns:** None
- **Intent Domain:** Business and B2B Solutions (ID-J000)
- **Intent Modifiers:** Vendor Focused (IM-4000); Brand Focused (IM-3000)
- **Intent Stage:** Form Fill Contact or Application (IS-9200)
- **Intent Strength:** Very Strong or Explicit (IG-4000)
- **Commercial Readiness:** Transaction Readiness (CR-3000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** High (PU-1000)
- **Primary KPI Alignment:** Lead
- **Lead Gen Relevance:** High
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.96

This example indicates **Demo Request** in the **Business and B2B Solutions** domain with provider or brand specificity. It is classified as **Transaction Readiness** and **Eligible**.

---

## Example 13

**Input text:** `emergency plumber near me open now`

- **Page or Entity ID:** ex-013
- **Primary Intent Pattern:** Contact Request (IP-2120)
- **Secondary Intent Patterns:** Finding Places Nearby (IP-A110)
- **Intent Domain:** Professional Services (ID-H000)
- **Intent Modifiers:** Local (IM-2000); Urgency (IM-5000)
- **Intent Stage:** High Booking or Contact Readiness (IS-8200)
- **Intent Strength:** Very Strong or Explicit (IG-4000)
- **Commercial Readiness:** Transaction Readiness (CR-3000)
- **Actionability:** Eligible (AC-1000)
- **Performance Utility:** High (PU-1000)
- **Primary KPI Alignment:** Lead
- **Lead Gen Relevance:** High
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.95

This example indicates **Contact Request** in the **Professional Services** domain with local intent signals, urgency. It is classified as **Transaction Readiness** and **Eligible**.

---

## Example 14

**Input text:** `best online mba programs`

- **Page or Entity ID:** ex-014
- **Primary Intent Pattern:** Comparison Intent (IP-6000)
- **Secondary Intent Patterns:** None
- **Intent Domain:** Education (ID-E000)
- **Intent Modifiers:** None
- **Intent Stage:** Comparison (IS-4000)
- **Intent Strength:** Strong (IG-3000)
- **Commercial Readiness:** Commercial Investigation (CR-2000)
- **Actionability:** Eligible With Strong Confidence Only (AC-2000)
- **Performance Utility:** Medium (PU-2000)
- **Primary KPI Alignment:** Lead
- **Lead Gen Relevance:** High
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Full activation
- **Confidence Score:** 0.84

This example indicates **Comparison Intent** in the **Education** domain. It is classified as **Commercial Investigation** and **Eligible With Strong Confidence Only**.

---

## Example 15

**Input text:** `how do electric cars work`

- **Page or Entity ID:** ex-015
- **Primary Intent Pattern:** Introductory Learning (IP-8110)
- **Secondary Intent Patterns:** None
- **Intent Domain:** Automotive (ID-2000)
- **Intent Modifiers:** None
- **Intent Stage:** Learning (IS-3000)
- **Intent Strength:** Moderate (IG-2000)
- **Commercial Readiness:** Non Commercial Informational (CR-1000)
- **Actionability:** Reporting Only (AC-3000)
- **Performance Utility:** Primarily Analytical (PU-4000)
- **Primary KPI Alignment:** Engagement
- **Lead Gen Relevance:** None
- **Sensitive Category Flag:** Not sensitive
- **Allowed Activation Scope:** Reporting only
- **Confidence Score:** 0.78

This example indicates **Introductory Learning** in the **Automotive** domain. It is classified as **Non Commercial Informational** and **Reporting Only**.

---
