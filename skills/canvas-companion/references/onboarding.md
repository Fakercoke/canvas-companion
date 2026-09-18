# First connection for a nontechnical student

## First turn

Inspect current tools. If the school is unknown, ask only: “你在哪所学校上学？告诉我名字就行，我来找 Canvas 入口。” Adapt language to the user. If the school is already named, search its official website for the Canvas/student LMS link and open the verified destination with supported tools; do not ask the user to copy a URL you can find. If multiple schools share a name, resolve that ambiguity first. Do not guess a domain or send credentials through search.

An existing authenticated tool can be reused. Do not inspect unrelated accounts or other projects to discover identity. Installed Skill, configured connector and authenticated Canvas are different states.

## Select and execute one route

- Existing Canvas tools: discover schemas and perform a minimal course read.
- Browser tools: open the verified official entry, then ask the user to complete login/MFA there. Continue from visible success and read a course. Browser access does not require a manual API key or new MCP installation.
- An actual supported connector: inspect its real setup documentation, help configure it while preserving unrelated entries, then let the user authorize through the provider/school interface. Consult client instructions and key guide as needed.
- No usable tools/service: state the specific limitation. Ask the client name only if necessary to identify its supported options. Do not invent a remote service or claim a downloaded Skill adds browser/API tools.

If the student says “怎么做” or “不知道”, simplify the next action and perform everything currently possible. Do not repeat the same URL/token/config request. If unable to open the login page, give the verified clickable school entry and one action; explain the exact capability missing.

## First useful result

After access, use the user's existing course/task scope. If none is specified, show a short list of current visible course names/terms and ask which to use; do not fetch every course's contents. For the selected course return a small first result: course name, next visible assignment/deadline, source links, and what still could not be checked. Offer a natural next task without turning setup into a long questionnaire.

For a whole-course request, immediately move to the reading workflow; do not require a fictional demo. Ask for additional input only when it changes the next action. Do not promise connection will work before testing.

## Resume

When useful for multi-step work, save a brief local `canvas-session.md` in the user's private task workspace, never in this repository. Record the school URL, selected course/resource links, verified route, last check time, coverage gaps and next action. Store no credentials, cookies or unnecessary profile data. On another turn, recheck tool access and time-sensitive deadlines; a saved note is not proof of current authentication. Explain what is saved if persisting course content.
