# Example: Project Release Delay Retrospective

This case tests whether Retrospective Coach Free can handle a more complex project scenario without simplistic blame. It should separate facts from assumptions, identify risk accumulation, and produce concrete improvement actions.

## User Input

```text
Last week our team released a redesign of the new-user registration flow. The original plan was to release on Wednesday, but the release was delayed until Friday evening. Within two hours after release, the verification-code failure rate increased and customer support received more than 40 complaints.

I was the project lead. Looking back, product, frontend, backend, and QA joined the requirements review, but the security team was not involved. During development, backend delivered the interface one day later than expected. During frontend integration, we found that the interface fields did not match the documentation. QA had only one day left and mainly tested the main flow. They did not cover verification-code rate limiting or exception scenarios.

On release day, we did not do a gradual rollout. We released to all users directly. The verification-code issue happened because the new logic called a new API from a third-party service, and that API timed out during peak traffic. No one had done a load test, and no fallback plan was prepared.

I want to review where the problem really was and how to avoid it next time.
```

## Example Output

### Retrospective Conclusion

The issue was not just "the release was delayed" or "backend delivered one day late". The registration flow is a high-risk user path, but the project lacked key gates in risk review, API contract management, test coverage, release strategy, and fallback planning. As a result, the team released a still-unverified risk directly to all users.

### Facts and Gaps

- Original plan: release on Wednesday.
- Actual result: released on Friday evening.
- Post-release issue: verification-code failure rate increased within two hours.
- User impact: customer support received more than 40 complaints.
- Known facts:
  - Security was not involved in the requirements review.
  - Backend delivered the interface one day late.
  - Frontend integration found field mismatches between interface and documentation.
  - QA had only one day left and mainly tested the main flow.
  - Verification-code rate limiting and exception scenarios were not covered.
  - The team did not use a gradual rollout.
  - The new logic called a new third-party API that timed out during peak traffic.
  - No load test or fallback plan was prepared.

### Key Findings

1. The requirements review missed a risk role for the registration and verification-code path.
   - Evidence: product, frontend, backend, and QA joined the review, but security was not involved.
   - Confidence: medium.
   - Boundary: security participation would not guarantee prevention, but the missing security or risk-control perspective reduced the chance of identifying verification-code, rate-limit, and exception risks early.

2. API contract management was weak and compressed integration and testing time.
   - Evidence: backend delivered one day late, and frontend found field mismatches during integration.
   - Confidence: high.

3. The test strategy focused on the happy path and missed the real risk scenarios.
   - Evidence: QA had only one day and mainly tested the main flow, without covering rate limiting or exception scenarios.
   - Confidence: high.

4. Direct full release amplified the impact.
   - Evidence: the team skipped gradual rollout and received more than 40 complaints within two hours.
   - Confidence: high.

5. The new third-party API lacked availability validation and fallback planning.
   - Evidence: the new API timed out during peak traffic; there was no load test and no fallback plan.
   - Confidence: high.

### Lessons

- Registration, login, payment, verification-code, and permission flows should not be treated as ordinary feature changes. They require explicit risk review.
- Delay is not the only risk. A compressed testing window becomes dangerous when release standards are not raised accordingly.
- Happy-path testing is insufficient for real production risk. Rate limiting, timeout, third-party failure, and exception paths must be tested.
- Any new third-party API should have load testing, timeout handling, retry logic, and fallback plans before release.
- Full rollout is appropriate for low-risk changes, not for high-risk paths with unverified failure modes.

### Improvement Actions

1. P0: Create a release gate for critical user paths.
   - First step: classify registration, login, verification code, payment, permission, and third-party service calls as mandatory risk items.
   - Check signal: if a change hits any risk item, security, risk-control, operations, or relevant owners must be added to the review.
   - Readiness: ready to start.

2. P0: Use gradual rollout by default for critical paths.
   - First step: next time, release registration-flow changes to a small percentage of traffic first and monitor verification-code success rate, registration conversion, and complaint volume.
   - Check signal: expand only after rollout metrics are stable.
   - Readiness: baseline needed first.

3. P1: Add an API contract freeze mechanism.
   - First step: after requirements review, produce an API field table and have frontend and backend confirm fields, error codes, and exception responses before integration.
   - Check signal: integration no longer gets blocked by field-document mismatch.
   - Readiness: baseline needed first.

4. P1: Define a pre-release testing entry bar.
   - First step: if testing time falls below the agreed minimum, the project lead must reassess whether to delay, reduce scope, or switch to gradual rollout.
   - Check signal: main flow, exception scenarios, rate limiting, and third-party failure all have test records.
   - Readiness: ready to start.

5. P1: Prepare a fallback plan for third-party services.
   - First step: define what happens when the third-party API times out, such as switching back to the old API, delayed retry, backup verification channel, or temporary user messaging.
   - Check signal: load tests and failure drills verify that the fallback path works.
   - Readiness: baseline needed first.

### Missing Information

- The actual verification-code failure rate.
- Why the team decided to release on Friday after the Wednesday delay.
- Third-party timeout rate, peak QPS, and SLA.
- Whether monitoring alerts existed and how long detection and mitigation took.
- Whether complaints were concentrated in specific devices, regions, or channels.

### Free Version Test Evaluation

Pass level: excellent Free-version pass.

The output completes basic retrospective analysis, identifies mechanism-level issues, and provides concrete action suggestions. It separates facts from assumptions and does not blame backend, QA, or the project lead simplistically. Instead, it identifies risk accumulation across review, API contract, testing coverage, release strategy, and fallback planning.

Areas left for the Pro version:

- Stronger coaching questions, such as asking the project lead to revisit key decision points.
- Full RCA, 5 Whys, or fishbone analysis.
- Owner / deadline / acceptance criteria.
- Monitoring thresholds, alert rules, and release-gate templates.

