# Awesome Claude Skills

A curated collection of skills that teach Claude how to think and work better.

## What are Claude Skills?

Skills are packages of instructions, scripts, and resources that teach Claude how to complete specific tasks in a repeatable way. They improve consistency, speed, and quality by addressing fundamental gaps in how LLMs approach problems.

**Skills tell Claude "how to do things well"** while **MCPs provide "access to external systems"**. Use them together: MCP connects Claude to your data and tools, Skills teach it how to use them effectively.

---

## How to Install Skills

### For Claude.ai (Web/Desktop App)

**Step 1: Enable Skills**
1. Go to **Settings → Capabilities**
2. Turn on **"Code execution and file creation"**
3. Turn on **"Skills"** (under Feature Previews)

**Step 2: Install a Skill**
1. Download a skill folder from this repository
2. Zip the folder (e.g., `first-principles-thinking.zip`)
3. Go to **Settings → Capabilities → Skills**
4. Click **"Upload skill"**
5. Upload the ZIP file

**Step 3: Use It**
- Claude automatically loads relevant skills based on your task
- Or explicitly ask: *"Use the first principles thinking skill for this"*

### For Claude Code (CLI)

```bash
# Clone this repository
git clone https://github.com/surendranb/awesome-claude-skills.git

# Copy skill to Claude's skills directory
mkdir -p ~/.claude/skills
cp -r awesome-claude-skills/first-principles-thinking ~/.claude/skills/
```

Skills load automatically when relevant to your task.

### For Claude API

Skills work with the API when using the code execution tool. See [Skills API Quickstart](https://docs.anthropic.com/en/docs/build-with-claude/agent-skills).

---

## Available Skills

### 🧠 [First Principles Thinking](./first-principles-thinking/)

**What it does:**
- Makes pattern-matching conscious instead of automatic
- Requires multi-source research from authoritative sources
- Flags uncertainty explicitly instead of generating confident-sounding text
- Traces causality and admits when speculating
- Surfaces decision points instead of making choices unilaterally
- Enforces signal-to-noise ratio (every sentence must add information)

**Use it for:** Complex system design, strategic decisions, ambiguous problems, multi-dimensional challenges

---

## Contributing

Want to add a skill? Submit a PR with a new skill folder containing a `SKILL.md` file. See [first-principles-thinking](./first-principles-thinking/) for structure.

---

## License

MIT License - See [LICENSE](./LICENSE)

**Created by** [Surendran Balakrishnan](https://surendran.info)
