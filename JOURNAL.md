## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/146

**Issue title:** PII scrubber fails to redact parenthesized US phone numbers

**Tier:**  Tier 1

**Problem summary:**
Pii_scrubber is failing to detect US phone numbers using the parenthesized format. This issue impacts scrub() and detect(), and is most likely an issue with the regex for US phone numbers.

**Branch name:** fix/146-paranthesized-US-phone-number-redaction

**Setup confirmation:** App runs locally at localhost:5173

**Cohort ledger:** Issue added to cohort ledger

## Week 8

bug reproduction: running the pytests in tests/unit/test_pii_scrubber.py results in fails for test_us_phone_number_redaction, test_us_phone_formats, test_detect_phone_pii, and test_phone_at_start_of_text.

## Week 8 — Reproduction & solution planning

**Reproduction commit link:** https://github.com/JacobKwiat1/pathreview/commit/052a6c21ca62c589391228b2b0551283ebb8f61c

**Reproduction summary:**
I ran the pytests for pii_scrubber and observed that formats using parentheses do indeed fail to be caught.

**PLAN.md link:** https://github.com/JacobKwiat1/pathreview/blob/fix/146-parenthesized-us-phone-number-redaction/PLAN.md

**Blockers or open questions:**
