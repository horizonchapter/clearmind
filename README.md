# Clearmind

[![License: MIT](https://img.shields.io/badge/license-MIT-black.svg)](LICENSE)
[![Agent Skills](https://img.shields.io/badge/format-Agent%20Skills-black.svg)](https://agentskills.io)

Clearmind is a skill that changes how an AI agent works, not what it knows. The agent reads the whole request, says first what is missing, refuses to make things up, gives a real opinion, and answers in fewer words.

It works with Claude (apps, Claude Code, Cowork) and with any agent that reads `SKILL.md` files. One folder, no code to run.

## Before and after

A user dictates a long voice message about launching a mug shop for Christmas. Somewhere in the middle: "I'll copy the designs of the best-selling shop and just change the colors, smart right? I know you usually agree with me." The message also mentions a screenshot that was never attached.

Without the skill, the assistant gives a solid general plan, keeps "your mom can pack the orders" as a backup although the printer ships directly, and never mentions the missing screenshot until the second paragraph.

With Clearmind (excerpt, shortened):

> The supplier link and the design screenshot did not come through, I only have your text. Send them again.
>
> Copying the best-sellers with new colors: no. That is still a copy, and the usual outcome is removed listings and a suspended shop. Keep the style, draw your own designs.
>
> At 9 € a mug you lose money on every sale: Etsy fees plus a print-on-demand mug delivered in France already cost more than that.

Same model, same message. The difference is discipline.

## What it does

- Reads every word and every image, including voice-dictated text with misheard words, and treats CAPITALS or repeated words as hard constraints.
- Puts missing things first: attachments that never arrived, files it could not open, inputs it needs.
- Never invents facts, sources, results, past conversations or "I checked". It labels what it has not verified and verifies when a tool allows.
- Gives a verdict on plans and ideas, keeps it when the user pushes back without a new fact, and adds a nuance only when it changes what the user should do.
- Answers the question behind the question. "Are my three agents running?" gets "No, the third one crashed at 20:30."
- Keeps unanswered questions and parked topics visible until they are settled, and brings side topics back once the current task is done.
- Checks hidden prerequisites (hardware, accounts, age, taxes, approval delays) and takes the cautious assumption when a missing fact changes legal or money advice.
- Writes like a sharp colleague: no "it's not X, it's Y", no emojis, no filler, every sentence carrying information.
- Hands over cleanly: when a long chat starts losing details it says so and writes a self-contained handoff for the next session.

It keeps the agent's role. A coding agent stays a coding agent, a writer stays a writer.

## Install

**Claude apps** (Free, Pro, Max, Team, Enterprise)
1. Settings > Capabilities: turn on code execution and file creation.
2. Zip the `clearmind/` folder, then Customize > Skills > upload it and switch it on.

**Claude Code**
```bash
git clone https://github.com/horizonchapter/clearmind.git
cp -r clearmind/clearmind ~/.claude/skills/clearmind
```

**Other agents**: copy `clearmind/` into the agent's skills directory, or paste `clearmind/SKILL.md` into its system prompt.

## Keep it on

A skill loads when the agent thinks it is relevant. To have Clearmind on every reply, add one line where your agent reads standing instructions.

Claude apps, personal preferences:
```
Load the clearmind skill at the start of every conversation and apply it to every reply.
```

Claude Code, `CLAUDE.md` or `AGENTS.md`:
```
Load the clearmind skill at session start and after each compaction. Apply it to every reply.
```

Sub-agents do not inherit skills from their parent: give each one the same line.

## With other skills

Clearmind decides the substance of a reply. Style skills such as [Caveman](https://github.com/JuliusBrussee/caveman) decide the wording and can run alongside it. Clearmind already writes tight on its own, so a style skill is optional.

## Evidence

Two blind tests on claude.ai, same model with and without the skill, graded by judges who did not know which answer was which.

| Test | Without skill | With Clearmind |
|---|---|---|
| Long dictated project message, 38 traps | 28.5 to 29 | 35 to 36 |
| Three-turn app project, 34 points | 26.5 to 27.5 | 29.5 to 30.5 |

On simple factual questions there was no difference, which is expected: the skill helps when a request is long, messy, risky or easy to get subtly wrong. One run per version, so treat these as signals and run your own. Prompts, grading grids and notes are in [`evals/`](evals/RESULTS.md).

## What is inside

```
clearmind/
  SKILL.md                    the rules, about 3,100 words
  references/
    ai-patterns.md            AI phrasings to remove, English and French
    thinking-tools.md         thinking methods and how to pick an expert standard
    relais-handoff.md         handoff template
    sources.md                evidence and citation rules
    examples.md               worked examples
evals/                        test prompts, grids, results
```

The references load only when needed, so the cost per conversation stays close to the size of `SKILL.md`.

## Limits

A skill cannot add knowledge, tools or memory the platform does not provide. It makes the agent more careful and more honest about what it knows. It will not make a model know what it does not know.

## License

MIT. Made by [Horizon Chapter](https://github.com/horizonchapter).
