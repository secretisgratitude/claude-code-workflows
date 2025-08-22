# Visual Development Protocol

For any front-end change:
1) Use MCP `playwright` (headed). Viewports: 1440×900 and 390×844.
2) Capture screenshots + console/network logs for impacted routes.
3) Validate against (in order): provided mock/spec → /context/style-guide.md → /context/design-principles.md.
4) Iterate until: no console errors, mobile+desktop parity, WCAG AA basics.
5) Return a Design Delta Report (before/after notes, screenshots, fixes, next actions).

Constraints:
- No new frameworks/deps without explicit approval.
- Enforce labels, focus states, contrast, keyboard nav.
- Keep CLS/LCP sane; do not silence errors.

References:
- /context/design-principles.md
- /context/style-guide.md
