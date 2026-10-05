# Clearledger: Evidence-First Payment Review

A UI/UX prototype entered in Hyperbloom October 2026 by GitHub/Devpost `m7mdd77`.

## Problem

Seeing a payment is not the same as proving an invoice is settled. Partial payments, refunds, ambiguous references and mixed currencies need an evidence-first review flow, not a reassuring but misleading paid badge.

## Try the prototype

1. Download and extract `clearledger-source.zip`; install Node.js 22 or later.
2. In the extracted folder run `npm ci` and `npm start`.
3. Open `http://127.0.0.1:3221`. Filter invoices, inspect the refund exception, import the included synthetic JSON files, and toggle identifier masking.

Run `npm test` and `npm run check` for automated verification. On October 5, 2026, 64 tests passed with no failures or skips, and syntax checks passed. Tests cover accounting and input/transport contracts, not a full usability study or every browser interaction.

## Design decisions

- An invoice table and adjacent exception queue let users compare totals with unresolved evidence.
- Partial, unpaid, overpaid and review-required states stay distinct.
- Refund-affected records do not silently become paid invoices.
- Exact integer minor-unit accounting supports currencies with different decimal precision.
- Search, status filtering, labeled controls and identifier masking support repeated review work.
- Failed imports retain the previous valid report rather than replacing it with incomplete data.

## Honest limitations

This competition demonstration uses synthetic records. It does not perform payments, refunds or customer messaging. The optional PayPal reader was separately verified against one bounded sandbox reporting window, but no account credentials or real transaction records are distributed here. That verification does not establish production readiness.

The optional local-AI adapter is not verified with an actual running model. Do not interpret its presence or fixture-based tests as live AI integration. No model, sandbox account or credentials are needed for the synthetic design demo. AI review may report unavailable.

The screenshots show an earlier local UI iteration using synthetic records. Existing project components were developed before entry registration; this is disclosed reuse, not a claim that the whole project was built after registration. Development and submission preparation used substantial AI assistance, including Codex.

There has been no merchant usability study, production deployment, verified financial outcome or earned prize. This entry is a functional design prototype, not an eligible completed PayPal AI Hackathon submission.

## Package boundary

The source archive includes application code, synthetic fixtures and tests. It excludes `.env`, credentials, caches, node_modules, downloaded runtimes, private reports and runtime logs. Lucide icons are installed from the pinned package dependency; its own license applies. No new license grant is claimed for unrelated workspace files.
