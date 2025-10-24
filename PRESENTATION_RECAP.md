# AI Coding Agents & MCPs - Presentation Recap

**Presenter:** Jure Grandovec
**Date:** October 2025
**Context:** 3 months of testing Claude Code in production

---

## Key Takeaway

AI coding agents **speed up development and make multitasking easier** - but they're not full automation. They work best as supervised assistants that handle routine tasks while you stay in control.

---

## What Are AI Coding Agents?

**AI Agents vs AI Assistants:**
- **Assistants** (GitHub Copilot): Give code suggestions, you do the rest manually
- **Agents** (Claude Code): Execute complete workflows with your approval at each step

**Key Difference:**
Copilot suggests → you implement
Claude Code executes end-to-end → you approve each action

**Main Tools:**
- **Claude Code** (CLI) - Free, npm install
- **Cursor** - IDE-based alternative
- **claude.ai/code** - Browser-based, no installation

---

## Model Context Protocol (MCP)

**What is MCP?**
Think "USB-C for AI" - standard protocol for connecting AI agents to development tools

**Created:** Anthropic, November 2024
**Purpose:** Standardize how AI communicates with dev tools

**Essential MCPs:**
- **GitHub/Bitbucket** - Repo access, PRs, issues
- **Jira** - Tickets, sprints
- **Slack** - Messages, channels
- **Playwright** - Browser automation, E2E testing
- **Chrome DevTools** - Debugging, network monitoring
- **Angular CLI / Laravel** - Framework-specific code generation

**Ecosystem:** 100+ community-built MCPs available

---

## Real-World Examples Shown

### Example 1: Fixing Image Processing Queue
Production bug fix from Slack error to deployed PR

### Example 2: Monitoring Production Exceptions via Slack
Automated error tracking and resolution using Slack MCP integration

### Example 3: Solving JIRA Ticket BRIEFD-5606
Complete workflow: Ticket → Investigation → Implementation → Testing → PR → Update

### Example 4: Market Study MCP (Internal Tool)
Custom MCP for vehicle analysis from screenshots
Input: Vehicle photo → Output: Make, model, year, price

---

## MCP Workflow Examples

**Frontend Development:**
- Angular component generation
- Responsive design implementation
- Playwright E2E tests
- Chrome DevTools debugging

**Backend Development:**
- Production error monitoring (Slack)
- Laravel API development
- Automated testing
- Documentation updates

**Project Management:**
- Sprint blocker tracking
- Resource allocation reports
- Client status updates

**Sales:**
- Lead qualification
- Proposal generation
- Opportunity tracking

---

## Prompt Engineering Tips

1. **Be specific** - Vague prompts get vague results
2. **Give context** - Reference files, explain the problem
3. **Include examples** - Show what you want
4. **Start simple, iterate** - Don't try complex tasks first
5. **Always review output** - Don't blindly accept AI suggestions

---

## Getting Started

### Step 1: Install
```bash
npm install -g @anthropic/claude-code
claude-code auth
```

### Step 2: Add Project Context
Create `CLAUDE.md` in your project root:
- Build commands
- Test commands
- Architecture overview
- Coding conventions

### Step 3: Add MCPs
Start with essentials:
1. GitHub/Bitbucket
2. Jira
3. Slack

### Step 4: Create Slash Commands
Reusable prompts for common tasks:
- `/review` - Code review
- `/test` - Generate tests
- `/docs` - Update documentation

---

## What Works Well (After 3 Months)

✅ **Bug fixes** - Routine production issues
✅ **Boilerplate code** - Components, controllers, forms
✅ **Test writing** - Unit tests, E2E tests
✅ **Documentation** - README updates, code comments
✅ **Refactoring** - Structured code improvements
✅ **Multitasking** - Handle multiple tasks in parallel

---

## What Doesn't Work (Yet)

❌ **Full automation** - Still need developer oversight
❌ **Complex architecture decisions** - Requires human judgment
❌ **Critical production changes** - Too risky without review
❌ **Domain-specific logic** - Needs business context

---

## Key Principles

1. **You stay in control** - Approve each step, review all output
2. **Start with small tasks** - Build confidence gradually
3. **Good prompts matter** - Specific, contextual prompts get better results
4. **MCPs extend capabilities** - Connect AI to your existing tools
5. **Not magic, but effective** - Realistic expectations lead to better results

---

## Resources

- **Claude Code Documentation:** https://docs.claude.com/claude-code
- **MCP Registry:** https://github.com/modelcontextprotocol
- **Browser-based Alternative:** https://claude.ai/code

---

## Demo Tools Shown

1. **Claude Desktop** - Full MCP integration for deep work
2. **Market Study MCP** - Internal vehicle analysis tool
3. **claude.ai/code** - Browser-based coding for quick tasks

---

## Bottom Line

After 3 months of testing: **AI coding agents are production-ready for routine tasks with proper supervision.** They won't replace developers, but they significantly speed up development workflows and enable better multitasking when used correctly.

**Best suited for:** Teams willing to invest time in setup (CLAUDE.md, MCPs, prompts) and comfortable with approval-based workflows.

**ROI:** Noticeable time savings on repetitive tasks; allows developers to focus on architecture and complex problems.
