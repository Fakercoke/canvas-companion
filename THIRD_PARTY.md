# Sources and attribution

Canvas Companion is an original onboarding/workflow package produced with AI assistance. It does not include a Canvas MCP server, vendor SDK, upstream executable or copied course content. No association with the providers below is implied.

## Community implementation studied

- [vishalsachdev/canvas-mcp](https://github.com/vishalsachdev/canvas-mcp), by Vishal Sachdev and contributors, MIT licensed.
- Source snapshot inspected: `f098b2c472bf68d6c5cf6b21daeaaf4ca0556f04` (package metadata 1.12.0).
- Reviewed areas: setup documentation, dependency manifest, shared/student tool registration, request handling, confirmation guard and weekly-plan skill.
- No upstream source or executable is redistributed in this package. Links are references, not a security endorsement or a blanket recommendation of every deployment route. In particular, community manual-token instructions should not be treated as overriding Canvas's API policy.

## Official documentation consulted

Checked 2026-09-18; links can change. Configuration examples are limited references and still require a real provider and authorization.

- [Canvas OAuth and manual-token distinction](https://developerdocs.instructure.com/services/canvas/oauth2/file.oauth)
- [Canvas API policy](https://www.instructure.com/policies/canvas-api-policy)
- [Codex MCP configuration](https://developers.openai.com/codex/mcp/)
- [Codex skills](https://developers.openai.com/codex/skills/)
- [Cursor MCP](https://cursor.com/docs/mcp)
- [Claude Code MCP](https://code.claude.com/docs/en/mcp)

MCP tool names and client capabilities are not universal. The skill instructs the consuming Agent to inspect its actual tools and current documentation rather than copying an assumed API schema.

## Learning workflow references

Inspected 2026-09-18. These public skills informed the design of the learning workflow; their code and scripts are not bundled. The Canvas Companion instructions were written independently for this project.

- [Course Note Organizer](https://github.com/Sylvia-huangz/Course-note-organizer/blob/main/SKILL.md): source-aware lecture notes and recording/transcript coverage.
- [Anything to Course](https://github.com/lowwwbank/anything-to-course/blob/main/SKILL.md): objectives, practice and dialogue-based learning. This is a general study skill, not a Canvas connector.
