# Regex NFA Visualizer

Compile a regular expression into a Thompson NFA, draw the state machine, and step a test string through it watching the active state set move.

**Live:** <https://regex-visualizer.slippylabs.com/>

## What it does

- Compile a regular expression into a Thompson NFA and see the state machine drawn out.
- Step a test string through it one character at a time, watching the active state set move.
- Built-in examples for alternation, quantifiers, character classes and bounded repetition.

## How it works

The regex is parsed to an AST and compiled with **Thompson's construction** into an NFA with epsilon transitions, then simulated as a *set* of active states — which is what makes the animation honest about backtracking-free matching rather than pretending a regex is a single cursor.

Every verdict the visualiser reaches is cross-checked against the browser's own `RegExp` engine. If the NFA and the native engine ever disagree on whether a string matches, that is a bug in the visualiser, and the check is there to catch it.

## Run it locally

A static site. No build step, no package manager, no dependencies:

```
git clone git@github.com:slippylabs/regex-visualizer.slippylabs.com.git
cd regex-visualizer.slippylabs.com
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

---

Part of [Slippy Labs](https://slippylabs.com). Every tool is indexed at
[projects.slippylabs.com](https://projects.slippylabs.com).
