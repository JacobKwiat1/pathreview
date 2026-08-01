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


## Week 9 — Solution building & PR submission

### Check-in 1 (mid-week)

**Current progress:**
I have not had the chance to make any changes yet this week.

**Next steps:**
I will be implementing a change to the phone_us regex in pii_scrubber.py to fix the issue

**Blockers:**


---

### Check-in 2 (end of week)

**PR link:** https://github.com/ascherj/pathreview/pull/517

**Branch:** https://github.com/JacobKwiat1/pathreview/tree/fix/146-parenthesized-us-phone-number-redaction

**What you built:**
My fix was a change to the phone_us pattern in pii_scrubber.py. I added a space to the character set [-.] which was not detecting spaces between numbers and misaligning space and parthesized phone formats from the pattern.

**Tests added or updated:**
The only change I made was to the phone_us pattern in pii_scrubber. I did not change any tests because there was already sufficient tests to determine if the code works.

**Self-review confirmation:** [X] make check passes  [X] make test-unit passes
note: there are two ruff failures, but neither failure is related to the code that I changed.

**Draft PR feedback received from:** none