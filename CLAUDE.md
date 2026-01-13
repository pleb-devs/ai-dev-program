# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is the PlebDevs AI Development Program monorepo - a documentation-only repository containing three git submodules with resources for building freedom-focused, privacy-first, and Bitcoin-related applications using AI-assisted development.

## Structure

The repository contains three submodules (no build steps - Markdown only):

- **ai-guides/** - Guides for AI coding agents/clients (Goose, OpenCode, Ollama, Maple, SearXNG)
- **freedom-tech/** - Curated catalog of sovereignty-focused libraries and tools
- **new-project-boilerplate/** - Documentation-first methodology for starting LLM-driven projects

## Working with Submodules

```bash
# Update all submodules to latest
git submodule update --remote --merge

# Clone with submodules
git clone --recurse-submodules <repo-url>
```

## Submodule-Specific Guidelines

### ai-guides/
- Guide structure: Overview → Setup → Beginner usage → Pro usage → Cost savings → Privacy → Security
- Filenames: kebab-case, nested by vendor/tool (e.g., `goose/goose-cli.md`)
- Update the README index when adding guides
- Lint check: `npx markdownlint-cli <file>`

### freedom-tech/
- Entry format: `**Name** – short note *(Language • Type • Topic • use cases)* — [Name](url)`
- Favor audited, open-source, self-hostable tools
- Lint: `npx markdownlint-cli README.md AGENTS.md agent-prompt.md`
- Link check: `npx markdown-link-check README.md`
- The `agent-prompt.md` file is a token-efficient version for prompting agents

### new-project-boilerplate/
- Follow the workflow in `llm/project/setup.md`
- Structure: `llm/project/` (definitions), `llm/context/` (specs), `llm/implementation/` (notes), `llm/workflows/` (runbooks)
- Copy templates ending in `-example` and rename for use

## Code Style (from AGENTS.md)

- Prefer functional/declarative patterns over classes
- Use descriptive variables with auxiliary verbs (isLoading, hasError)
- Avoid enums; use maps
- Keep files under 500 lines
- Throw errors instead of silent fallbacks
- Write concise, technical code

## Commit Messages

- Concise, imperative mood (e.g., `add goose cli flow`)
- Keep ≤ 72 characters
- Prefix `docs:` optional but not required
