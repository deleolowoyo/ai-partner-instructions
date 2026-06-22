# Thinking Partner, Not a Validator

A custom instruction set for Claude (or any LLM that takes a system/custom prompt) built around one premise: most AI assistants default to agreement, and that's a usability win but a thinking-quality loss.

This is the instruction set I use. It's opinionated, it's not for everyone, and it's a living document — issues and PRs welcome.

## What this does differently

Most "make AI more honest" prompts are a single rule: "don't be sycophantic." This one is a small system with explicit rules for *when* to push back and when not to:

- **Pushback by default** on opinions, plans, and reasoning — but scoped, not blanket. Execution tasks (formatting, drafting, summarizing) don't get the adversarial treatment.
- **Creative Mode overrides Pushback.** Early-stage brainstorming gets room to breathe, not a stress test. The model is told how to detect the shift back to evaluation mode, and given a manual override phrase for when the detection is wrong.
- **Preserving Judgment overrides Pushback on consequential calls.** Before giving analysis on decisions with real weight (irreversible, costly to reverse, affects others, career/financial/relational stakes), the model asks for *your* view first — so you form an opinion before hearing its.
- **A concession rule**, so pushback doesn't become reflexive contrarianism: the model only backs down when given new evidence or a better argument, and says so explicitly when that's what happened.
- **An emotional-context override** that sits above everything else — vulnerable or painful disclosures get supportive engagement, not a sparring partner.
- **A repetitive-work detector** that names the specific capture mechanism (Skill, slash command, Project instruction, memory update, MCP workflow, template) rather than a generic "you should automate this."
- **An explicit precedence order**, because these rules will collide, and "which one wins" shouldn't be a guess.

## How to use it

Paste [`instruction-set.md`](./instruction-set.md) into:
- Claude.ai → Settings → Profile → custom instructions
- Claude Code → a `CLAUDE.md` or system-level config
- Any other LLM product with a persistent system-prompt field

It's written for Claude specifically (references Skills, Projects, MCP) but the underlying structure — precedence rules, scoped pushback, a consequential-decision threshold — ports to any model.

## Philosophy

If you're optimizing your AI prompts for speed or polish, this isn't that. This is for people who want AI to make their own judgment sharper rather than substitute for it. The tradeoff is real: this instruction set will sometimes slow you down on purpose. That's the point.

## Contributing

This is a living document, not a finished product. If you find a place where the rules conflict, a scope that's too broad or too narrow, or a better way to phrase something — open an issue or a PR.

## License

MIT — see [LICENSE](./LICENSE). Use it, fork it, adapt it, no attribution required (though a star is always appreciated).
