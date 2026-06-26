# Home Assistant Config Instructions

This repository is a Home Assistant configuration project.

## Package Layout

- Prefer placing package-specific entities, scripts, and automations under `includes/packages/`.
- Keep new code close to the existing package for the related feature, room, device, or integration.
- Follow the surrounding YAML structure and indentation in the file being edited.

## Script And Automation Aliases

When adding or editing `script:` or `automation:` entries, use the alias format already used in `includes/packages/`:

```yaml
alias: "[Domain] Action Name"
```

Alias rules:

- Always start with a square-bracketed domain prefix.
- The domain prefix should describe the feature, room/device, or integration, using the existing vocabulary when possible.
- Use room plus device when that is how the nearby package is named, for example `[Bedroom Covers]`, `[Bedroom Climate]`, `[Livingroom TV]`, `[Kidsroom Lights]`.
- Use integration or feature names for integration-wide packages, for example `[Telegram]`, `[SMS]`, `[Roborock]`.
- Use a short human-readable action after the bracketed prefix.
- Prefer title case for English action names, matching examples like `System Report`, `Toggle Power`, `Open Smoothly`, `Reset Zone Selection`, and `Smart Turn On Heater`.
- Existing aliases sometimes use sentence/lowercase wording or Russian text when that matches the package context. Preserve that local style when editing nearby entries.
- Do not use generic aliases without a bracket prefix.

Good examples from this repository:

```yaml
alias: "[Telegram] System Report"
alias: "[Bedroom Covers] Set Cover Position"
alias: "[Livingroom TV] Toggle Power"
alias: "[Roborock] Start Zone Cleaning"
alias: "[Door Lock] Try to unlock"
alias: "[Car Climate] Smart Turn On Heater"
```

Before creating a new alias, inspect nearby aliases in `includes/packages/` and match their domain prefix, capitalization, wording style, and language.

## Dashboard Grouping

- If you create two or more scripts or automations with the same alias group (bracketed domain prefix), group them together on a dashboard page.
- Use a logical section or container to keep related actions visible and organized for the user.

## Change Scope

- Make small, focused changes.
- Do not reorganize packages, rename existing entities, or refactor unrelated automations unless explicitly requested.
- Prefer consistency with this repository over generic Home Assistant examples.
- Stay within this project folder at all times. Do not browse, modify, or rely on files or resources outside the current workspace/project directory unless the user explicitly asks for it.
