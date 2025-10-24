# AI Coding Agents & MCPs - Quick Recap

**Presented by:** Jure Grandovec | **Testing Period:** 3 months

## Summary

AI coding agents (Claude Code, Cursor) **speed up development** by executing complete workflows with your approval. After 3 months of testing: they're production-ready for routine tasks but **not full automation** - you stay in control.

## Key Concepts

**AI Agents vs Assistants:**
- Copilot = suggestions only
- Claude Code = complete workflows (with your approval at each step)

**MCP (Model Context Protocol):**
"USB-C for AI" - standard way to connect AI agents to dev tools (GitHub, Jira, Slack, etc.)
- Created by Anthropic, Nov 2024
- 100+ MCPs available

## What Works Well

✅ Bug fixes, boilerplate code, tests, documentation, refactoring
✅ Multitasking - handle multiple tasks in parallel
✅ Routine production issues

## What Doesn't Work Yet

❌ Full automation, complex architecture, critical production changes without review

## Real Examples Shown

1. **Fixing image processing queue** - Production bug to deployed PR
2. **Monitoring Slack for errors** - Automated error tracking with MCP
3. **JIRA ticket BRIEFD-5606** - Complete workflow from ticket to PR
4. **Market Study MCP** - Internal tool: vehicle photo → extracted details

## Getting Started

```bash
# 1. Install
npm install -g @anthropic/claude-code

# 2. Create CLAUDE.md with project context

# 3. Add MCPs: GitHub, Jira, Slack

# 4. Start with small tasks
```

## Essential MCPs

- **GitHub/Bitbucket** - Code & PRs
- **Jira** - Tickets & sprints
- **Slack** - Team communication
- **Playwright** - E2E testing
- **Angular CLI / Laravel** - Framework code generation

## Prompt Engineering Tips

1. Be specific
2. Give context (reference files)
3. Include examples
4. Start simple, iterate
5. Always review output

## Bottom Line

**Not magic, but effective.** Best for teams comfortable with approval-based workflows. Noticeable time savings on repetitive tasks. Allows developers to focus on architecture and complex problems.

**Resources:**
- Docs: https://docs.claude.com/claude-code
- MCPs: https://github.com/modelcontextprotocol
- Browser version: https://claude.ai/code
