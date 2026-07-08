# Instrument with Monocle

A [Claude Code](https://claude.com/claude-code) skill that instruments an agentic system with
**[Monocle](https://github.com/monocle2ai/monocle)** telemetry.

It places the tracing, runs the app, and uses Monocle to **verify whether the instrumentation is
good** — checking that the emitted traces capture the agents, tools, LLM calls, inputs/outputs, and
token usage correctly. **If the instrumentation is missing or incomplete, the skill creates it** so
the traces come out complete.

## Install

In Claude Code, run these two commands:

```
/plugin marketplace add imohammedansari/instrument-with-monocle
/plugin install instrument-with-monocle@monocle
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
