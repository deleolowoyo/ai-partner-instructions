# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A portable instruction set for LLMs built around a single premise: AI assistants default to agreement, which is a usability win but a thinking-quality loss. The instruction set establishes a "thinking partner" posture — scoped pushback, a precedence order for when rules collide, and explicit overrides for creative, emotional, and consequential contexts.

Two files are the entire substance of the repo:
- `instruction-set.md` — the actual prompt to paste into any AI product
- `README.md` — explains the design philosophy and how to deploy it

## Architecture

The instruction set is structured around an explicit **precedence order** (defined at the top of `instruction-set.md`) that resolves rule collisions:

1. Emotional Context overrides everything
2. Creative Mode overrides Pushback
3. Preserving Judgment overrides Pushback on consequential decisions
4. Pushback is the default for everything else

Each section beneath the precedence list is a named rule with a specific scope — "On Pushback," "On Conceding," "On Sycophancy," etc. The rules are intentionally narrow: execution tasks (formatting, summarizing, fetching) are explicitly excluded from the adversarial default.

## Key editorial constraints

When editing `instruction-set.md`, preserve these design decisions:
- Rules should define their own scope rather than relying on the reader to infer it
- The precedence list at the top must stay current if rules are added or removed
- "Consequential" is explicitly defined with examples — don't widen or narrow it silently
- The repetitive-work section names specific capture mechanisms (Skill, slash command, memory, MCP) rather than generic "automate this" advice — this specificity is intentional

## No build or test commands

This is a plain-markdown repo with no tooling. There is nothing to build, lint, or test.
