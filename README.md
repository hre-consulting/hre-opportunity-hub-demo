# HRE Opportunity Hub — Interactive Portfolio Demo

A working demonstration of an opportunity-management system: consistent intake, qualification, pursuit decisions, supplier quote tracking, and follow-up ownership.

**Maintained by HRE Consulting. All buyers, opportunities, quotes, amounts, and activity shown in this demo are fictional.**

## Business problem

Opportunities arrive through multiple channels. Teams need to understand fit, distinguish supplier cost from bid value, assign a next action, and retain the reasoning behind a pursuit decision.

## Try the workflow

1. Search or filter the synthetic pipeline.
2. Open an opportunity and review its screening rationale.
3. Choose Pursue, Review, or No Bid; assign an owner and follow-up date.
4. Record a quote reference and the lowest supplier cost including freight.
5. Use the pricing summaries to locate missing quotes or pending pricing.
6. Create a simulated follow-up or inspect an example Q&A response.
7. Reset the demonstration to its initial state.

Edits stay in the visitor's browser. The demo has no user accounts, central database, procurement feeds, live AI calls, or ClickUp writes.

## Run and build

Requires Node.js 22 or later. There are no third-party runtime dependencies.

```bash
npm test
npm run build
```

Serve `dist/index.html` through your web host or local static server. The output is self-contained. Append `?embed=1` for the workspace-only view. Browser-local persistence depends on browser storage availability, particularly in third-party frames.

## Engineering choices

- Shared pure valuation rules distinguish missing cost from zero.
- Freight is already included in the total and is never added twice.
- RFI and decision-pending exceptions prevent unnecessary quote requests.
- Revision checks reject conflicting quote edits in different browser tabs.
- Demo state migration preserves existing decisions and queued follow-ups.
- Four automated valuation tests check totals, currency validation, exceptions, and tile classifications.

## Production adaptation

A client implementation can use a separately deployed workbook, authenticated server, provider-specific intake, on-demand Q&A, and an explicit task handoff. Those deployment components are not included in this showcase repository. Each client implementation requires its own scope, authorization, credentials, and verification.

## Project status

Portfolio demo v0.2. Desktop and embed behavior have been checked. The new narrow-screen valuation form still needs visual verification. This is a demonstration of the workflow, not evidence of independently measured client outcomes.

## Ownership and reuse

Repository visibility and licensing are separate decisions for the maintainer. This export does not add an open-source license. Review ownership and intended reuse before publishing or licensing the code.

## Links to add before launch

- Public demonstration URL on the HRE domain.
- HRE portfolio or solution page.
- Contact or booking link.
- Desktop screenshot and a short walkthrough video.

Do not publish the original client export, client workbook data, credentials, internal task links, or the private deployment starter in this repository.
