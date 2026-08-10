# Study Plan

This is the practical day-by-day guide for the first two weeks of the 120-day sprint.

Do not complete an entire MDN module in one day. Study only the sections listed here.

## Daily rhythm

| Activity | Target |
|---|---:|
| Learn | 45 min |
| Recall | 30 min |
| Build | 90 min |
| Practice drill | 30 min |
| Documentation and debugging | 30 min |
| Ship and reflect | 15 min |

The target is understanding and evidence, not finishing every page linked from a module. Use the full time to practise, build, debug, and review when the reading itself is shorter.

## What the practice block means by phase

| Roadmap phase | Practice drill |
|---|---|
| Days 1–10 | Rebuild the day's HTML/CSS/Git concept from memory and test it. No formal DSA or SQL yet. |
| Days 11–30 | JavaScript exercises based on the current topic. DSA is optional until the JavaScript foundations are comfortable. |
| Days 31–60 | TypeScript and React exercises, with optional small problem-solving exercises. |
| Days 61–80 | PostgreSQL exercises first; optional SQL interview questions only after the relevant SQL concept is understood. |
| Days 81–112 | Apply DSA/SQL selectively while building the capstone and production work. |
| Days 113–120 | Interview drills: coding, SQL, debugging, and system design. |

## Days 1–14

| Date | Day | Focus | Study | Build | Done when |
|---|---:|---|---|---|---|
| Aug 10 | 1 | Environment and Git | [GitHub Skills](https://skills.github.com/); [Git basics](https://docs.github.com/en/get-started/git-basics). Learn `init`, `status`, `add`, `commit`, and `log`. | Set up the repository, mission, first lesson, and first commit. | You can create, commit, and inspect a file. |
| Aug 11 | 2 | Basic HTML | [Basic HTML syntax](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Structuring_content/Basic_HTML_syntax). Read: HTML, element anatomy, nesting, attributes, document anatomy, and adding page features. | Build a profile page with headings, paragraphs, links, and an image. | You can create a valid `index.html` and explain elements versus attributes. |
| Aug 12 | 3 | Forms | [Your first form](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/Your_first_form); [native controls](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/Basic_native_form_controls); [form validation](https://developer.mozilla.org/en-US/docs/Learn_web_development/Extensions/Forms/Form_validation). Learn `form`, `label`, `input`, `textarea`, `button`, `for`, `id`, `name`, `required`, and `type`. | Build an accessible contact form. | Every field has a label, native validation works, and the form works with only the keyboard. |
| Aug 13 | 4 | CSS foundations | [CSS styling basics](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Styling_basics). Read CSS structure, selectors, cascade, box model, and values/units. | Style the profile page. | You can explain margin versus padding and style the page without copying CSS. |
| Aug 14 | 5 | Flexbox | [Flexbox](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Flexbox). Read the flex model, `display`, direction, wrapping, alignment, and gap. | Recreate a navigation bar and card row. | You can arrange items in rows/columns, align them, and add space between them. |
| Aug 15 | 6 | CSS Grid | [CSS Grid](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Grids). Read grid creation, columns, rows, `fr`, gap, and basic placement. | Build a dashboard with a header, sidebar, main area, and footer. | You can create a two-column grid and explain Grid versus Flexbox. |
| Aug 16 | 7 | Responsive design | [Responsive design](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/CSS_layout/Responsive_Design). Read responsive design, media queries, viewport meta, and basic responsive layouts. | Make the page work on mobile, tablet, and desktop. Review Days 1–6. | The page works at three widths without horizontal scrolling. |
| Aug 17 | 8 | Accessibility | [Accessibility on the web](https://developer.mozilla.org/en-US/docs/Learn_web_development/Core/Accessibility). Read accessible HTML, keyboard use, headings, landmarks, alt text, focus, and contrast. | Audit and improve the profile page and contact form. | You can navigate with a keyboard and identify accessibility problems. |
| Aug 18 | 9 | GitHub workflow | [GitHub Skills](https://skills.github.com/); [Introduction to GitHub](https://github.com/skills/introduction-to-github); [Review pull requests](https://github.com/skills/review-pull-requests). | Complete issue → branch → commit → pull request → merge. | You have completed one full GitHub workflow. |
| Aug 19 | 10 | Portfolio v1 | [GitHub Pages](https://pages.github.com/); [GitHub Pages documentation](https://docs.github.com/en/pages). | Combine the profile, form, responsive layout, and accessibility work; deploy it. | Someone else can open your public portfolio URL. |
| Aug 20 | 11 | JavaScript values | [Grammar and types](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Grammar_and_types); [Expressions and operators](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_operators). Read values, variables, strings, numbers, booleans, `null`, `undefined`, operators, and `typeof`. | Complete 20 small console exercises. | You can predict simple JavaScript output before running it. |
| Aug 21 | 12 | Conditions and loops | [Control flow](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Control_flow_and_error_handling); [Loops](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration). Read `if`, `else`, ternary, `switch`, `for`, `while`, truthy/falsy, `break`, and `continue`. | Build input → decision → output exercises. | You can choose and write a condition or loop without copying an example. |
| Aug 22 | 13 | Functions and scope | [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions). Read defining/calling functions, parameters, return values, scope, and arrow functions. | Refactor earlier exercises into reusable functions. | You can write a function that accepts input and returns a result. |
| Aug 23 | 14 | Arrays | [Array reference](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array). Read array creation, indexes, `.length`, `push`, `pop`, `slice`, `includes`, and `indexOf`. | Practise adding, removing, finding, counting, and reading array items. | You understand ordered collections and can work with values by index. |

## Intentionally deferred

- HTML tables: study them after the contact-form foundation; they are not needed for Day 3.
- Advanced form controls, form styling, custom widgets, and sending form data with JavaScript.
- Advanced CSS, responsive images, subgrid, and complex layout techniques.
- Formal LeetCode practice until JavaScript begins on Day 11.
- `map`, `filter`, `reduce`, and `find` until Day 16.

## Weekly review

Every Sunday, answer:

1. What did I build?
2. What can I explain without notes?
3. What still feels like magic?
4. What bug or mistake taught me something?
5. What evidence did I commit?
