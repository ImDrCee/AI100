# AI100 LLM Continuation Guide

Use this document to continue the AI100 exam-preparation work with another
LLM. Read it before changing or creating any study material.

## 1. Project Goal

This repository publishes concise, accurate, printable, and browser-friendly
AI100 exam resources.

The user may provide new:

- textbook chapters;
- lecture PPT/PPTX files;
- study guides;
- multiple-choice review questions and solutions;
- theory questions and solutions.

For each exam, synthesize those sources into:

1. a two-sided A4 cheat sheet in standalone HTML; and
2. concept slide decks for topics the user finds difficult.

The materials must prioritize the official study guide and review/theory
questions over generic textbook summaries.

## 2. Current Published Resources

- [AI 100 Midterm I - Portrait Large-Print Cheat Sheet](https://imdrcee.github.io/AI100/AI100_Midterm_Two_Sided_Cheat_Sheet_Portrait.html)
- [AI 100 Chapter 4 - McCulloch-Pitts Neurons and Finite Automata](https://imdrcee.github.io/AI100/AI100_Chapter4_Neurons_and_Finite_Automata_Slides.html)

Current repository:

- GitHub: `https://github.com/ImDrCee/AI100`
- GitHub Pages: `https://imdrcee.github.io/AI100/`
- Default branch: `main`

## 3. Existing File Roles

### Published files

- `AI100_Midterm_Two_Sided_Cheat_Sheet_Portrait.html`
  - Two-page A4 portrait cheat sheet.
  - Uses two balanced columns per page.
  - Body text is approximately 8 pt.
  - Designed for duplex printing with long-edge flipping.

- `AI100_Chapter4_Neurons_and_Finite_Automata_Slides.html`
  - Standalone 25-slide HTML presentation.
  - Covers McCulloch-Pitts neurons, Boolean prerequisites, finite automata,
    recurrent memory, and the finite-automaton/Turing-machine boundary.
  - Includes relevant official Review and Theory question references.
  - Supports arrow keys, Space, Home, End, touch swipes, URL slide fragments,
    and A4 landscape printing.

- `README.md`
  - Contains direct links to the rendered GitHub Pages resources.

### Local source files that must not be published automatically

The original working folder may contain a textbook draft, course slides,
study guides, questions, and solutions. Treat these as source material for
analysis, not as files to publish.

In particular:

- Never upload the textbook draft.
- Do not upload lecture PPT/PPTX files, review PDFs, solution PDFs, or other
  instructor-provided material unless the user explicitly requests it and
  confirms they have permission.
- Publish generated study aids only by default.

## 4. Source Priority

When sources disagree or space is limited, use this order:

1. Official exam study guide and stated exam scope
2. Official review questions and solutions
3. Official theory questions and solutions
4. Lecture PPT/PPTX material
5. Assigned textbook chapters
6. General background knowledge

Preserve the course's terminology and conventions, even when another field or
textbook commonly uses a different term. If there is a meaningful ambiguity,
state the course convention and briefly note the alternative.

## 5. Workflow for the Next Exam

### Step 1: Confirm scope

Ask the user for:

- exam name or number;
- included chapters;
- included lectures;
- whether all PPTs are in scope;
- permitted cheat-sheet page count and orientation;
- whether answers may appear directly on concept slides;
- whether existing files should be preserved as previous-exam versions.

Do not overwrite a previous exam's published file. Create a clearly named new
file, for example:

```text
AI100_Midterm_II_Two_Sided_Cheat_Sheet.html
AI100_Final_Two_Sided_Cheat_Sheet.html
AI100_Chapter7_Concept_Slides.html
```

### Step 2: Inventory sources

List all relevant files and identify:

- book chapter boundaries;
- lecture dates and topics;
- study-guide sections;
- every review question in scope;
- every theory question in scope;
- corresponding official solutions.

Do not assume PDF text extraction preserved diagrams correctly. Render and
inspect pages containing state diagrams, graphs, tables, equations, or other
visual questions.

### Step 3: Build a question-to-concept map

Before authoring, map each question to:

- concept tested;
- required definition or procedure;
- official answer;
- likely distractor or common mistake;
- lecture/chapter source.

Every in-scope review and theory question must appear in the final map. Place
question-reference badges beside the relevant concept, not only in an appendix.

### Step 4: Write the cheat sheet

The cheat sheet should emphasize:

- exact definitions;
- formulas and algorithms;
- compact comparison tables;
- worked calculation patterns;
- state-tracing procedures;
- official answer cues;
- common traps;
- short theory-answer templates.

Prefer readable compression over tiny text. Use the available page area
efficiently and balance columns.

### Step 5: Write concept slides

Concept slides should:

- begin with an intuitive mental model;
- introduce formal notation only after the intuition;
- show a repeatable solving procedure;
- include worked examples;
- explain why wrong approaches fail;
- connect related computational models;
- display relevant Review and Theory question badges;
- end with a complete question-reference map and mastery checklist.

The slides must be a standalone HTML file with no external runtime dependency.

### Step 6: Validate

For cheat sheets:

- emulate print media;
- verify the exact requested A4 page count;
- verify portrait/landscape dimensions;
- check every column and element for overflow or clipping;
- verify text remains searchable;
- visually inspect both/all printed pages.

For slides:

- test at a 16:9 viewport such as 1600x900;
- ensure every slide has no horizontal or vertical overflow;
- verify keyboard navigation;
- verify URL fragments such as `#14`;
- verify there are no browser console errors;
- verify print output produces one A4 landscape page per slide;
- visually inspect representative title, formula, diagram, table, and final
  reference slides.

Do not report completion until these checks pass.

## 6. HTML Design Requirements

### Cheat sheets

- Use `@page` with explicit A4 size and orientation.
- Use physical units (`mm`) for page dimensions.
- Use `break-after: page` or `page-break-after: always`.
- Enable `print-color-adjust: exact`.
- Hide browser-only controls during printing.
- Avoid content that depends on an internet connection.

### Slides

- Use one `.slide` section per slide.
- Provide visible previous/next controls and a slide counter.
- Support:
  - Right/Down/PageDown/Space for next;
  - Left/Up/PageUp for previous;
  - Home and End;
  - touch swipes;
  - URL hashes for direct slide access.
- Use inline SVG for automata, graphs, and diagrams.
- Keep formulas and answer cues large enough to read from a screen.
- Add print CSS for A4 landscape.

## 7. Current Course Conventions and Known Ambiguities

Retain these conventions if the topics reappear:

- McCulloch-Pitts output is `1` when
  `sum(weight_i * input_i) >= threshold`; otherwise it is `0`.
- AND: weights `(1,1)`, threshold `2`.
- OR: weights `(1,1)`, threshold `1`.
- NOT: the course slides/practice solutions emphasize weight `-1` and
  threshold `-0.5`.
- The textbook may show NOT with threshold `0`; both work for binary input
  under the stated `>=` rule. Prefer the repeated course convention and note
  the alternative only when useful.
- A single threshold neuron cannot compute XOR/XNOR because they are not
  linearly separable.
- A finite automaton accepts only when it ends in an accept state after the
  entire finite input has been read.
- An accept state is drawn with a double/concentric circle.
- The language of an automaton is the set of all strings it accepts.
- A complete DFA for exactly `101` needs a rejecting sink and transitions for
  every wrong or additional symbol.
- The course summary is:
  `finite automaton + external read/write memory = Turing machine`.
- Course slides may use "admissibility" to mean guaranteed optimality in
  search. Standard later AI terminology often uses "optimality" for the
  property and "admissible" for a non-overestimating heuristic.

## 8. Git and Publishing Rules

- Repository: `ImDrCee/AI100`
- Keep the repository private unless the user explicitly changes that choice.
- GitHub Pages output is public.
- Upload generated HTML study resources and documentation only by default.
- Never upload the textbook or other instructor-provided source files without
  explicit permission.
- Never overwrite an existing published exam resource unless explicitly asked.
- Use descriptive commit messages, for example:

```text
Add Midterm II printable cheat sheet
Add Chapter 7 concept slides
Update study resource links
```

- After publishing, verify the exact `github.io` URL returns HTTP 200 and
  renders as a webpage rather than source code.
- Add every new public resource to `README.md` using its GitHub Pages URL.

## 9. README Link Format

Use ordinary Markdown links:

```markdown
[Resource title](https://imdrcee.github.io/AI100/FILENAME.html)
```

GitHub Markdown cannot force links to open in a new tab. Users can use
Ctrl+click, Cmd+click, or the browser's "Open link in new tab" command.

## 10. Completion Checklist for the Next LLM

Before concluding a future exam update, confirm:

- [ ] Exam scope was confirmed.
- [ ] All source files were inventoried.
- [ ] Every in-scope Review question was mapped.
- [ ] Every in-scope Theory question was mapped.
- [ ] Official solutions were checked.
- [ ] Diagram-based questions were visually inspected.
- [ ] Existing published files were preserved.
- [ ] New HTML passes screen and print validation.
- [ ] Only approved generated files were uploaded.
- [ ] GitHub Pages URLs were verified.
- [ ] `README.md` was updated with all new links.
- [ ] The user received direct links and print/navigation instructions.
