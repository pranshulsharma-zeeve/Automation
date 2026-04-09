# Open Questions

Only high-value unresolved questions that block reliable completion of the Foundation Pack.

1. **Product direction lock:** Should the Foundation Pack be aligned to the GolDefi digital-gold tokenization product defined in `/docs/product/srs.md`, or should the SRS be replaced with one for the current “Foundation Pack Orchestrator” concept?
2. **MVP boundary confirmation:** If GolDefi is the target, which payment methods are in MVP (USDT, card via Stripe, bank transfer, cash via distributor), and which are explicitly deferred?
3. **Compliance baseline:** What exact compliance obligations are mandatory for MVP (e.g., KYC/AML jurisdictions, data residency, retention, sanctions screening, auditability)?
4. **Blockchain execution model:** Which chain/environment and smart-contract control model are required in MVP (direct MetaMask only vs relayer/meta-transactions, threshold routing behavior, signer authorization model)?
5. **Operational ownership:** Who is the final approval authority for tokenization, redemption, audit exceptions, and readiness-to-backlog decisions?
6. **External integration contracts:** What are the required integration SLAs/error-handling expectations for Sumsub, Stripe, bank verification process, wallet providers, and email/SMS providers?
7. **Non-functional targets:** What are the approved MVP SLOs for availability, latency, throughput, RTO/RPO, and security incident response?
8. **Fee/valuation governance:** What source-of-truth and cadence govern gold rate updates, platform fee tables, and dispute handling for quote/payment mismatches?
