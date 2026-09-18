# Choose a connection that actually exists

This reference is for the Agent. Explain the selected route in ordinary language; do not overwhelm a student with all alternatives.

## 1. Existing authorized Canvas tools

Inspect available tool descriptions and schemas. Prefer read-only course and assignment tools. If a selected tool needs a course ID, retrieve it from the user's link or a course list; do not guess. Where multiple courses have similar names, ask the student to choose using names and term labels.

Run the minimal access check from SKILL.md. Reuse the connection for the scope it supports. If the request exceeds that scope, inspect available browser capabilities and try the verified school site using an existing authorized session. A request to read other courses authorizes that read-only fallback; do not ask the user to choose a technical route or repeat the same authorization.

Distinguish a connector scope restriction from an actual account/resource access denial. Never alter a course-specific tool to bypass its restrictions. Report an overall access limitation only after checking the available supported alternatives; describe what was tried and what remains unread. If login/MFA is required, hand that step to the user. No additional package is needed when the browser route works.

## 2. Institution-approved remote MCP or connector

Obtain the service's actual URL and setup documentation from the institution or provider. A Canvas homepage is not this URL. Check who operates the service and which data it will receive. The MCP client's login to a connector and the connector's authorization to Canvas are separate layers: one OAuth login does not establish both automatically.

Use [clients.md](clients.md) for the matching client. User completes authorization in the intended provider/school UI. Avoid sharing passwords or manually generated tokens with the project author. Verify a selected course after login.

### Why this pack does not ship a universal token form

Canvas's OAuth documentation distinguishes manual tokens for testing from multi-user applications, for which it requires OAuth. A public project asking every student to supply a manually generated token should not be assumed acceptable merely because a community repo does it. A real multi-user connector needs an appropriate Canvas developer-key/OAuth arrangement and institutional permission. This pack does not implement or provide that service.

An already configured personal integration may be useful, but determine that its use is authorized; do not present its existence as permission to redistribute access. For a developer's own testing, use the concrete [key and personal API guide](keys.md); do not turn that conditional route into a multi-user token-collection service.

Sources: [Canvas OAuth](https://developerdocs.instructure.com/services/canvas/oauth2/file.oauth), [API policy](https://www.instructure.com/policies/canvas-api-policy).

## 3. User-authenticated browser

Only select this route when the current host actually exposes browser control and the user authorizes visiting their Canvas. Do not assume a client has a browser because it supports MCP.

1. Open the user's confirmed school Canvas homepage.
2. If login or MFA is needed, let the user complete it in the official page; resume from visible logged-in state.
3. Open the chosen course and verify its name and term.
4. Open Assignments and the requested assignment. Read the title, current due date, allowed file type and description.
5. Follow the requested scope: inspect a rubric/reading for one assignment, or use the [course reading workflow](course-reading.md) for a whole course. Retrieve permitted content directly in batches.
6. Return a concise answer with the current source links. A browser-only connection may not persist in later sessions; say so.

Use only the host's supported browser operations. Do not extract cookies, replay hidden authenticated requests, or automate around login barriers. If reading is blocked, give the exact next user action or use permitted user-provided material.

## 4. No working route

Explain the narrow missing capability: no tools, login required, school service not offered, API access unavailable, or particular reading inaccessible. Do not imply Canvas can never be connected. Offer the fictional demo or a checklist based on permitted material. Do not install unrelated plugins or promise that a Skill can grant access.

## Success record

Provide a short user-facing record without identifiers beyond those needed for source links:

> Method: authorized connector / browser. Checked: selected course and assignment. Last checked: time and timezone. Still unavailable: rubric / library full text / nothing observed. Available next: assignment checklist, reading map or deadline check.
