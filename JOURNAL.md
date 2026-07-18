## Week 7 — Issue selection

**Issue link:** https://github.com/ascherj/pathreview/issues/146

**Issue title:** PII scrubber fails to redact parenthesized US phone numbers

**Tier:**  Tier 1

**Problem summary:**
Pii_scrubber is failing to detect US phone numbers using the parenthesized format. This issue impacts scrub() and detect(), and is most likely an issue with the regex for US phone numbers.

**Branch name:** fix/146-paranthesized-US-phone-number-redaction

**Setup confirmation:** App runs locally at localhost:5173

**Cohort ledger:** Issue added to cohort ledger