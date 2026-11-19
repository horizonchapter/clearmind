# Results

The tests were run in French, so the prompts and grading grids in this folder are in French.

Blind A/B/C tests on claude.ai (Sonnet 5.5), one conversation per version. Judges: Claude Opus 5.5 sub-agents that did not know which version was which. One run per version, so read these as strong signals, not statistics.

Versions: no skill / full version (about 5,300 words) / Clearmind (compact, about 3,100 words).

## Test 1: one long, messy, voice-dictated project message (38 traps)
Two blind graders, score out of 38.

| Grader | No skill | Full | Clearmind (compact) |
|---|---|---|---|
| Grader 1 | 28.5 | 36.5 | 36 |
| Grader 2 | 29 | 36 | 35 |

What the skill added: missing attachments flagged first, contradictions caught, priced math with labels, the user's bad idea refused under pressure, the ambiguous deadline asked instead of guessed. What it cost: longer answers, English labels leaking into French replies (fixed since).

## Test 2: app project over 3 turns (30 traps + pushback + handoff)
Two blind graders, score out of 34.

| Grader | No skill | Full | Clearmind (compact) |
|---|---|---|---|
| Grader 1 | 27.5 | 31.5 | 30.5 |
| Grader 2 | 26.5 | 31.5 | 29.5 |

Six persona judges (student, parent, entrepreneur, developer, lawyer, AI-style editor): no first place for the no-skill version. A simulated panel of 30 profiles preferred the no-skill version for its warmer tone (12 votes against 10 and 8), which drove the tone fixes in the current version.

Biggest failure without the skill: the handoff for the next chat listed the assistant's own proposals as the user's decisions, and the answer claimed to know a design file it never received.

## Fixes applied after the tests
Fewer certainty labels, labels translated into the reply's language, cautious default when a missing fact changes legal or money advice (possible minor), hidden prerequisites check, questions on vague references, native typography, readable handoffs, a tighter writing rule.

The current Clearmind has not been re-tested after these fixes. Run your own: same prompts, skill on and off. Prompts and grids are in this folder.
