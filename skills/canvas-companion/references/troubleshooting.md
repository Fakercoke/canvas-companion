# Troubleshooting without collecting secrets

| Symptom | Check | Useful next step |
|---|---|---|
| Agent says connected but no course can be read | Was only configuration saved? Does a real tool call work? | Perform the minimal read check; report the failed stage |
| No Canvas tools | Current client capabilities and whether a server is registered | Use approved connector setup, supported browser route, or demo |
| Browser login loop / MFA | Visible school authentication state | Let user complete official login; do not extract cookies |
| 401 / unauthenticated | Expired or absent authorization, correct service | Re-authenticate in official UI; do not ask for a token in chat |
| 403 / forbidden | User role, course enrolment and granted scope | Explain denied resource; ask school/provider if access is expected |
| Canvas URL produces MCP errors | Was an ordinary homepage used as server URL? | Obtain an actual approved MCP endpoint; do not guess `/mcp` paths |
| No token creation button | School may restrict API access | Ask institutional IT about approved access; do not bypass controls |
| Some tasks missing | Pagination, date range, course scope, graded discussions | Recheck scope and omitted pages; don't declare no assignments |
| Two due dates | Effective user deadline vs prose/notice vs lock date | Show sources and contradiction; distinguish lock from due |
| PDF/library source unavailable | Metadata link vs authorized full text | Mark access state, ask for permitted access, continue other work |
| File visible but assignment unsubmitted | Current attempt says in progress/draft | Report upload only; stop before a separate submit task |
| Remote app can't find local executable | Client runs in a cloud environment | Use a supported remote service or a local client |

Ask for client name/version, OS, the stage that failed and a redacted error category. A complete config dump or raw log is usually unnecessary. If a secret was exposed, explain how the user can revoke it at the issuing service; never reproduce the value in a reply or public issue.

Do not repeatedly retry a permission failure as though it were a temporary network error. Apply the stopping condition in SKILL.md.
