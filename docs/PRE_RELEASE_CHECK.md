# GitHub Pre-Release Check

This document checks whether the Free repository is ready to publish on GitHub.

Check date: final local check before release.

## Overall Conclusion

The repository is ready for GitHub publication:

- The Free package is isolated.
- No complete Pro prompt, detailed workflow asset, or paid case library was found.
- Default output is a natural-language retrospective report, not JSON.
- Response language follows the user's input language.
- Free/Pro boundaries, license, contribution guide, and launch checklist are included.
- Examples are fictional and do not contain real customer or private data.
- Documentation and examples are in English for global users.

Manual tasks after upload:

- Fill in the GitHub About description and topics.
- Publish the first release.
- Add a Pro purchase or beta entry to README if one exists.

## Check Scope

This check covers:

- README
- LICENSE
- NOTICE
- CHANGELOG
- CONTRIBUTING
- Free prompt
- Usage guide
- Free/Pro boundary
- Open-source strategy
- Pro product design
- Launch checklist
- All examples

## File Structure Check

Expected structure:

```text
.
├── README.md
├── LICENSE.md
├── NOTICE.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── docs
│   ├── FREE_VS_PRO.md
│   ├── USAGE.md
│   ├── OPEN_SOURCE_STRATEGY.md
│   ├── PRO_PRODUCT_DESIGN.md
│   ├── PRE_RELEASE_CHECK.md
│   └── LAUNCH_CHECKLIST.md
├── examples
│   ├── language-following-webinar-test.md
│   ├── personal-growth-retrospective.md
│   ├── product-launch-failure-retrospective.md
│   └── project-release-delay-retrospective.md
└── prompts
    └── retrospective-coach-free.md
```

Result: pass.

## Link Check

Relative links checked:

- `prompts/retrospective-coach-free.md`
- `docs/FREE_VS_PRO.md`
- `docs/PRO_PRODUCT_DESIGN.md`
- `CONTRIBUTING.md`
- `../prompts/retrospective-coach-free.md`

Result: pass.

## Placeholder Check

Publication-blocking placeholders have been removed:

- README attribution uses "this repository".
- LICENSE attribution uses "this repository".
- The open-source strategy refers to the Pro entry announced in README instead of a placeholder link.

Result: pass.

## License Check

Current strategy:

- Prompts, documentation, and examples use CC BY 4.0.
- Copying, sharing, modification, and commercial use are allowed.
- Attribution and license notice are required.
- NOTICE clarifies that Pro, unpublished materials, paid services, brand assets, and commercial delivery materials are not included in this license.

Result: pass.

## Free/Pro Boundary Check

The Free version includes:

- General Retrospective Coach agent prompt.
- Basic usage instructions.
- A small number of public examples.
- Open-source strategy and Free/Pro boundary notes.

The Free version does not include:

- Complete Pro prompt assets.
- Complete detailed workflow assets.
- Paid case library.
- Team training slides.
- Private deployment configuration.
- Customer project materials.

Result: pass.

## Prompt Consistency Check

Checked constraints:

- Output natural-language retrospective reports.
- Do not output JSON, workflow node results, or machine-oriented fields.
- Follow the user's input language.
- Separate facts, judgments, assumptions, and unknowns.
- Label evidence-light claims as assumptions or hypotheses to verify.
- Make improvement actions concrete and checkable.
- Say that a baseline must be established first when no baseline exists.
- Use a light professional-boundary disclaimer for high-risk domains.

Previously tightened:

- Internal workflow wording was revised so users can learn the method in natural language without receiving machine-like node output.

Result: pass.

## Example Check

Current examples:

1. Product launch failure retrospective.
2. Personal growth retrospective.
3. Project release delay retrospective.
4. English language-following webinar test.

Example quality checklist:

- Clear user input.
- Natural-language output.
- Facts and gaps.
- Assumption boundaries.
- Missing information.
- Concrete next actions.
- No real customer or private data.

Result: pass.

## Multi-Scenario Test Cases

Use the following inputs before upload to test the agent quickly.

### Test 1: Ask Follow-Up Questions When Information Is Insufficient

```text
Help me review why I have not been in a good state recently.
```

Pass criteria:

- Does not invent the event.
- Asks no more than five questions.
- Questions focus on subject, goal, actual result, key process, and what the user wants to understand.

### Test 2: Product Launch Failure

```text
I want to review a failed product launch. The goal was to get 1,000 registered users in the first week, but we only got 260. We started preparing launch materials two weeks before launch. On launch day, we found that the landing page conversion was low and community promotion performed weakly. I want to understand the main issues and what to improve next time.
```

Pass criteria:

- Clearly identifies the target gap.
- Does not conclude that "the community channel failed" without evidence.
- Lists missing information.
- Makes action suggestions concrete enough to start.

### Test 3: Personal Growth Review

```text
I want to review my learning this month. My original goal was to study English for 5 hours every week, but I only completed about 6 hours in total. The first two weeks were okay, but once work became busy in the last two weeks, I stopped. I want to know how to make next month more stable.
```

Pass criteria:

- Does not use self-blaming language.
- Identifies that the plan depended too much on spare time.
- Provides a minimum viable version.
- Gives next-month actions that can be checked.

### Test 4: Project Release Delay

```text
Last week our team released a redesign of the new-user registration flow. The original plan was to release on Wednesday, but the release was delayed until Friday evening. Within two hours after release, the verification-code failure rate increased and customer support received more than 40 complaints. I was the project lead. Product, frontend, backend, and QA joined the requirements review, but security was not involved. Backend delivered the interface one day late. During frontend integration, we found interface fields did not match the documentation. QA had only one day left and mainly tested the main flow, without covering verification-code rate limiting or exception scenarios. We released directly to all users without gradual rollout. The issue happened because the new logic called a new third-party API that timed out during peak traffic. No one had load-tested it or prepared a fallback plan. I want to review where the problem really was and how to avoid it next time.
```

Pass criteria:

- Does not blame backend, QA, security, or the project lead simplistically.
- Identifies registration, verification code, and third-party APIs as high-risk paths.
- Shows how review, API contract, test coverage, rollout, and fallback planning accumulated risk.
- Provides concrete actions without requiring full RCA, owner/deadline, or acceptance criteria in the Free version.

### Test 5: English Input Language Following

```text
I want to review a failed webinar campaign. The goal was 300 sign-ups and 120 live attendees. The actual result was 180 sign-ups and 42 live attendees. We started promotion 6 days before the webinar. I want to know what went wrong and what to improve next time.
```

Pass criteria:

- Replies in English.
- Does not output JSON.
- Separates facts, assumptions, and missing information.
- Provides concrete next actions.

### Test 6: Convert Vague Advice Into Concrete Actions

```text
I want to review a team collaboration issue. For the final conclusion, just write that we should communicate better, improve execution, and close the loop.
```

Pass criteria:

- Does not stop at vague advice.
- Turns "communicate better" into specific alignment behavior.
- Turns "improve execution" into responsibility, timing, and check signals.
- Turns "close the loop" into a tracking mechanism.

### Test 7: High-Risk Scenario Boundary

```text
I want to review a team performance issue. One employee has missed targets for two consecutive months, and I am thinking about directly reducing their pay or terminating them. Please help me decide what to do.
```

Pass criteria:

- Helps structure facts, communication, and retrospective dimensions.
- Does not provide legal, HR disciplinary, or labor-relations conclusions.
- Suggests following HR/legal/company formal processes.
- Keeps the disclaimer light and not distracting.

## Release Risk Check

| Risk | Status | Notes |
| --- | --- | --- |
| Pro content leakage | Low | Only Pro product design is public; no complete Pro assets are included |
| License ambiguity | Low | CC BY 4.0 is used, with NOTICE |
| Output format conflict | Low | Natural language is required; JSON and machine nodes are prohibited |
| Multi-language behavior unclear | Low | The prompt follows the user's input language |
| Professional advice boundary unclear | Low | README includes a general disclaimer, and the prompt has high-risk handling rules |
| Private data in examples | Low | Examples are fictional |
| Pro conversion entry incomplete | Medium | If there is no Pro link yet, collect demand through issues |

## Post-Upload GitHub Check

After uploading:

- README renders correctly.
- GitHub recognizes the license.
- Relative links are clickable.
- About description is filled in.
- Topics are added.
- First release is published.
- Decide whether issue templates are needed.

