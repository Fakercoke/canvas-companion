# Read a course without repeated manual transfers

## Scope and inventory

When asked to read a whole course, identify its term and title, then enumerate modules/items, syllabus, pages, announcements, files, assignments, quiz metadata and required/recommended reading links accessible to the student. For all courses, enumerate the account's visible courses and group by term; clarify current term versus archives if ambiguous. Do not inspect peers' private information just because broad tools expose it.

Use actual connector schemas or browser navigation. With an authorized API tool, common read routes include `/api/v1/courses`, `/api/v1/courses/:course_id/modules`, module `/:module_id/items`, `/pages`, `/assignments`, `/files` and `/quizzes` under a course. Announcement APIs use context codes; consult official documentation rather than guessing. These are API routes, not guaranteed MCP tool names. Classic Quizzes and New Quizzes/LTI may differ.

Follow each API response's `Link` next relation until exhausted, validating the Canvas origin before attaching credentials. In browsers, expand modules and inspect pagination/lazy loading. Listing results are an inventory, not evidence of reading full content.

## Read content in batches

For each item keep: course/week, title, type, source URL, retrieval time, access/reading status and relevant notes. Fetch page bodies and documents with authorized tools. If local document extraction is needed, download to a private user workspace outside this repo, using available PDF/document tools. The student should not have to manually transfer material already accessible to the agent.

Resolve course reading-list and library links using the user's permitted access; separate login or unavailable full text is a genuine gap. Do not stop at bibliography metadata and claim the articles were read. For videos, distinguish viewed content, captions/transcripts and metadata; do not invent a transcript.

Work in manageable batches, saving an index and summaries with source locations so later turns can resume. Report counts by fully read, partly read, metadata-only, inaccessible and pending. Do not claim “all course information” while pending or unread items remain. Record changes by rechecking announcements/deadlines when freshness matters.

## Long documents and recordings

For a full-reading request, establish the page/section count or recording duration first. Track actually reviewed ranges separately from downloaded/extracted ranges. Process the entire requested scope in manageable batches, retaining source locations and unresolved gaps. An 80-page PDF with only pages 1–10 reviewed remains partial even when all text was extracted. If extraction truncates, continue from the last verified range; inspect image-only pages, tables and figures with appropriate visual tools rather than assuming text extraction captured them.

Do not silently reduce a whole-document request to keyword hits or an abstract. If the user requests targeted reading, state the selected scope and avoid claiming full coverage. Report unread/unavailable ranges and their effect on the answer; continue independent useful work. For learning-specific lecture/transcript handling, follow [learning and tutoring](learning.md).

## Outputs

Adapt to the request: course overview, week-by-week notes, concept explanations, source-linked reading synthesis, revision questions, assignment preparation or a cross-course workload plan. Preserve distinctions between required readings and optional research. A connection eliminates some manual transfers, not school access restrictions or AI context limits.

Sources: [Canvas API documentation](https://developerdocs.instructure.com/services/canvas), [Pagination](https://developerdocs.instructure.com/services/canvas/basics/file.pagination).
