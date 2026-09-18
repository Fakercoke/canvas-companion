# Deadline and submission-status checks

Use this workflow for due dates, upcoming work and outstanding assignments. Stay within the requested courses and time range; do not read all course materials merely to build a deadline list.

## Cover the requested courses

Discover visible courses and terms. For an unqualified request for upcoming work, use the current term and state that scope; ask only if the term is genuinely ambiguous. Dashboard favourites and a course-specific connector are not a complete enrolment inventory. Use the course list when available and label coverage as partial otherwise.

For each selected course:
- Read all assignment-list pages, including exposed graded discussions and quizzes, and distinguish dated from undated items. A planner/to-do list alone is insufficient: it may omit completed or dismissed items.
- Check the course assessment overview or syllabus and relevant deadline/extension announcements. Follow directly relevant instructions or attachments when they contain dates absent from the list; do not indiscriminately download readings.
- Include future work mentioned in the overview even when its submission portal is not yet published. Label these dates as published in the overview, with the personal deadline unverified.
- Merge duplicate references by course and assignment identity. Keep separate required deliverables with separate portals or dates. A name containing “delete” is not sufficient evidence that a task is cancelled.

Stop after the selected sources are covered or a concrete access boundary is reached. Return checked courses, check time/timezone, unread sources and undated work. Say “all found in the checked sources”, not “all Canvas work”, if coverage is incomplete.

## Establish the applicable deadline

Record the source link, displayed timezone, effective user due date if exposed, dates in instructions/announcements, and availability closing time separately. Use an explicitly applicable personal override or extension when verified; a generic API due_at field alone does not prove that all personal overrides were resolved.

Compare contradictory sources and flag unresolved conflicts rather than silently replacing one with another. A newer timestamp alone does not prove an extension applies to this student. Never treat “Available until” as the due date. Do not invent 23:59 when a source gives only a date. If timezone is not verified, label it as the page-displayed time rather than assuming the computer's timezone.

## Verify status at the correct scope

Use the current student's assignment/submission details or authenticated group receipt, not a generic assignment-list label alone. Report one of:
- Submitted: a recorded submission state or receipt, with attempt/time when exposed.
- Graded: a recorded grade for the current student/group; distinguish any later unsubmitted draft if present.
- Not submitted: an explicit current-user/group state supports this; distinguish missing, late, draft and in progress where visible.
- No submission required: the assignment's instructions/type explicitly establish this.
- Unknown: submission details are unavailable, ambiguous or contradictory.

A course-wide has_submitted_submissions flag does not establish this student's submission. A list label such as “No submission” can conflict with a quiz grade or group receipt; open the details before concluding work is missing. For group work, check the applicable group's submission because another member may have submitted it. Do not inspect unrelated students' records. Uploaded/selected files and an “In Progress” attempt are not receipts.

For a due-date-only request, avoid unnecessary grade collection and mark status unverified when not checked. For “what have I not submitted?”, verify status for candidate tasks before calling them outstanding. Do not start quizzes or submit work during a read-only check.

## Present an actionable result

Sort upcoming dates and show course, task/deliverables, deadline with timezone, status evidence when requested, and source. Separate past-due dates from verified missing work. Surface conflicts and unknown dates alongside the affected task. Keep priorities conditional on unverified submission status. Reading a deadline list does not create recurring monitoring or reminders.
