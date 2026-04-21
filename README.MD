# AI Agentic Skills and Agents Copilot Setup

This repository is a GitHub Copilot customization pack centered around the `.github` directory. It includes reusable agents, skills, prompts, command templates, hooks, and design references that can be copied into another repository or adapted in place.

## What's Included

### Custom Agents
`.github/agents/` contains a large library of agent definitions for workflows such as code review, accessibility, debugging, architecture, documentation, performance, security, GitHub operations, and language-specific development.

### Skills
`.github/skills/` contains skill folders and supporting docs used to extend agent behavior. The collection spans frontend and full-stack development, testing, debugging, content generation, document tooling, refactoring, planning, and repository documentation.

### Prompts
`.github/prompts/` contains reusable prompt files for recurring workflows such as feature work, UX review, e-learning generation, upgrades, and meta-prompting.

### Commands and Hooks
`.github/commands/` contains markdown command templates for common repo tasks, and `.github/hooks/` contains skill evaluation scripts plus JSON rule definitions and schema files.

### Project Context and References
The repository also includes shared Copilot instructions, an `about-me.md` context file, a `design-md/` reference library, and an archived `.zip` asset inside `.github/`.

## Current Structure

```text
agent-skills/
├── .github/
│   ├── about-me.md
│   ├── agents/                    # Agent definitions and supporting metadata
│   ├── commands/                  # Reusable command templates
│   ├── copilot-instructions.md    # Shared Copilot behavior and repo guidance
│   ├── design-md/                 # Reference design system/example sources
│   ├── grand-ai-hotel-main.zip    # Archived asset kept in-repo
│   ├── hooks/                     # Skill evaluation scripts, rules, and schema
│   ├── prompts/                   # Reusable prompt templates
│   └── skills/                    # Skill folders and supporting docs
└── README.MD
```

## Notable Subdirectories

- `.github/agents/`: individual `.agent.md` files, supporting `.md` agent definitions, preferences files, and `SOURCE_REGISTRY.json`.
- `.github/skills/`: one folder per skill plus supporting docs such as `README.md`, `quick-reference.md`, and diagram/reference files.
- `.github/prompts/`: prompt files like `add-feature`, `ux-review`, `upgrade-prompt`, and `metaprompt-maker`.
- `.github/commands/`: task-oriented command docs such as onboarding, PR review, ticket writing, and documentation sync.
- `.github/hooks/`: shell and JavaScript evaluation helpers plus JSON rule configuration.
- `.github/design-md/`: brand and product reference folders used for design-oriented work.

## Getting Started

1. Clone this repository.
2. Copy the parts of `.github/` you want into your target repository.
3. Adjust `copilot-instructions.md`, agent definitions, skills, and prompts to match your workflow.
4. Keep the structure intact if you want GitHub Copilot and related tooling to discover these assets consistently.

## Maintenance Note

If you add or remove directories under `.github/`, update this README so the documented structure stays aligned with the repository.