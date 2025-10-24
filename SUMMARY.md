# AI Coding Agents & MCPs - What I Learned in 3 Months

I've been testing AI coding agents for 3 months, and here's what actually works.

## What Are AI Coding Agents?

Think of the difference between asking someone for advice vs hiring an assistant to do the work.

**GitHub Copilot** suggests code while you type - helpful, but you still do all the work manually.

**AI Agents** (like Claude Code) actually do the work - they read tickets, write code, run tests, create PRs, and update Jira. You just approve each step.

The key: **you stay in control**. It proposes, you approve. Not automation - supervised assistance.

## What Are MCPs?

MCP = Model Context Protocol. Think of it like USB-C for AI.

Just like USB-C lets any device connect to any charger, MCPs let AI agents connect to your tools: GitHub, Jira, Slack, etc.

Before MCPs, you'd copy-paste between AI and your tools. Now they just talk directly.

**The important ones:**
- **GitHub/Bitbucket** - AI can read code, create PRs, manage issues
- **Jira** - AI can read tickets, update status, add comments
- **Slack** - AI can monitor channels, post updates
- **Playwright** - AI can test your website automatically

100+ MCPs available and growing.

## Real Examples from Our Work

**Bug fix workflow:** Production error in Slack → AI investigates → fixes the bug → runs tests → creates PR → posts update to team. I just approved each step.

**JIRA ticket:** "Fix BRIEFD-5606" → AI reads the ticket → understands the problem → implements solution → writes tests → submits for review.

**Market Study tool:** Upload a vehicle photo → AI extracts make, model, year, price → compares market prices. Saves hours of manual data entry.

## What Actually Works

After 3 months, here's what I use it for daily:

✅ **Bug fixes** - Especially routine production issues
✅ **Boilerplate code** - Forms, components, controllers
✅ **Writing tests** - Unit tests, E2E tests
✅ **Documentation** - READMEs, comments
✅ **Multitasking** - Handling 3-4 tasks in parallel while I focus on architecture

## What Doesn't Work Yet

❌ **Full automation** - You can't just "set and forget"
❌ **Complex decisions** - Architecture, design patterns need human judgment
❌ **Critical production changes** - Always needs review

## The Bottom Line

It's not magic. It won't replace developers. **But it does speed things up.**

The routine stuff that takes 30 minutes? AI does it in 5 minutes with your supervision.

That gives you more time for the interesting problems: architecture, complex features, mentoring the team.

**Worth the setup time?** Yes, if you're comfortable reviewing code and staying involved. The time savings on repetitive tasks add up fast.

## How to Get Started

1. **Install Claude Code** (free): `npm install -g @anthropic/claude-code`
2. **Add a CLAUDE.md file** to your project explaining your setup
3. **Connect a few MCPs** - start with GitHub and Jira
4. **Try a small task** - "Write tests for this component"
5. **Review everything** - Don't blindly accept

Start small. Build trust. Scale up as you get comfortable.

---

**Questions?** Happy to show you examples or help with setup.

**Resources:**
- Docs: https://docs.claude.com/claude-code
- MCPs: https://github.com/modelcontextprotocol
- Try in browser: https://claude.ai/code
