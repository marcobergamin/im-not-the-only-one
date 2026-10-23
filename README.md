# I'm Not the Only One

> "You may say I'm a dreamer, but I'm not the only one." — John Lennon, *Imagine*

An agent skill that enforces a **Search → Think → Do** workflow before starting a new project, choosing an architecture/library, or debugging an unexpected error.

Instead of relying on stale training data or blind trial-and-error, it makes the agent:

1. **Search** the current state of the art and upstream issue trackers/forums.
2. **Think** through the options and root cause before acting.
3. **Do** the implementation with evidence and citations.

## When it triggers

- Starting a project or selecting libraries, frameworks, models, protocols.
- Implementing a complex feature where the ecosystem may have moved on.
- Hitting an unexpected build/runtime/hardware error that is not an obvious local typo.

## Installation

Clone the repo into the Agent Skills directory:

```bash
git clone https://github.com/marcobergamin/im-not-the-only-one.git \
  ~/.agents/skills/im-not-the-only-one
```

OpenCode reads `~/.agents/skills` directly. To expose it to other harnesses:

```bash
mkdir -p ~/.config/opencode/skills ~/.gemini/config/skills ~/.gemini/antigravity-cli/skills
ln -sfn ~/.agents/skills/im-not-the-only-one ~/.config/opencode/skills/im-not-the-only-one
ln -sfn ~/.agents/skills/im-not-the-only-one ~/.gemini/config/skills/im-not-the-only-one
ln -sfn ~/.agents/skills/im-not-the-only-one ~/.gemini/antigravity-cli/skills/im-not-the-only-one
```

## Files

- `SKILL.md` — the skill manifest and workflow instructions.
