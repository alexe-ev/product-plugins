# Experiment Quality Audit: Redesigned In-App Tooltip System

## Quality Verdict
**Low confidence** — DO NOT SHIP

---

## Major Risks

### 1. **FATAL: Sample Ratio Mismatch (SRM) — Severe Allocation Imbalance**

The experiment shows a significant departure from the intended 50/50 split:

- **Control:** 6,203 total enrollments (46.5%)
- **Test:** 7,143 total enrollments (53.5%)
- **Difference:** +940 test users, representing a 7 percentage point deviation from the target 50/50 split

This allocation imbalance is a red flag for potential assignment or collection issues. A 50/50 split intended but 46.5/53.5 observed violates basic randomization assumptions and undermines trustworthiness.

### 2. **FATAL: Day 3 Enrollment Spike in Test Arm — Anomalous Data Quality Issue**

Day 3 shows a dramatic and unexplained spike in test arm enrollment:

- **Day 3 Test:** 1,287 enrollments (nearly 3× the typical daily average of ~440)
- **Day 3 Control:** 415 enrollments (roughly normal)
- **Day 3 Ratio:** 1,287:415 = ~3.1:1 (highly imbalanced)

Days 1, 2, 4–14 show roughly balanced enrollment patterns (~430–460 per variant per day). Day 3 is a stark outlier.

**Possible explanations (unconfirmed):**
- A data logging bug or duplicate ingestion on Day 3
- A temporary assignment algorithm failure
- A production incident that re-routed users to the test arm
- An uncontrolled traffic spike affecting only the test variant

**Current status:** The spike is unexplained and unresolved.

### 3. **Fatal Implication: The Overall Result is Unreliable**

The combination of the overall 7-point allocation imbalance and the Day 3 spike means:

- The test group differs systematically in size and composition from the control group
- Classical statistical inference (p-value = 0.031) assumes a fair random assignment
- The imbalance violates that assumption

A formal Sample Ratio Mismatch (SRM) check (e.g., Chi-squared goodness-of-fit test) would almost certainly flag this as a serious problem. The p-value of 0.031 reflects only the observed metric difference, not whether the experiment was run correctly.

---

## Reliability Level
**Low**

The predefined sample size and stopping rule are positive procedural elements. However, they cannot overcome the fundamental data quality and allocation issues revealed in the enrollment logs.

---

## Fatal vs. Manageable Issues

| Issue | Category | Justification |
|-------|----------|---|
| Overall 46.5/53.5 allocation imbalance (7pp deviation) | **Fatal** | Violates randomization assumptions; indicates systematic assignment or data collection failure |
| Day 3 test spike (1,287 enrollments vs. ~440 expected) | **Fatal** | Unexplained 3× anomaly; suggests logging, algorithm, or traffic bug |
| P-value reliability under imbalance | **Fatal** | Classical p-value assumes proper randomization; imbalance undermines that assumption |

---

## Root Cause Recommendations

**Before any shipping decision, the team must:**

1. **Investigate the Day 3 enrollment spike immediately**
   - Was there a code deployment on Day 3?
   - Did the assignment algorithm behave differently on Day 3?
   - Are there duplicate records, logs, or data ingestion errors in the test arm for Day 3?
   - Check server logs, assignment system logs, and data warehouse audit trails

2. **Perform a formal Sample Ratio Mismatch (SRM) check**
   - Conduct a Chi-squared goodness-of-fit test: expected 50/50 vs. observed 46.5/53.5
   - Calculate the test statistic and p-value
   - Standard practice: p < 0.05 is concerning; p < 0.01 is a strong signal of assignment failure
   - If SRM p < 0.05, the experiment must be considered compromised

3. **Re-examine the enrollment data for the test arm**
   - Validate that Day 3 test enrollments are unique users (not duplicates)
   - Check for any data pipeline, logging, or ETL issues specific to Day 3

4. **If Day 3 data is confirmed as erroneous:**
   - Consider whether a corrected analysis (e.g., excluding Day 3) would still support the result
   - A rerun may be necessary to build confidence

---

## Recommendation
**Do not ship.**

The +1.4 percentage point uplift with p = 0.031 would normally merit cautious consideration. However:
- The severe allocation imbalance (46.5/53.5 vs. intended 50/50) is a red flag for broken randomization
- The unexplained Day 3 test spike (3× normal enrollment) suggests a data or assignment bug
- Until the root causes are understood and ruled out, the p-value cannot be trusted
- Shipping based on this result risks amplifying a systematic error

**Required path forward:**
1. Root-cause the Day 3 spike
2. Perform SRM check
3. Confirm the test arm data quality
4. Either rerun the experiment with confirmed good data, or report findings to the analytics team for investigation

---

## Missing Procedural Evidence
- Why did enrollment spike 3× on Day 3 specifically in the test arm?
- How are users assigned to variants? Is the assignment algorithm deterministic, randomized, or based on client-side logic?
- Was the assignment system or code modified on or before Day 3?
- Are there data quality checks or validation rules that would have caught an enrollment anomaly?

---

## Summary
This experiment fails the trustworthiness bar due to **Sample Ratio Mismatch and unexplained allocation anomalies**. The p-value of 0.031 is secondary to the more fundamental concern that the experiment was not run as intended. Investigation and rerun are required.
