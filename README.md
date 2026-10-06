# Economist Translator

A Codex skill that translates supplied *The Economist* articles into natural Simplified Chinese Mandarin and produces a readable PDF with the article's original images.

## What it does

- Translates the complete article paragraph by paragraph, preserving meaning, facts, attribution and editorial tone.
- Uses natural Chinese journalistic prose instead of literal English sentence structure.
- Includes original article illustrations and captions when present.
- Exports an A4 PDF with source information, page numbers and the footer “THE ECONOMIST · 由 ChatGPT 翻译”.
- Keeps ordinary paragraph breaks without numbered paragraph headings.

## Install

Clone this repository and copy the skill folder into your personal Codex skills directory:

```bash
git clone https://github.com/sqzhang-jeremy/economist-translator.git
mkdir -p ~/.codex/skills
cp -R economist-translator/economist-translator ~/.codex/skills/
```

If you downloaded the repository as a ZIP, extract it and copy the inner `economist-translator` folder, containing `SKILL.md`, into `~/.codex/skills/`.

The installed entrypoint should be:

```text
~/.codex/skills/economist-translator/SKILL.md
```

If you use a custom `CODEX_HOME`, install under its `skills` directory instead. Start a new Codex conversation after installation.

## Use

Attach the original article PDF or provide accessible article text, then ask:

```text
Use $economist-translator to translate this article into natural Mandarin
and export a PDF with its original images.
```

You can also request a text-only translation or bilingual output explicitly.

For articles extracted from a full magazine issue, provide all continuation pages. The skill distinguishes article illustrations from images belonging to neighbouring stories.

## Requirements

This is an instruction-based skill, not a standalone translation application. It requires a Codex environment with access to the supplied article and file-generation tools. PDF output also needs an available PDF workflow, a compatible Chinese font and a renderer for visual checks.

## Repository contents

| File | Purpose |
|---|---|
| `economist-translator/SKILL.md` | Translation workflow and PDF design instructions |
| `economist-translator/agents/openai.yaml` | Skill display metadata and example invocation |
| `economist-translator/references/approved-style.md` | Notes from approved trial translations |

The repository contains the skill instructions, not the original magazine articles or their illustrations. It does not include a standalone PDF-generation script.

## Scope

Supply articles you are permitted to use. The skill does not bypass paywalls or automatically publish translations. This is an independent project and is not affiliated with or endorsed by *The Economist*. Translations are AI-generated and should be reviewed before reuse.

