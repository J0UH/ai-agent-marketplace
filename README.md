[← All systems](https://github.com/J0UH) · [Agentic systems](https://github.com/J0UH/agentic-systems)

<p align="center">
  <img src="assets/hero.webp" alt="Seven distinct modular units occupy separate bays with one bay illuminated" width="100%" />
</p>

# AI agent marketplace

A marketplace for agents is not a grid of prompts. Each agent needs a clear job, known tools, understandable limits, a way to evaluate quality, and an operating model that survives more than one impressive demo.

## The engineering problem

Specialised agents vary in risk, latency, cost, and evidence needs. The platform had to make those differences visible while giving users a consistent way to configure and run them.


## Foundation and adaptation

The experimentation studio is adapted from Microsoft's [AutoGen Studio](https://github.com/microsoft/autogen). The agent catalog and product operating model sit outside that upstream runtime, so the two bodies of work remain clearly separated.

## What the system covers

- Agent discovery and configuration
- Tool and permission declarations
- Run state and output handling
- Evaluation and review workflows
- Multi-agent experimentation
- Product and operator interfaces

## System shape

```mermaid
flowchart TD
accTitle: AI agent marketplace
accDescr: An agent configuration cannot run until permissions and expected cost are accepted. Results are evaluated against a versioned configuration and either retained or sent back for revision.
    catalog["Agent catalog"] --> config["Run configuration"]
    config --> gate{"Permission and cost?"}
    gate -->|Accepted| runtime["Agent runtime"]
    gate -->|Rejected| config
    runtime --> tools["Bounded tools"]
    tools --> evaluate{"Outcome meets test?"}
    evaluate -->|No| config
    evaluate -->|Yes| history["Versioned result"]
```

## Build notes

- Describe the job and stop condition before the persona.
- Expose permissions and cost before a run starts.
- Keep evaluation data attached to the version that produced it.

<sub>Public overview only. Source code, customer data, credentials, and private operating details are not included.</sub>

## Talk through a similar problem

Working on something similar? [Tell me about it](mailto:ju@jomena.group?subject=AI%20agent%20marketplace).
