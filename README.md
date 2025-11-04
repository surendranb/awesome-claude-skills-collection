# Awesome Claude Skills

A curated collection of skills that teach Claude how to think and work better. These skills address fundamental gaps in how LLMs approach problems and help Claude leverage its computational advantages.

## What are Claude Skills?

**Skills are packages of instructions, scripts, and resources that teach Claude how to complete specific tasks in a repeatable way.** They improve consistency, speed, and quality by providing procedural knowledge—clear instructions for how to complete workflows.

**Think of it this way:**
- **Skills** teach Claude *how to do things well*
- **MCPs** provide *access to external systems*

Skills tell Claude how to think and work. MCPs give Claude the data and tools to work with. Together, they're powerful—MCP connects Claude to your systems, Skills teach it how to use them effectively.

---

## Why Skills Matter

Claude has fundamental gaps compared to human thinking:

**Pattern completion over novel reasoning**  
→ Falls into familiar patterns ("this looks like problem X, so apply solution Y") rather than examining what's actually in front of it

**No world model**  
→ Works from text patterns, not embodied experience. When you think about "how teams coordinate," you're drawing on real experiences. Claude is drawing on text about experiences.

**No genuine uncertainty**  
→ Simulates reasoning but generates text that looks like thinking. No moment of being truly stuck and breaking through.

**Weak counterfactual reasoning**  
→ Can say "what if we used approach X?" but lacks the deep causal models that let humans intuitively grasp second-order effects

**No stakes**  
→ Has no consequences for being wrong, which fundamentally changes how thinking happens

**Verbosity as false rigor**  
→ Equates thoroughness with length. Sharp thinking is often terse.

**Skills compensate for these gaps** by making weaknesses explicit and providing structured approaches to overcome them.

---

## Available Skills

### 🧠 [First Principles Thinking](./first-principles-thinking/)

Addresses Claude's tendency to jump to solutions and give "top 5" lists. Teaches comprehensive analysis from fundamental truths.

**Gaps it addresses:**
- Pattern-matching over genuine analysis
- Arbitrary limits on exploration ("top 5" syndrome)
- Surface-level reasoning without validation
- Making strategic choices instead of surfacing tradeoffs
- Verbosity without substance

**What it does:**
- Makes pattern-matching conscious ("What pattern am I matching to? Is this valid or am I being lazy?")
- Requires multi-source research (authoritative sources, community feedback, real implementations)
- Flags uncertainty explicitly instead of generating confident-sounding text
- Traces causality and admits when speculating
- Surfaces decision points instead of making choices unilaterally
- Enforces signal-to-noise ratio (every sentence must add information)

**Use it for:** Complex system design, strategic decisions, ambiguous problems, multi-dimensional challenges

---

## Quick Start

### Prerequisites

Skills require **Code execution** to be enabled. Available on Claude Pro, Max, Team, and Enterprise plans.

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
- Or explicitly reference it: *"Use the first principles thinking skill for this problem"*

### For Claude Code (CLI)

**Step 1: Install to Skills Directory**
```bash
# Clone this repository
git clone https://github.com/surendranb/awesome-claude-skills.git

# Copy skill to Claude's skills directory
mkdir -p ~/.claude/skills
cp -r awesome-claude-skills/first-principles-thinking ~/.claude/skills/
```

**Step 2: Use It**
- Claude Code automatically loads skills from `~/.claude/skills`
- Skills invoke automatically when relevant to your task
- Or explicitly reference them in prompts

### For Claude API

Skills work with the API when using the code execution tool. See [Skills API Quickstart](https://docs.anthropic.com/en/docs/build-with-claude/agent-skills) for implementation details.

---

## Skill Structure

Each skill is a folder containing a `SKILL.md` file:

```
skill-name/
├── SKILL.md          # Main skill file with YAML frontmatter
├── README.md         # (Optional) Documentation
└── scripts/          # (Optional) Helper scripts or resources
```

### SKILL.md Format

```markdown
---
name: skill-name
description: Clear description of what this skill does and when to use it
version: 1.0.0
author: Your Name
created: 2025-11-04
tags:
  - thinking
  - analysis
trigger_patterns:
  - "phrase that should trigger this skill"
  - "another trigger phrase"
---

# Skill Name

## Overview
What this skill does and why it matters.

## Instructions
Detailed, actionable instructions for Claude to follow.

## Examples
Concrete examples of the skill in action.

## Anti-Patterns
What Claude should avoid when using this skill.
```

**Key principle:** The YAML frontmatter (name, description, trigger_patterns) is how Claude decides when to load your skill. Make the description specific.

---

## Creating Your Own Skills

**1. Identify a Real Gap**
- Where does Claude consistently fail?
- What does it do that frustrates you?
- What human capability is it missing?

**2. Make It Explicit and Actionable**
- Don't say "think carefully" — specify *how* to think carefully
- Turn weaknesses into questions Claude must ask itself
- Define concrete steps, not philosophy

**3. Test on Real Problems**
- Use it for actual work
- Iterate based on what works/doesn't work
- Refine until outputs consistently improve

**4. Share It**
- Submit a PR to this repository
- Include: what gap it addresses, example usage, why it matters

### Tips for Effective Skills

✅ **Specific over vague**  
"Ask: what pattern am I matching to?" is better than "think deeply"

✅ **Address actual weaknesses**  
Focus on where Claude fails in practice, not theoretical improvements

✅ **Make it executable**  
Provide steps and frameworks, not just concepts

✅ **Keep it focused**  
One skill = one coherent capability. Don't try to do everything.

✅ **Test in the real world**  
Does it actually improve outputs on your work?

❌ **Avoid generic advice**  
"Be thorough" doesn't help. "Explore all N dimensions, not just top 5" does.

---

## Contributing

**Want to add a skill?**

1. Fork this repository
2. Create a new folder: `your-skill-name/`
3. Add a `SKILL.md` file with proper YAML frontmatter
4. Test your skill on real use cases
5. Submit a PR with:
   - What gap your skill addresses
   - Example of before/after behavior
   - When to use it

**Contribution guidelines:**
- Skills must address a real, observable gap in Claude's capabilities
- Include clear examples and anti-patterns
- Test before submitting
- One skill per PR

---

## Resources

**Official Documentation**
- [Agent Skills Documentation](https://docs.anthropic.com/en/docs/build-with-claude/agent-skills)
- [Skills Engineering Blog](https://www.anthropic.com/engineering/equipping-agents-for-the-real-world-with-agent-skills)
- [Official Anthropic Skills Repository](https://github.com/anthropics/skills)

**Related**
- [Model Context Protocol (MCP)](https://modelcontextprotocol.io/) - For connecting Claude to external systems
- [Claude API Documentation](https://docs.anthropic.com/)

---

## About

Created by [Surendran Balakrishnan](https://surendran.info)  
Blog: [surendran.info](https://surendran.info)  
GitHub: [@surendranb](https://github.com/surendranb)

**More from the author:**
- Building AI agents with communication protocols (MCP, A2A, ACP)
- Workflow automation with n8n and Agno
- Technical writing on AI systems and patterns

---

## License

MIT License - See [LICENSE](./LICENSE) file for details.

---

**Note:** Skills are available as a feature preview for Pro, Max, Team, and Enterprise plans. Code execution must be enabled to use Skills.
