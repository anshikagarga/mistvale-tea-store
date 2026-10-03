# Mistvale Tea Co. — Implementation Notes

## Business Rules

### R1 — Product Pricing
All product prices are calculated directly from the `PRODUCTS` data.
The values displayed and used for cart calculations are not taken from
page text or DOM content.

### R2 — Quantity Limits
A maximum of 5 units can be added for each product, and quantity cannot
exceed the available stock.

### R3 — WELCOME10 Coupon
- Coupon code is case-insensitive.
- Minimum cart subtotal is ₹399.
- Discount is 10% of eligible items.
- Gift products are excluded.
- Maximum discount is ₹150.
- Applying the coupon repeatedly does not increase the discount.

### R4 — Shipping
Standard shipping is ₹49.
Free shipping is applied when the amount after discount reaches the
implemented free-shipping threshold of ₹599.

## Contradiction

The assessment materials contain a contradiction regarding the free-shipping
threshold. The original announcement referenced ₹499, while the existing
store logic used ₹599.

The implementation retains ₹599 for consistency with the existing store
logic. The announcement was updated accordingly rather than introducing
a new business rule without confirmation.

## R5 — Currency and Rounding
Prices use the Indian Rupee symbol and Indian number grouping.
Only the final total is rounded to the nearest rupee.

## R6 — Sold-Out Products
Sold-out products cannot be added to the cart and are displayed after
available products regardless of the selected sort order.

## R7 — Search, Category and Sort
Search, category filtering and sorting work together while preserving
the current search and category state.

Search results are restricted to products returned by the provided
`API.search()` implementation.

## R8 — Delivery Check
The provided `API.checkPincode()` function is used for delivery checks.

The UI handles:
- serviceable pincodes
- unserviceable pincodes
- invalid 6-digit pincode input
- unexpected API errors

The delivery status does not remain permanently stuck on "Checking...".

## Product Data Integrity

The existing product IDs, names, prices and stock values were preserved.
Product information is derived from the provided `PRODUCTS` data.

Ratings and review counts are displayed only for products where those
values are provided in `PRODUCTS`.

No unsupported ratings, awards, customer counts or testimonials were added.

## API Contract

The provided API implementation between the API START and API END markers
was preserved.

## Checkout Contract

The required checkout form contract was preserved:

- `id="checkout-form"`
- POST method
- `https://mistvale.example/cart/checkout` action
- `items` field containing the cart JSON
- `coupon` field containing the entered coupon

The endpoint was not tested as a live network service because
`mistvale.example` is an example endpoint and does not resolve publicly.

## AI-Assisted Development

AI was used to identify bugs, propose implementation changes, improve
the UI according to `BRAND.md`, and assist with verification.

AI-generated changes were reviewed and tested rather than accepted
without verification.

## Unverified External Behavior

The checkout endpoint could not be tested as a live backend because the
provided example domain does not resolve. The frontend correctly prepares
the required form fields and invokes form submission.

## Final Verification

The implementation was manually tested for:

- search, category filtering and sorting
- sold-out ordering
- cart operations
- quantity and stock limits
- coupon behavior
- shipping calculation
- pincode validation and delivery status
- checkout form behavior
- responsive layout
- accessibility basics
- content and brand alignment
- SEO metadata and structured data