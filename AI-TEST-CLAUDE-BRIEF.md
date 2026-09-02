# Claude implementation brief — make the GVDP AI test sing

Read `CLAUDE.md` before touching the site. It is authoritative for voice, design, architecture and deployment. This brief is deliberately specific about the assessment. Do not redesign the rest of the page.

## The outcome

Replace the current five-question yes/no checklist with a six-question, 60-second diagnostic that tells a founder how AI is operating in their business and gives them one useful next move.

The test should make this progression obvious without jargon:

0. **Write** — AI creates content. A person still carries the work.
1. **Connect** — AI can see the business through its existing systems.
2. **Act** — agents complete work within boundaries set by people.
3. **Become** — AI changes the product, customer promise or business model.

There are four diagnostic stages, but only three next-step editorial outputs. This resolves the apparent conflict in the original request:

- A Level 0 result points to output 1: **Connecting your existing systems with an AI brain**.
- A Level 1 result points to output 2: **Developing agents to work for you**.
- A Level 2 or Level 3 result points to output 3: **Five companies that became completely AI-native**.

The three articles do not exist yet. Use clear placeholder constants for their URLs. Do not invent or publish the articles as part of this change.

## Why the existing test needs to change

The current test counts how many negative statements sound familiar. It has several problems:

- The result is a deficit count, not a meaningful stage.
- A yes/no answer loses too much nuance.
- The questions mix tools, knowledge and maturity. Knowing the term MCP is treated as evidence of readiness when it is not.
- It rewards tool choice rather than business change.
- The final answer is a list of generic payoffs followed by the same sales CTA for nearly everyone.
- Someone who answers “Not us” five times is told they are unusually advanced, even though the test has not gathered enough evidence to justify that claim.
- It does not create a natural bridge into Gerald's three planned articles.

## What to borrow from the GenAIPI assessment

Reference: <https://genaipi.org/ai-readiness-assessment>

Useful ideas to adapt:

- State the time and value before the first question.
- Show visible progress and a running question count.
- Use labelled maturity choices rather than bare numbers or yes/no answers.
- Ask about observable behaviour: manual handoffs, connected context, automation, decision-making and measurable outcomes.
- Give a result preview before asking for contact details.
- Make the result feel tangible: a named stage, the most important gap and a prioritised next action.

Things not to copy:

- Do not use 24 questions or eight departments. GVDP promises 60 seconds.
- Do not show a pseudo-precise percentage. A maturity stage is more useful than “60%”.
- Do not require a phone number or gate the diagnosis behind a form.
- Do not reproduce GenAIPI's wording, visual design, scoring labels or sales funnel.
- Do not turn the result into a dashboard of generic cards. Keep the existing editorial GVDP design.

## Section copy

Replace the current diagnostic heading and introduction with:

**Eyebrow**

`The 60-second AI test`

**Heading**

`Is AI helping your business write—or changing how it works?`

**Introduction**

`Six questions. No jargon. See whether your AI can only create, can see the business, can do the work—or is changing what the business can become.`

Show a single start button before question one:

`Start the test →`

Do not ask for a name, email or company before the result.

## The six questions

Present one question at a time. Each answer has an internal score of 0–3, but the user should see the answer text, not a large naked number. The whole answer row is clickable. Selecting an answer should advance after a short 150–200ms visual acknowledgement.

### Question 1 — current use

**Question:** `Today, what does AI mostly do in your business?`

- 0 — `Writes, summarises or creates content`
- 1 — `Uses information from our files or business tools`
- 2 — `Completes tasks across tools, with our approval`
- 3 — `Powers something we could not offer before`

### Question 2 — context

**Question:** `How does AI get the information it needs?`

- 0 — `We paste it into a chat each time`
- 1 — `It is connected to at least one system or knowledge source`
- 2 — `An agent finds the right context and keeps track of the job`
- 3 — `The system learns from every interaction and outcome`

### Question 3 — action

**Question:** `What happens after AI gives you an answer?`

- 0 — `A person copies it into the next tool`
- 1 — `It can update one connected system`
- 2 — `It completes several steps, pausing when approval is needed`
- 3 — `It acts within clear limits and sends exceptions to a person`

### Question 4 — customer value

**Question:** `Where does AI create the clearest value for your customer?`

- 0 — `Faster content and replies`
- 1 — `A more personal experience using customer information`
- 2 — `It notices what a customer needs and helps us act first`
- 3 — `It makes a new product, service or promise possible`

### Question 5 — evidence

**Question:** `How do you know the AI is working?`

- 0 — `The output looks good or saves a little time`
- 1 — `We track time or cost in a specific workflow`
- 2 — `We measure a customer, quality or revenue outcome`
- 3 — `Those outcomes improve the next decision automatically`

### Question 6 — dependence

**Question:** `If AI disappeared tomorrow, what would happen?`

- 0 — `Writing and office work would be slower`
- 1 — `Manual handoffs between our systems would return`
- 2 — `Important day-to-day operations would stop`
- 3 — `Our core product or business model would no longer work`

## Interaction details

- Show `Question 1 of 6` and a thin progress rule above each question.
- Add a quiet `Back` control from question two onwards. It must restore the previous selection.
- Do not show a separate Next button; a selected answer advances.
- Keep all questions and answers in a single JavaScript data structure so the copy and scoring are easy to change.
- Allow keyboard operation. Each question should be a `fieldset` with a real `legend`, and answers should behave like radio buttons even if styled as large text rows.
- Respect `prefers-reduced-motion`.
- On completion, replace the question panel with the result in place. Do not redirect.
- Provide `Take it again` beneath the result.

## Scoring

Add the six selected values for a total from 0 to 18:

- 0–4: Level 0 — Write
- 5–9: Level 1 — Connect
- 10–14: Level 2 — Act
- 15–18: Level 3 — Become

Add two credibility guardrails:

1. The result cannot exceed Level 1 unless Question 3 is scored 2 or 3. Producing sophisticated output is not agentic if a person still carries every step.
2. Level 3 requires Question 4 to be 3 and Question 6 to be at least 2. If either condition is missing, cap the result at Level 2. AI-native means the customer offer or operating model has changed.

Do not display the numerical total or a percentage. The score is classification logic, not scientific precision.

## Result design

Use one strong editorial result block, not a grid of cards. It should contain, in this order:

1. Eyebrow: `Your AI stage`
2. Result heading
3. A four-stage horizontal ladder: `Write — Connect — Act — Become`, with the current stage emphasised in orange
4. One plain-English truth about the current stage
5. `The shift to make next`
6. One concrete action for this week
7. One primary link to the matching article
8. A quieter `Talk it through with Gerald →` link to `#question`
9. `Take it again`

Do not congratulate everyone and do not shame lower scores. The tone is direct, useful and optimistic.

### Level 0 result

**Heading:** `Level 0 — AI writes. You carry the work.`

**Truth:** `You are getting useful output, but AI still begins and ends in a chat window. The business around it has not changed yet.`

**Shift label:** `Write → Connect`

**This week's action:** `Choose one task you repeat every week. Connect AI to the file, inbox or system that holds the context, so nobody has to paste it in again.`

**Primary CTA:** `Connect your existing systems with an AI brain →`

**Content constant:** `LEVEL_ONE_ARTICLE_URL`

### Level 1 result

**Heading:** `Level 1 — AI can see the business.`

**Truth:** `Your systems are beginning to share context with AI. People still move most of the work from insight to action.`

**Shift label:** `Connect → Act`

**This week's action:** `Pick one workflow with a clear trigger and finish line. Let an agent collect the context, prepare the action and pause for approval.`

**Primary CTA:** `Develop agents that work for you →`

**Content constant:** `LEVEL_TWO_ARTICLE_URL`

### Level 2 result

**Heading:** `Level 2 — AI does useful work.`

**Truth:** `Agents are completing real tasks inside clear boundaries. The next opportunity is not more automation. It is a different customer promise.`

**Shift label:** `Act → Become`

**This week's action:** `Ask what you could now deliver in ten minutes that used to take ten days—and whether that should become the product.`

**Primary CTA:** `See five companies that became completely AI-native →`

**Content constant:** `LEVEL_THREE_ARTICLE_URL`

### Level 3 result

**Heading:** `Level 3 — AI changes what the business can be.`

**Truth:** `AI is part of the product or operating model, not an add-on. Your edge now depends on judgement, feedback and what your system learns that competitors cannot copy.`

**Shift label:** `Become → Compound`

**This week's action:** `Find the most important decision your system makes. Capture the outcome and use it to improve the next decision.`

**Primary CTA:** `Compare your model with five AI-native companies →`

**Content constant:** `LEVEL_THREE_ARTICLE_URL`

## Personalised evidence beneath the result

Under the core result, show a short section titled `What your answers say` with exactly two sentences generated deterministically from the answers—no API call.

- First sentence: reflect the user's highest-scoring dimension.
- Second sentence: reflect the user's lowest-scoring dimension as the immediate constraint.
- If several dimensions tie, prefer Question 4 for the strength and Question 3 for the constraint because customer value and action are the most commercially meaningful.
- Write the sentence fragments in advance in the question data. Do not send assessment answers to Claude or any external service.

Example:

`Your strongest signal is customer value: AI is already helping you anticipate what people need. The constraint is action: a person still has to carry the answer into the next system.`

## Conversion behaviour

The diagnosis and article link must be visible without a form.

The secondary `Talk it through with Gerald →` link should:

- scroll to the existing Ask Gerald form;
- set the hidden `topic` value to `assessment-level-0`, `assessment-level-1`, `assessment-level-2` or `assessment-level-3`;
- change the message placeholder to `I got Level X. The workflow I want to change is…`;
- not prefill or submit any personal information.

Do not add a new popup, lead gate, phone field or newsletter modal.

If lightweight analytics already exists, emit an `ai_test_completed` event containing only the level and article path. Do not add a new analytics vendor and do not include individual answers or personal data.

## Visual direction

Stay inside the established editorial system in `index.html`:

- warm paper background;
- Fraunces for the question and result headline;
- Manrope for controls and supporting copy;
- black rules and orange emphasis;
- no gradients beyond the locations already allowed in `CLAUDE.md`;
- no icons, dashboard cards, badges, confetti, glass effects or SaaS-style illustrations.

Suggested treatment:

- The assessment remains a maximum of roughly 52rem wide.
- Replace the heavy filled box with a clean top and bottom rule, plus a 3px orange progress line.
- Answers are full-width rows separated by thin rules. On hover/focus, shift the label slightly right and colour the rule orange.
- The result heading should be large enough to feel like a reveal, but smaller than the main page thesis.
- The stage ladder is text on one line on desktop and two lines on mobile. Do not turn it into four feature cards.

## Architecture constraints

- Keep the site framework-free.
- Keep all page HTML, CSS and client JavaScript in `index.html`.
- Do not add a package or build step.
- Do not change `/api/ask` unless the existing endpoint rejects the new `topic` values. Inspect it first.
- Do not change any section outside `#ai-test` except the smallest code needed to pass the assessment topic into the existing form.
- Do not change the page's offer, evidence, photographs, masthead or footer.
- Do not deploy, push or publish. Leave the implementation ready for review in the working tree.

## Acceptance criteria

- The test has six questions and can genuinely be completed in about 60 seconds.
- Every answer is explicit and describes observable behaviour.
- Progress, Back and retake all work.
- The browser Back button is not hijacked.
- Each completion produces exactly one Level 0–3 diagnosis and one of the three editorial next-step paths.
- The two scoring guardrails work.
- The article URLs exist as obvious constants and can be replaced later.
- The user sees the full result without entering contact details.
- The Ask Gerald link sets the correct assessment topic and placeholder.
- No assessment answers leave the browser.
- The static/no-JavaScript fallback still explains the four stages and provides a link to Ask Gerald.
- The test is usable at 320px width, at desktop width, by keyboard and with reduced motion.
- Existing form behaviour and the rest of the page remain unchanged.
- No publish or deployment action is taken.

## Deliverable from Claude

Implement the assessment in `index.html`, test all four result paths locally, and report:

1. the files changed;
2. the score/guardrail test cases used;
3. the placeholder article constants that still need final URLs;
4. any genuine ambiguity or risk that remains.

