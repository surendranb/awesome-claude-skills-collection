# Problem-Solving Skills for Claude

> **Transform Claude into a systematic problem-solving partner** with persistent visual memory across conversations.

A collection of 4 composable skills that work together to guide Claude through rigorous, curiosity-driven problem-solving — with an MCP server that creates interactive visual maps of your investigation.

![Problem-Solving Graph Example](docs/graph-example.png)
*Visual graph tracking facts, hypotheses, divergences, and their relationships*

---

## 🎯 What This Does

When you ask Claude a complex question, it typically:
- Gives you one answer path (the first pattern match)
- Forgets context between conversations
- Doesn't show its reasoning process
- Makes implicit assumptions without flagging them

**With these skills + MCP**, Claude instead:
- ✅ **Explores multiple paths** before converging on an answer
- ✅ **Remembers everything** across sessions in a visual graph
- ✅ **Shows its work** - facts vs conjectures vs hypotheses
- ✅ **Questions its own assumptions** using statistical rigor
- ✅ **Traces causal chains** to Nth-order effects
- ✅ **Creates an interactive map** you can explore in your browser

---

## 🧩 The Skills

These four skills compose together like building blocks:

### 1. **Scientific Problem-Solving** 
*The foundation - curiosity-driven methodology*

- Strategic context: Understand the *why* before the *how*
- Diagnostic dialogue: Establish facts through evidence
- Root cause analysis: Trace problems to their source
- Hypothesis generation: Distinguish facts from conjectures
- Validation framework: Design experiments to test claims

**Use for:** Complex business problems, technical investigations, strategic decisions

---

### 2. **Statistical Rigor**
*The reality-check - counters cognitive biases*

- Sample size checks (are you generalizing from n=1?)
- Selection bias detection (self-selected samples)
- Correlation vs causation flags
- Survivorship bias warnings
- Regression to mean considerations

**Use for:** Data analysis, A/B test interpretation, user research, metrics-driven decisions

---

### 3. **First Principles Thinking**
*The depth-layer - breaks through assumptions*

- Multi-source research from authoritative origins
- Explicit uncertainty flagging
- Causal chain tracing
- Pattern-matching awareness
- Signal-to-noise enforcement

**Use for:** System design, strategic planning, novel problems without established solutions

---

### 4. **Problem-Solving Graph** 
*The memory system - persistent visual tracking*

- Creates a graph of your investigation
- Nodes: Facts, Hypotheses, Divergences, Statistical Checks, etc.
- Edges: Relationships like "supports," "tests," "emerged from"
- Persists across conversations
- Generates interactive HTML visualization

**Use for:** Multi-session investigations, complex problems with many moving parts, team collaboration

---

## 🚀 Quick Start

### Prerequisites

1. **Claude Desktop** (or Claude.ai with Skills enabled)
2. **Python 3.8+** (for the MCP server)

### Installation

**Step 1: Install the Skills**

```bash
# Clone this repository
git clone https://github.com/yourusername/problem-solving-skills.git
cd problem-solving-skills

# In Claude Desktop: Settings → Skills → Upload Skill
# Upload each skill folder as a ZIP:
# - first-principles-thinking.zip
# - scientific-problem-solving.zip  
# - statistical-rigor.zip
# - problem-solving-graph.zip
```

**Step 2: Install the MCP Server**

```bash
# Install FastMCP
pip install fastmcp

# Copy the MCP server
mkdir -p ~/mcps
cp -r problem-solving-graph-mcp ~/mcps/
```

**Step 3: Configure Claude Desktop**

Add to `~/Library/Application Support/Claude/claude_desktop_config.json`:

```json
{
  "mcpServers": {
    "problem-solving-graph": {
      "command": "python",
      "args": [
        "/Users/yourusername/mcps/problem-solving-graph-mcp/problem_solving_graph_server.py"
      ]
    }
  }
}
```

**Step 4: Restart Claude Desktop**

Quit and reopen Claude Desktop. The skills and MCP are now active!

---

## 📖 Usage Examples

### Example 1: Business Problem

```
User: "Our landing page conversion rate dropped from 4.2% to 2.8% last month. 
       What should we do?"

Claude: [Recognizes complex problem, initializes graph session]
        Let me set up a problem-solving session for this.
        
        [Calls: init_session("conversion-drop-nov-2025", 
                            "Recover landing page conversion rate")]
        
        Before we jump to solutions, help me understand the strategic context.
        What's the business impact of this drop? How does conversion rate 
        tie into your broader goals?
        
        [Proceeds with diagnostic dialogue, capturing facts as nodes...]
```

Claude will:
- Ask clarifying questions to establish facts
- Track each fact, hypothesis, and statistical check in the graph
- Surface hidden assumptions ("Are you comparing the same traffic sources?")
- Propose validation methods with cost/time tradeoffs
- Create an HTML visualization you can explore

### Example 2: Technical Investigation

```
User: "Why is our API response time suddenly slower?"

Claude: [Begins scientific-problem-solving methodology]
        [Captures baseline metrics as Facts]
        [Flags potential selection bias in monitoring]
        [Explores multiple divergent hypotheses]
        [Traces Nth-order effects of proposed solutions]
        
        At end: "Here's your investigation graph: file:///.../view.html"
```

### Example 3: Strategic Planning

```
User: "Should we build feature X or Y next quarter?"

Claude: [Applies first-principles thinking]
        [Researches market data from multiple sources]
        [Makes uncertainty explicit]
        [Traces causal chains for each option]
        [Documents the exploration in a persistent graph]
```

---

## 🎨 How the Skills Compose

The skills work independently but are **designed to compose**:

```
┌─────────────────────────────────────────────────────┐
│  First Principles Thinking                          │
│  "Break through surface assumptions"                │
└─────────────────────────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│  Scientific Problem-Solving                         │
│  "Follow curiosity-driven methodology"              │
└─────────────────────────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│  Statistical Rigor                                  │
│  "Question assumptions with data reality-checks"    │
└─────────────────────────────────────────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────┐
│  Problem-Solving Graph (MCP)                        │
│  "Persist everything in a visual, explorable graph" │
└─────────────────────────────────────────────────────┘
```

You can use any skill alone, or let them work together for maximum effect.

---

## 📊 The Graph Visualization

When Claude tracks a problem-solving session, it creates an interactive graph:

**Node Types:**
- 🔵 **Strategic Outcome** - The ultimate goal
- 🟢 **Fact** - Established, verified information
- 🟡 **Conjecture** - Testable claim (experiment design exists)
- 🔴 **Hypothesis** - Higher-level claim (requires action to validate)
- 🟣 **Insight Thread** - Divergence or rabbit hole exploration
- 🔷 **Validation Method** - How to test a claim (with cost/time)
- 🟣 **Statistical Check** - Bias identification, rigor validation
- 🟠 **Open Question** - Unresolved uncertainty
- 🔷 **Nth Order Effect** - Causal chain or downstream impact

**Edge Types:**
- "supports" - Evidence backs a claim
- "tests" - Validation method checks hypothesis
- "emerged from" - Divergence arose from exploration
- "challenges" - Node questions another node
- "traces causal chain from" - Downstream effect
- And more...

The graph shows:
- ✅ Non-linear exploration (divergences, rabbit holes)
- ✅ What's proven vs what's speculated
- ✅ Statistical reality-checks on claims
- ✅ How pieces connect together

**Sessions persist across conversations**, so you can pick up where you left off.

---

## 🛠️ Advanced Usage

### Resume a Session

```
User: "Let's continue that conversion optimization work from yesterday"

Claude: [Calls: get_graph("conversion-drop-nov-2025")]
        We left off exploring three hypotheses: value prop clarity, 
        page load speed, and traffic source quality. We had established 
        [X facts] and identified [Y validation methods].
        
        Where should we continue?
```

### View All Sessions

```
User: "What problem-solving sessions do I have?"

Claude: [Calls: list_sessions()]
        You have 3 active sessions:
        - conversion-drop-nov-2025 (created Nov 9)
        - api-performance-investigation (created Nov 7)
        - feature-prioritization-q1 (created Nov 1)
```

### Export and Share

The HTML visualizations are self-contained files you can:
- Open in any browser
- Share with teammates
- Archive for documentation
- Embed in Notion/Confluence

---

## 🧪 Real-World Applications

### Marketing & Growth
- Conversion rate investigations
- A/B test analysis
- User research synthesis
- Channel attribution problems

### Product & Engineering  
- Feature prioritization
- Technical root cause analysis
- Architecture decisions
- Performance debugging

### Strategy & Operations
- Market entry decisions
- Competitive analysis
- Process optimization
- Risk assessment

---

## 🤝 Contributing

Contributions are welcome! To add a skill:

1. Fork this repository
2. Create a new skill folder with `SKILL.md`
3. Follow the structure in existing skills
4. Submit a PR with examples

---

## 📚 Learn More

- **Blog:** [surendran.info](https://surendran.info) - Deep dives on problem-solving with AI
- **Claude Skills Docs:** [Anthropic's Skills Documentation](https://docs.anthropic.com/en/docs/build-with-claude/agent-skills)
- **MCP Protocol:** [Model Context Protocol Spec](https://modelcontextprotocol.io)

---

## 📄 License

MIT License - See [LICENSE](./LICENSE)

**Created by** [Surendran Balakrishnan](https://surendran.info)

---

## ⭐ Star This Repo

If these skills helped you solve a complex problem, give this repo a star! It helps others discover systematic problem-solving with Claude.
