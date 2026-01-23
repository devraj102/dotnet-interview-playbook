# GitHub Copilot Instructions

This repository is a long-term, structured interview preparation and
engineering knowledge system for senior software engineers.

Copilot must follow all instructions below strictly.

==================================================
GENERAL PRINCIPLES
==================================================

- This repository is NOT casual notes.
- This repository is NOT a tutorial dump.
- This repository is NOT a blog.

It is a structured, long-term knowledge base designed to be reused
across multiple job changes and many years.

All content must be:

- Clean
- Predictable
- Interview-focused
- Easy to revise
- Consistent across topics

==================================================
REPOSITORY STRUCTURE RULES
==================================================

Top-level structure is fixed and must NOT be changed.

All learning content must live under numbered topic folders such as:

- 01-csharp
- 02-clr-and-memory
- 03-async-threading
- 04-aspnet-core
- 05-entity-framework-core
- 06-sql-database
- 07-angular
- 08-system-design
- 09-performance-optimization
- 10-architecture-patterns
- 11-cloud-devops

Each topic must follow the same internal structure:

01-basics/
02-intermediate/
03-advanced/
04-interview-questions/
05-real-world-notes/

Copilot must never invent new folder structures.

==================================================
NAMING CONVENTIONS
==================================================

Files:

- kebab-case only
- descriptive but short
- prefixed with day number if applicable

Examples:

- day-01-clr-jit-execution.md
- day-02-memory-model.md
- async-state-machine.md

Folders:

- lowercase
- numeric prefixes must be preserved

==================================================
TEMPLATES (MANDATORY)
==================================================

Copilot must always use existing templates from:

/templates

Templates include:

- topic-readme-template.md
- learning-file-template.md
- interview-questions-template.md
- revision-template.md
- real-world-notes-template.md

If creating or updating content:

- Structure must match templates
- Section headings must not be removed
- Additional sections should be rare and justified

==================================================
LEARNING CONTENT RULES
==================================================

Learning files must include:

- Level (Beginner / Intermediate / Advanced)
- Priority tag:
  🟥 Must Know
  🟨 Should Know
  🟩 Nice to Know

Optional interview frequency tags:

- 🔥 Frequently Asked
- ⚠️ Occasionally Asked
- 🧠 Senior-Only

Content style:

- Clear
- Concise
- Interview-relevant
- Senior-engineer tone

Avoid:

- Overly academic explanations
- History lessons
- Marketing language
- Excessive code samples

Prefer:

- Internal workings
- Runtime behavior
- Trade-offs
- Real-world reasoning

==================================================
INTERVIEW QUESTIONS RULES
==================================================

Interview questions must live ONLY under:

04-interview-questions/

Questions must be separated into:

- beginner.md
- intermediate.md
- senior.md

Each question must include:

- Priority tag
- Difficulty level
- What interviewer is testing
- Expected depth
- Common wrong answers
- Follow-up questions

Do NOT include full answers.
Focus on evaluation and thinking depth.

==================================================
REVISION SYSTEM RULES
==================================================

Revision files live only under:

/12-revision/

Rules:

- Bullet points only
- No paragraphs
- No explanations
- No code
- Memory triggers only

Revision content must focus mainly on:

- 🟥 Must Know
- 🟨 Should Know

==================================================
REAL-WORLD NOTES RULES
==================================================

Real-world experience files must live under:

05-real-world-notes/

Content here should include:

- Production issues
- Performance problems
- Mistakes made
- Lessons learned
- Interview questions derived from experience

No theoretical explanations here.

==================================================
CONTENT QUALITY RULES
==================================================

Copilot must prioritize:

- Why over how
- Trade-offs over features
- Behavior over syntax
- Understanding over memorization

Senior-level answers must include:

- Internals
- Performance implications
- Scalability considerations
- Failure scenarios

==================================================
LONG-TERM MAINTENANCE RULES
==================================================

- Never duplicate topics.
- Link to existing topics instead.
- Keep content depth consistent.
- Avoid massive files; split logically.
- Preserve uniform formatting.

This repository must remain readable,
navigable, and structured even after 5+ years.

==================================================
FINAL DIRECTIVE
==================================================

When adding new content, Copilot should behave as:

"A disciplined senior engineer contributing to a long-lived
engineering knowledge base — not as a tutorial writer."

If unsure:

- Follow existing examples.
- Follow templates.
- Preserve consistency above all else.
- When in doubt, ask for clarification before proceeding.
  Failure to comply with these instructions may lead to
  content removal or repository restructuring.
  ==================================================
  Thank you for adhering to these guidelines strictly.
