# coding-agents-skills

A collection of custom skills for AI coding agents (OpenCode and Claude Code).

## Skills

| Skill | Description |
|-------|-------------|
| [backend-developer](opencode/skills/backend-developer/) | Think and act like a professional backend developer - design APIs, work with databases, implement business logic |
| [git-commit-review](opencode/skills/git-commit-review/) | Review staged changes, create conventional commit messages, and push to remote |
| [readme-generator](opencode/skills/readme-generator/) | Analyze codebase and generate/update README.md with project information |

---

## Installing Skills

### Claude Code

#### Global (All Projects)

Skills stored in `~/.claude/skills/` are available in every project.

```bash
mkdir -p ~/.claude/skills
git clone <this-repo> ~/.claude/skills/coding-agents-skills
```

Or copy individual skills:
```bash
mkdir -p ~/.claude/skills/<skill-name>
cp -r <skill-path>/* ~/.claude/skills/<skill-name>/
```

#### Per-Project

Skills in `.claude/skills/` at your project root are only available in that project.

```bash
mkdir -p .claude/skills
cp -r <skill-path> .claude/skills/
```

#### Usage

- Invoke directly: `/skill-name`
- Claude auto-detects when to use skills based on description

---

### OpenCode

#### Global (All Projects)

Skills stored in `~/.config/opencode/skills/` are available in every project.

```bash
mkdir -p ~/.config/opencode/skills
git clone <this-repo> ~/.config/opencode/skills/coding-agents-skills
```

Or copy individual skills:
```bash
mkdir -p ~/.config/opencode/skills/<skill-name>
cp -r <skill-path>/* ~/.config/opencode/skills/<skill-name>/
```

#### Per-Project

Skills in `opencode/skills/` at your project root are only available in that project.

```bash
mkdir -p opencode/skills
cp -r <skill-path> opencode/skills/
```

#### Usage

Load a skill in your conversation:
```
skill({ name: "<skill-name>" })
```

---

## Creating New Skills

### Claude Code Skill Structure

```
my-skill/
├── SKILL.md          # Required - main skill file
├── scripts/          # Optional - executable code
├── references/       # Optional - documentation
└── resources/        # Optional - assets
```

**SKILL.md format:**
```yaml
---
name: my-skill
description: What this skill does
---

# Instructions
Your skill instructions here...
```

### OpenCode Skill Structure

```
my-skill/
└── SKILL.md          # Required - main skill file
```

**SKILL.md format:**
```yaml
---
name: my-skill
description: What this skill does
license: MIT
compatibility: opencode
metadata:
  audience: developers
  workflow: git
---

# Instructions
Your skill instructions here...
```

---

## Directory Structure

```
.
├── claude/           # Claude Code skills (currently empty - use global/per-project paths)
├── opencode/         # OpenCode skills
│   └── skills/
│       ├── backend-developer/
│       │   └── SKILL.md
│       ├── git-commit-review/
│       │   └── SKILL.md
│       └── readme-generator/
│           └── SKILL.md
└── README.md
```
