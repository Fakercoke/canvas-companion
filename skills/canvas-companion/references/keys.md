# Canvas keys, explained for beginners

Use this when a student asks “where is the key?” Explain the relevant route, not every technical option at once.

## Three different things

- **School Canvas address**: the official HTTPS site used for normal login. It is not a secret and not an MCP endpoint.
- **Access token / API token**: a credential allowing API actions as the account, within its permissions. It is password-equivalent and not inherently read-only.
- **Developer key / OAuth client ID and secret**: application credentials normally arranged with the school administrator for a service. Students should not be told to obtain an administrator's secret. Signing into an MCP provider and authorizing its access to Canvas can be separate steps.

## Regular student connection

Prefer an existing authorized connector or supported browser. For OAuth, guide the student to the provider's real setup page, then official school authorization, explain requested access and verify a course afterward. No manual key is needed for the browser route. If neither service nor browser exists, name the missing component; a token alone does not add tools to an agent.

## Personal developer testing: where manual tokens live

Canvas documents manual tokens for testing your own application before implementing OAuth. This is a conditional developer-testing route, not the default onboarding for all users of a public app. Check institutional permission and whether the setting exists before proceeding.

1. The user opens their official Canvas site and Account/Profile → Settings (labels vary). The profile/settings area is commonly `/profile/settings`.
2. Find **Approved Integrations** and **New Access Token** (or equivalent). If missing/disabled, stop this route; do not bypass school settings.
3. For authorized personal testing, the user supplies a recognisable purpose and short expiration if offered, then generates the token. It may only be shown once.
4. The user stores it in their own OS keychain or the verified local integration's secret input. Never paste it into AI chat, a command argument, repository, screenshot or Issue. Do not invent environment-variable names: inspect the chosen integration's documented schema. Preserve unrelated client settings.
5. If implementing a personal API test, read the secret within the local process from the approved secret store, send `Authorization: Bearer <token>` only to the confirmed Canvas HTTPS origin, and never print headers/secrets. Do not include the token in a URL or forward authorization on cross-origin redirects.
6. Test a minimal read such as `GET /api/v1/courses`, then one selected course resource. A token is not an MCP server; an API-capable tool or integration still has to execute the request.
7. Explain how to revoke the integration/token in Canvas settings. On expiry, use the integration's documented reauthorization. If exposed, revoke and replace; do not echo the exposed value.

Canvas explicitly requires multi-user applications to obtain tokens through OAuth and says asking other users to generate a token and enter it into your application violates its API policy. Do not repackage the personal testing instructions as a public token-collection service. This repository neither collects credentials nor supplies an OAuth application.

Sources, checked 2026-09-18: [Canvas OAuth and manual tokens](https://developerdocs.instructure.com/services/canvas/oauth2/file.oauth), [API policy](https://www.instructure.com/policies/api-policy).
