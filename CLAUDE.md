# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a Claude Code workflows repository demonstrating automated design review systems for front-end development. The workflows leverage Playwright MCP integration and specialized agents to ensure UI/UX consistency and accessibility compliance.

## Key Workflows

### Design Review System
The primary workflow automates comprehensive design reviews through two main entry points:

1. **Design Review Agent** (`@design-reviewer` or `.claude/agents/design-reviewer.md`)
   - Automated review following 7-phase methodology
   - Playwright browser automation for live testing
   - Multi-viewport testing (1440×900 desktop, 390×844 mobile)
   - Generates graded reports (A-F) with actionable feedback

2. **Visual Review Command** (`/visual-review`)
   - Quick visual and console checks on HTML files
   - Immediate feedback for rapid iteration

### MCP Configuration
- **Playwright MCP**: Browser automation server configured in `.claude/config.json`
- Enables live UI interaction testing, screenshot capture, and console monitoring
- Auto-restart enabled for reliability

## Design Standards

Reference documents in `context/` directory:

### Design Principles (`context/design-principles.md`)
- Clarity over decoration with purposeful whitespace
- Strong typographic hierarchy (≥1.4 line-height)
- WCAG AA contrast and 44px touch targets
- Mobile-first approach with specific viewport testing
- Subtle motion design (200-300ms)

### Style Guide (`context/style-guide.md`)
- Typography: Inter/System UI fonts, semantic scale, 16-18px body
- Color palette: Primary #0F172A, Accent #2563EB, Surface #FFFFFF, Muted #475569
- Component specs: 16-24px padding, 8-12px gaps, visible focus rings

## Visual Development Protocol

Located in `.claude/claude.md`, this protocol mandates:

1. Playwright MCP usage for any front-end changes
2. Screenshot capture at both desktop and mobile viewports
3. Validation against style guide and design principles
4. Iteration until WCAG AA compliance achieved
5. Design Delta Reports with before/after documentation

## Repository Structure

- `design-review/` - Workflow templates and documentation
- `context/` - Design standards and principles
- `.claude/` - Claude Code configuration (agents, commands, MCP settings)

## Development Commands

This repository is documentation-focused with no build system. Work primarily involves:
- Editing workflow templates and configuration files
- Testing design review agents on sample HTML files
- Validating MCP integrations with Playwright browser automation

References:
- /context/design-principles.md
- /context/style-guide.md

For any front-end change:
1) Use MCP `playwright` (headed). Viewports: 1440×900 and 390×844.
2) Capture screenshots + console/network logs for impacted routes.
3) Validate against (in order): provided mock/spec → /context/style-guide.md → /context/design-principles.md.
4) Iterate until: no console errors, mobile+desktop parity, WCAG AA basics.
5) Return a Design Delta Report (before/after notes, screenshots, fixes, next actions).