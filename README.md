# Monocle Auto-Instrument

A [Claude Code](https://claude.com/claude-code) skill that instruments an agentic system with
**[Monocle](https://github.com/monocle2ai/monocle)** telemetry.

It places the tracing, runs the app, and uses Monocle to **verify whether the instrumentation is
good** — checking that the emitted traces capture the agents, tools, LLM calls, inputs/outputs, and
token usage correctly. **If the instrumentation is missing or incomplete, the skill creates it** so
the traces come out complete.

## Install

Two separate steps in Claude Code — run them one at a time, not together.

**1. Add the marketplace:**

```
/plugin marketplace add imohammedansari/monocle-auto-instrument
```

> If Claude Code opens an "Add Marketplace / Enter marketplace source" prompt, type **only**
> `imohammedansari/monocle-auto-instrument` and press Enter — nothing else.

**2. Install the plugin** (run this as a new command, after step 1 finishes):

```
/plugin install monocle-auto-instrument@monocle
```

## Use

Open Claude Code in the Python agentic project you want to trace, then ask:

```
instrument this with monocle
```

The skill detects the framework, adds the telemetry, runs a representative question, and reports a
graded trace — telling you whether the instrumentation is good and fixing it if it isn't.

## Framework support

- **Supported frameworks** — the skill already adds and verifies instrumentation for the agent
  frameworks Monocle supports today (e.g. LangGraph, CrewAI, LlamaIndex, OpenAI Agents SDK, Strands).
- **Custom frameworks** — support for instrumenting custom / not-yet-supported agent frameworks from
  scratch is on the roadmap and not available yet.
