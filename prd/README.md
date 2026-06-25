# POD Operating System PRD

This `prd/` directory is the complete product and engineering blueprint for a fully automated print-on-demand supplier platform.

The product is designed for dropshippers, Shopify sellers, WooCommerce sellers, course communities, print businesses, and internal production teams. The system lets a seller create products from mockups, upload designs, push products to their store, receive orders automatically, pay the supplier upfront through wallet/prepaid balance, and track production, shipping, returns, and inventory from one simple dashboard.

## Core Principle

The business is not just a print shop. The business is infrastructure.

The platform must behave like a print fulfillment operating system where sellers do not need to message the supplier manually for product creation, order placement, shipping updates, returns, or billing.

## Required Folder Structure

```txt
prd/
├── README.md
├── MASTER_PRD.md
├── PRODUCT_VISION.md
├── TECH_STACK.md
├── ARCHITECTURE.md
├── seller-portal/
├── admin-portal/
├── factory-portal/
├── warehouse-portal/
├── product-catalog/
├── mockup-studio/
├── design-engine/
├── shopify-connector/
├── woocommerce-connector/
├── order-engine/
├── wallet-billing/
├── shipping/
├── returns-rto/
├── inventory/
├── notifications/
├── analytics/
├── api/
├── database/
├── ui-ux/
├── devops/
├── security/
└── testing/
```

## Documentation Standard

Every PRD file must be implementation-ready. A developer should be able to build directly from the documents without asking what the screen, table, state, permission, or workflow means.

Each module document should include:

1. Purpose
2. Users and roles
3. Screens
4. Data objects
5. User flows
6. Backend logic
7. API requirements
8. Edge cases
9. Validation rules
10. Permissions
11. Error states
12. Notifications
13. Acceptance criteria
14. QA checklist

## Product Summary

A seller signs up, connects Shopify or WooCommerce, selects a product, uploads a design, previews the product on mockups, sets selling price and profit, pushes the product to their store, and starts receiving orders.

When a customer places an order on the seller's store, the order enters this system automatically through webhooks. The system checks the seller's prepaid wallet balance. If the wallet has enough balance, the order is accepted into production. If not, the order is held until the seller adds funds. This applies even when the seller accepts COD from their end customer. The platform must never produce without supplier payment being secured upfront.

After payment is secured, the system creates a production job, assigns it to printing, packing, and shipping queues, generates labels and tracking, syncs fulfillment status back to Shopify/WooCommerce, and updates the seller dashboard live.

Returned/RTO orders go back into the seller's inventory when reusable. The seller can reship, sell from inventory, or request disposal depending on product condition and platform rules.

## Non-Negotiable Product Rules

- UI must be modern, clean, fast, and extremely simple.
- Seller onboarding must feel easier than using WhatsApp.
- No manual Excel-based operations.
- No order should enter production unless prepaid wallet balance is available.
- COD on seller's customer-facing store is allowed, but supplier billing remains prepaid.
- Returns/RTO must become seller-owned inventory where possible.
- Every order must have a traceable lifecycle.
- Every physical item must be scannable through barcode/QR during production and packing.
- Shopify and WooCommerce connectors are required from the beginning.
- Architecture must support more marketplaces later.
- Architecture must support multiple factories later.
- Documentation must remain under this `prd/` folder.

## Build Target

The intended build is a full SaaS + operations platform, not a small MVP. It should be architected cleanly enough that the system can later scale to multiple product categories, multiple sellers, multiple factories, and high-volume automated fulfillment.
