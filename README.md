# Retrospective Coach Free

Retrospective Coach Free is a free AI agent prompt that helps individuals and teams turn an event, project, action, meeting, experiment, or personal experience into a clear retrospective with lessons and next actions.

It is useful for:

- Project retrospectives
- Meeting retrospectives
- Sales retrospectives
- Interview retrospectives
- Presentation retrospectives
- Content retrospectives
- Growth experiment reviews
- Weekly or monthly personal reviews
- Team phase reviews
- Failure reviews
- Success pattern extraction
- Personal growth reviews

This repository contains the Free version. It is designed to be easy to use, easy to share, and useful enough for lightweight retrospectives. More complete scenario templates, detailed workflows, case libraries, deployment packages, and team operating materials are reserved for the Pro version.

## Core Capabilities

Retrospective Coach helps you:

1. Reconstruct facts, goals, and context.
2. Identify the gap between expected and actual results.
3. Separate facts, judgments, assumptions, and unknowns.
4. Extract success patterns, failure lessons, turning points, and anti-patterns.
5. Turn lessons into capabilities, principles, methods, or checklists.
6. Design short-term and mid-term improvement actions.
7. Define signals that make the next cycle easier to review.

It does not force JSON output or expose workflow nodes to end users. The default output is a readable natural-language retrospective report, and the response language follows the user's input language.

## Quick Start

1. Open [prompts/retrospective-coach-free.md](prompts/retrospective-coach-free.md).
2. Copy the "Agent System Prompt" section into your AI tool as the system prompt or role instruction.
3. Send the event, project, or experience you want to review.
4. If key information is missing, Retrospective Coach will ask a few focused questions or produce an initial review based on what is available.

Example input:

```text
I want to review a failed product launch.
The goal was to get 1,000 registered users in the first week, but we only got 260.
We started preparing launch materials two weeks before launch. On launch day, we found that the landing page conversion was low and community promotion performed weakly.
I want to understand the main issues and what to improve next time.
```

## Repository Structure

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

## Free and Pro

The Free version is for personal learning, lightweight retrospectives, and adaptation by the community.

The Pro version is for users who need a more complete retrospective system, including multi-scenario templates, detailed workflows, case libraries, deployment packages, and team operating materials.

See [docs/FREE_VS_PRO.md](docs/FREE_VS_PRO.md) for the detailed boundary.

## Pro Version

The Pro version will provide a more complete retrospective system, including scenario-specific templates, detailed workflows, a case library, team retrospective mechanisms, and agent deployment packages.

If you want to join the Pro beta or share which retrospective scenarios you need most, please leave an issue.

See [docs/PRO_PRODUCT_DESIGN.md](docs/PRO_PRODUCT_DESIGN.md) for the product design.

## License

The prompt, documentation, and examples in this repository are released under the [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) license.

You may copy, share, modify, build upon, and use the materials commercially, as long as you provide attribution and keep the license notice.

Recommended attribution:

```text
Based on "Retrospective Coach Free", licensed under CC BY 4.0. Original project: this repository.
```

This repository only licenses the Free version materials. The Pro version, unpublished materials, paid services, brand assets, and commercial delivery materials are not included in this repository's license.

## Contributing

Issues and pull requests are welcome, especially for:

- Better retrospective examples
- Clearer prompt wording
- More concrete action templates
- Better alternatives to vague advice
- Usage notes for different AI tools

Please read [CONTRIBUTING.md](CONTRIBUTING.md) before contributing.

## Disclaimer

AI-generated retrospective content is for reflection, communication, and improvement support only. It does not constitute legal, medical, financial, HR, or other professional advice. For high-risk or professional matters, consult qualified professionals and follow the formal processes of your organization.

