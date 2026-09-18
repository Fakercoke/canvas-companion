# Choose a connection that actually exists

This reference is for the Agent. Explain the selected route in ordinary language; do not overwhelm a student with all alternatives.

## 1. Existing authorized Canvas tools

Inspect available tool descriptions and schemas. Prefer read-only course and assignment tools. If a selected tool needs a course ID, retrieve it from the user's link or a course list; do not guess. Where multiple courses have similar names, ask the student to choose using names and term labels.

Run the minimal access check from SKILL.md. Reuse the connection if it works. No extra package is necessary. This is often the fastest path.

## 2. Institution-approved remote MCP or connector

Obtain the service's actual URL and setup documentation from the institution or provider. A Canvas homepage is not this URL. Check who operates the service and which data it will receive. The MCP client's login to a connector and the connector's authorization to Canvas are separate layers: one OAuth login does not establish both automatically.

Use [clients.md](clients.md) for the matching client. User completes authorization in the intended provider/school UI. Avoid sharing passwords or manually generated tokens with the project author. Verify a selected course after login.

### Why this pack does not ship a universal token form

Canvas's OAuth documentation distinguishes manual tokens for testing from multi-user applications, for which it requires OAuth. A public project asking every student to supply a manually generated token should not be assumed acceptable merely because a community repo does it. A real multi-user connector needs an appropriate Canvas developer-key/OAuth arrangement and institutional permission. This pack does not implement or provide that service.

An already configured personal integration may be useful, but determine that its use is authorized; do not present its existence as permission to redistribute access. For a developer's own testing, consult Canvas's official instructions and school rules rather than adapting that route into this pack's public onboarding.

Sources: [Canvas OAuth](https://developerdocs.instructure.com/services/canvas/oauth2/file.oauth), [API policy](https://www.instructure.com/policies/canvas-api-policy).

## 3. User-authenticated browser

Only select this route when the current host actually exposes browser control and the user authorizes visiting their Canvas. Do not assume a client has a browser because it supports MCP.

1. Open the user's confirmed school Canvas homepage.
2. If login or MFA is needed, let the user complete it in the official page; resume from visible logged-in state.
3. Open the chosen course and verify its name and term.
4. Open Assignments and the requested assignment. Read the title, current due date, allowed file type and description.
5. Inspect the visible rubric and AI rules if available; locate relevant reading links without bulk downloading the course.
6. Return a concise answer with the current source links. A browser-only connection may not persist in later sessions; say so.

Use only the host's supported browser operations. Do not extract cookies, replay hidden authenticated requests, or automate around login barriers. If reading is blocked, give the exact next user action or use permitted user-provided material.

## 4. No working route

Explain the narrow missing capability: no tools, login required, school service not offered, API access unavailable, or particular reading inaccessible. Do not imply Canvas can never be connected. Offer the fictional demo or a checklist based on permitted material. Do not install unrelated plugins or promise that a Skill can grant access.

## Success record

Provide a short user-facing record without identifiers beyond those needed for source links:

> Method: authorized connector / browser. Checked: selected course and assignment. Last checked: time and timezone. Still unavailable: rubric / library full text / nothing observed. Available next: assignment checklist, reading map or deadline check.
