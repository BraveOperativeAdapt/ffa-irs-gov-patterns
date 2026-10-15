# ffa-irs-gov-patterns

Architecture patterns for the IRS.gov/freefile hop that actually unlocks [TaxAct Free File](https://github.com/topics/taxact-free-file).

Brand desktop: [Taxcact-Alternative-Desktop](https://github.com/BraveOperativeAdapt/Taxcact-Alternative-Desktop). Hub: [awesome-taxact-free-file](https://github.com/BraveOperativeAdapt/awesome-taxact-free-file). Not affiliated with TaxAct Holdings.

## Problem

Bookmarking taxact.com/ffa still opens a commercial cart for people who already have a TaxAct login. TaxAct’s help file says Free File Alliance registration must start on the IRS (or participating state) site.

## Patterns

1. **Entry hop** — human opens IRS.gov/freefile, chooses TaxAct, then creates or signs in. [irs-entry-guard](https://github.com/BraveOperativeAdapt/irs-entry-guard) paints FAIL_COMMERCIAL on marketing hosts.
2. **Two-predicate eligibility** — [agi-age-ffa-gate](https://github.com/BraveOperativeAdapt/agi-age-ffa-gate) before the hop; military is [military-ffa-pass](https://github.com/BraveOperativeAdapt/military-ffa-pass).
3. **State after federal** — [ten-state-zero-matrix](https://github.com/BraveOperativeAdapt/ten-state-zero-matrix).
4. **Over-cap** — [fillable-forms-overflow](https://github.com/BraveOperativeAdapt/fillable-forms-overflow), not a second TaxAct SKU.
5. **Skipped hop** — one-way handoff into the desktop STOP screen; do not append fake `?ffa=` query params.

## Non-goals

No MeF transmitter. No scraping of TaxAct. No Quicken import (unsupported).
