# AI Prompt Log

## 1. Initial Bug Analysis
Prompt:
- Asked AI to inspect the existing index.html and identify bugs against R1–R8.

Verification:
- Reviewed the suggested changes before accepting them.

## 2. Cart and Business Rules
Prompt:
- Asked AI to fix cart quantity limits, stock validation, subtotal calculation,
  sold-out handling, and product sorting.

Verification:
- Tested add to cart, quantity limits, stock limits, remove, subtotal,
  and sold-out behavior manually and with automated checks.

## 3. Coupon, Shipping and Delivery
Prompt:
- Asked AI to implement WELCOME10 according to R3, shipping according to R4,
  and pincode handling according to R8.

Verification:
- Tested coupon minimum, 10% discount, ₹150 cap, Gift exclusion,
  shipping calculation, valid pincodes, invalid pincodes, and
  unserviceable pincodes.

## 4. Checkout Contract
Prompt:
- Asked AI to preserve the required checkout form contract and serialize
  cart items and coupon values before submission.

Verification:
- Verified the `items` and `coupon` fields and form submission behavior.

## 5. Brand and UX Redesign
Prompt:
- Asked AI to align the page with BRAND.md while preserving the required
  product data, API contract, and checkout contract.

Verification:
- Reviewed typography, colors, layout, accessibility, responsive behavior,
  content, and removal of unsupported claims.

## 6. SEO and Structured Data
Prompt:
- Asked AI to add the required metadata and JSON-LD without inventing
  unsupported business or product information.

Verification:
- Reviewed title, description, canonical, social metadata, Organization/
  OnlineStore, Product, and FAQ structured data.

## 7. Final Verification
Prompt:
- Asked AI to verify the implementation against the assessment requirements
  without modifying the code.

Verification:
- Checked functional requirements and manually tested the important
  user flows.