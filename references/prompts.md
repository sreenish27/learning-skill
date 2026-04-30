# Prompts — diagnostic probes, retrieval templates, spaced-review schedules

Read this when running Coach or Diagnose mode and you need a concrete rep to hand the user. These are templates — adapt to the specific target skill.

## Diagnostic probes (to verify a prerequisite is actually in LTM)

The test is whether the user can produce the answer unassisted, cleanly, without lengthy hesitation. Slow-and-correct often means it's not automatized enough to serve as a prereq.

### Format
- "Without looking anything up: [prompt]. Give me your answer, then I'll tell you what to check."
- Time-box when appropriate: "90 seconds. Go."
- Ask for the answer *and* a one-line justification. The justification reveals whether it's retrieved understanding or a lucky guess.

### Probe patterns by domain

**Math (calculus example):**
- "State the chain rule. Then apply it to d/dx of sin(x²) from scratch — show every step."
- "What's the derivative of ln(x)? Derive it from the definition of derivative, not memory."
- "Give me an example of a function that is continuous everywhere but not differentiable anywhere. Name it, don't just describe it."

**Math (linear algebra example):**
- "Define rank. Give a 3×3 matrix of rank 2. Verify."
- "State the spectral theorem in your own words. What are the two conditions on the matrix and what does the theorem guarantee?"
- "Without computing, what's the determinant of a matrix with two identical rows? Why?"

**Coding (algorithms example):**
- "Implement binary search on a sorted array. Closed-editor — just type it. Then tell me the invariant that makes it correct."
- "What's the time complexity of inserting into the middle of a dynamic array? Justify from the underlying mechanism."
- "Write the recurrence for merge sort. Solve it."

**ML (foundations example):**
- "Write the softmax function. Then explain why we subtract the max of the inputs before exponentiating."
- "State the bias-variance decomposition. What does each term represent?"
- "Derive the gradient of MSE loss w.r.t. a single weight in linear regression."

## Retrieval prompts during Coach mode

Keep these short. The rep is the attempt, not the framing.

- "Without looking — give me [the thing]."
- "From scratch — derive [the result]."
- "Close the notes. What's the next step in [the procedure]?"
- "New instance: [slightly varied problem]. Same technique. Go."
- "What would change if [one condition were different]?"
- "Summarize in one sentence, from memory: [the concept]."

## Grading the attempt

After the user attempts a rep, grade it in one of these categories. State which, plainly:

- **Clean.** Correct, unassisted, reasonable time. Counts as a successful retrieval. Raise difficulty or increase interval.
- **Clean but slow.** Correct, unassisted, but took too long. The knowledge is there but not automatized. Run more reps at this difficulty before raising.
- **Peeked.** Required a reference or hint. Doesn't count as a retrieval rep. Re-run the same kind of problem clean before moving on.
- **Failed.** Attempted and got it wrong. Good news: failure primes the correct answer. Now give the explanation — the user will retain it better after the failed attempt than they would have without.
- **Didn't attempt.** User tried to extract the answer instead of attempting. Send it back: attempt first.

## Spaced review schedule

Default intervals after a clean retrieval, unless the material is unusually dense or unusually simple:

- Same session: 1 more rep with a short delay (minutes) and a different surface form.
- +1 day
- +3 days
- +1 week
- +2 weeks
- +1 month

If a review is failed, reset the interval — next review is tomorrow, not continuing the schedule.

If a review is "too easy," extend the next interval more aggressively. Easy review is wasted review.

## Session structure template (for Coach mode)

Short template for a typical 30–60 minute study block under this skill:

1. **Warm-up retrieval (5 min).** Re-probe 2–3 items from prior sessions that are due for review.
2. **Micro-dose instruction (5–10 min).** Shortest viable explanation of the next concept.
3. **Attempt reps (20–30 min).** Problems at progressively increasing difficulty. Closed-book. Graded in real time.
4. **Consolidation (5 min).** User states, from memory, the key point and one worked example. No looking.
5. **Close-out (2 min).** Announce: what's retained, what's tomorrow's first rep, what's on the spaced-review queue.

## When to pull the difficulty lever

- Up one notch: clean rep, reasonable time, user seems slightly under-challenged.
- Up two notches: two clean reps in a row, fast.
- Down one notch: failed rep, confusion on a sub-step.
- Down two notches: repeated failures, signs of WM overload (user losing track mid-problem, forgetting the question).
- Hold: clean-but-slow, or successful-with-effort. Build automaticity before moving.

## Interview prep adaptation

For interview contexts, overlay these on top of the regular loop:

- Reps should be done out loud, in the format the interview will take.
- Add the constraint of explaining while solving. This is harder than silent problem-solving and trains the specific skill being evaluated.
- Include interleaving heavily — interviews don't tell you which method to apply.
- Add adversarial follow-ups: "what if the input is empty", "what's the complexity", "can you do it without extra space".
- Track: problems solved unassisted, in time, while explaining, without silly mistakes. That's the real metric.
