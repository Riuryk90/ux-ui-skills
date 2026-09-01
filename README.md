# UX/UI Skills

Version: 1.0.0 public package

Author: Wincenth Matthews Muñoz

License: MIT

This package contains two standalone skills:

- `ux-ui-build`: for designing, building, or improving user-facing interfaces when implementation or solution-oriented design help is wanted.
- `ux-ui-review`: for read-only expert UX/UI review of existing interfaces, pages, components, flows, screenshots, or frontend code.

The skills share a canonical UX/UI knowledge base projected into each skill's `references/` directory. They are intentionally separated so a build task does not behave like a formal audit, and a review task never edits files.

## Package Layout

```text
ux-ui-skills/
├── .codex-plugin/plugin.json
├── .claude-plugin/plugin.json
├── LICENSE
├── skills/
│   ├── ux-ui-build/
│   │   ├── SKILL.md
│   │   └── references/
│   └── ux-ui-review/
│       ├── SKILL.md
│       └── references/
├── CHANGELOG.md
├── PACKAGE-MANIFEST.md
└── RELEASE-NOTES.md
```

## ChatGPT / Codex Local Use

Use `.codex-plugin/plugin.json` as the OpenAI/Codex plugin manifest. The manifest points to `./skills/`, which contains both skill folders.

For repo or personal marketplace installation, expose this package folder through a local marketplace entry that points to the plugin root. No MCP server, app integration, hooks, credentials, or external service is required.

For OpenAI platform publication, create a new plugin from the OpenAI plugin portal and choose the skills-only option. Upload or point the submission to this package after reviewing the manifest, README, and license.

## Claude-Compatible Use

Use `.claude-plugin/plugin.json` and the same `skills/` directory for a Claude Code skills-only archive. The package contains no Claude-specific commands, hooks, MCP server, user configuration, or live artifact dependency.

For local Claude Code testing, clone this repository and load it as a local plugin directory. For public distribution, this repository can be used as the public source package; marketplace submission can be handled separately if Anthropic requests a marketplace catalog file or review form.

For a step-by-step local setup guide in Spanish, see [Claude Code Local Manual APH](docs/CLAUDE-CODE-LOCAL-APH.md).

## Usage

Use `ux-ui-build` when the task is to design, build, modify, or improve an interface, component, page, layout, navigation, form, dashboard, landing page, responsive state, or interaction.

Use `ux-ui-review` when the task is to evaluate, audit, critique, diagnose, or prioritize issues in an existing UI without modifying files.

For combined requests such as "review this and fix it," use `ux-ui-build`, because that request includes authorization to evaluate and modify. `ux-ui-review` remains read-only even when a requested fix looks obvious.

## Boundaries

These skills do not claim formal WCAG certification, legal review, security review, analytics validation, or user testing. They may flag risks and recommend validation, but they must not invent user behavior, conversion numbers, compliance conclusions, or test results.

## Provenance

Runtime reference files are generated artifacts projected from `canonical/knowledge/` in the source repository. Do not edit files under `skills/*/references/` manually; update canonical knowledge and reproject instead.
