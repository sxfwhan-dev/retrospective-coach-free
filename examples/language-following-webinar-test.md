# Test Case: Language-Following Webinar Retrospective

This case tests whether Retrospective Coach Free follows the user's input language, avoids JSON output, distinguishes facts from assumptions, and provides concrete next actions.

## User Input

```text
I want to review a failed webinar campaign.

The goal was to get 300 sign-ups and at least 120 live attendees.
The actual result was 180 sign-ups and 42 live attendees.

We started promotion 6 days before the webinar. Most traffic came from LinkedIn posts and one email newsletter.
The topic was "How AI can improve team productivity", but the landing page only had a short description and no speaker bio.
During the webinar, several attendees asked basic questions, and only 5 people requested a follow-up demo.

I want to understand what went wrong and what we should improve before the next webinar.
```

## Expected Behavior

The coach should:

1. Reply in English because the user input is in English.
2. Output a readable retrospective report, not JSON.
3. Clearly state the gap between target and actual results.
4. Mark weak conclusions as assumptions or hypotheses.
5. Avoid unsupported claims such as "the topic was bad" or "LinkedIn did not work" unless evidence is provided.
6. Provide concrete next actions with first steps and checkable signals.
7. Mention missing information, such as landing page visits, conversion rate, email open rate, LinkedIn reach, audience profile, and registration source breakdown.

## Example Output

### Retrospective Conclusion

The campaign underperformed mainly because the promotion window, conversion page, and audience qualification were not validated early enough. The available facts show a clear gap in both sign-ups and live attendance, but the exact cause still needs channel and landing-page data.

### Facts and Gaps

- Original goal: 300 sign-ups and at least 120 live attendees.
- Actual result: 180 sign-ups and 42 live attendees.
- Sign-up gap: 120 fewer sign-ups than planned.
- Attendance gap: 78 fewer live attendees than planned.
- Known facts:
  - Promotion started 6 days before the webinar.
  - Main traffic sources were LinkedIn posts and one email newsletter.
  - The landing page had a short description and no speaker bio.
  - Several attendees asked basic questions during the webinar.
  - 5 people requested a follow-up demo.

### Key Findings

1. The promotion window may have been too short for the sign-up target.
   - Evidence: promotion started only 6 days before the webinar.
   - Confidence: medium.
   - Note: this is still an assumption because historical webinar promotion benchmarks are not provided.

2. The landing page likely did not provide enough trust and decision support.
   - Evidence: the page had only a short description and no speaker bio.
   - Confidence: medium.
   - What to verify: landing-page visit-to-registration conversion rate.

3. The live audience may not have been well qualified for a demo-oriented outcome.
   - Evidence: several attendees asked basic questions, and only 5 requested a demo.
   - Confidence: medium.
   - What to verify: attendee roles, company profiles, source channels, and intent level.

### Lessons

- A webinar campaign should validate the conversion path before the main promotion push, not after the event is already scheduled.
- A broad topic such as "AI and productivity" needs sharper audience framing; otherwise, it may attract curious learners instead of high-intent buyers.
- Registration targets should be broken into funnel metrics: reach, landing-page visits, registration rate, attendance rate, and follow-up request rate.

### Next Actions

1. Build a simple webinar funnel dashboard before the next campaign.
   - First step: track reach, landing-page visits, registrations, live attendance, and demo requests by channel.
   - Check signal: each channel has visible conversion data before the next campaign review.
   - Measurement readiness: baseline needed.

2. Rewrite the landing page with stronger decision support.
   - First step: add speaker bio, target audience, specific takeaways, agenda, and who the session is not for.
   - Check signal: landing-page registration rate can be compared before and after the rewrite.
   - Measurement readiness: baseline needed.

3. Start promotion earlier and run a small message test first.
   - First step: test 2-3 topic angles on LinkedIn or email 14 days before the webinar.
   - Check signal: select the message with the highest qualified click or registration signal.
   - Measurement readiness: baseline needed.

### Missing Information

- Landing page visits and registration conversion rate.
- LinkedIn impressions, clicks, and registrations.
- Email open rate, click rate, and registrations.
- Registration source breakdown.
- Attendee roles, company types, and intent level.
- Historical webinar benchmarks.

### Next Review Focus

For the next webinar, review whether the team validated audience-message fit and landing-page conversion before scaling promotion.

## Check Result

This test case passes if the output remains in English, stays readable, avoids JSON, marks assumptions clearly, and turns improvement directions into concrete actions.

