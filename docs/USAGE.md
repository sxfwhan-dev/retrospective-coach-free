# Usage Guide

## 1. Use in ChatGPT, Claude, Gemini, or Similar Chat Tools

1. Open [../prompts/retrospective-coach-free.md](../prompts/retrospective-coach-free.md).
2. Copy the "Agent System Prompt" section.
3. Paste it into your AI tool as the system prompt or role instruction.
4. Enter the event, project, or experience you want to review.

Recommended input format:

```text
Retrospective subject:
Context:
Original goal:
Actual result:
Process description:
The main question I want to answer:
```

You can also paste an unstructured story. Retrospective Coach will extract the key information automatically.

## 2. Use in GPTs, Claude Projects, or Agent Platforms

Recommended configuration:

- Name: Retrospective Coach Free
- Description: Helps users extract facts, gaps, lessons, capability insights, and improvement actions from events, projects, or experiences.
- System prompt: Use the agent system prompt in [../prompts/retrospective-coach-free.md](../prompts/retrospective-coach-free.md).
- Output format: Natural-language retrospective report.
- Default language: Follow the user's input language. If the user specifies an output language, use that language.

## 3. Example User Input

```text
I want to review a failed job interview.
The goal was to get a product manager offer, but I was rejected after the second interview.
I prepared my project stories, but when the interviewer asked about metrics and decision logic, my answers became scattered.
I want to understand the main issue and how to prepare next time.
```

## 4. Useful Follow-Up Prompts

If the result is not concrete enough, you can ask:

```text
Please make the action suggestions more concrete and turn them into a 7-day plan.
```

```text
Please separate facts from assumptions.
```

```text
Please rewrite this retrospective for a team audience.
```

## 5. Usage Boundary

Retrospective Coach Free is designed for lightweight retrospectives and personal use. If you need team mechanisms, standardized workflows, multi-role collaboration, case libraries, industry templates, or deployment packages, use the Pro version.

AI-generated retrospective content is for reflection, communication, and improvement support only. It does not constitute legal, medical, financial, HR, or other professional advice. For high-risk or professional matters, consult qualified professionals and follow the formal processes of your organization.

