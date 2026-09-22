# Compute datapaths

## Start here: current investigation packet

Read the [starting guide](docs/START-HERE.md) for the current diagram, source evidence, parallel investigations and first useful outputs.

Explore and develop the arithmetic capabilities that turn the accelerator’s intended computations into effective hardware. The team seeks a sound balance among numerical behavior, throughput, latency, area and implementation complexity, using approaches its members choose.

## Read the charter

- [CHARTER.md](CHARTER.md): purpose, responsibilities, boundaries, member autonomy and collaboration.
- [OBJECTIVES.md](OBJECTIVES.md): high-level outcomes that members can choose how to advance.
- [SETUP.md](SETUP.md): optional technical setup and the scope of any existing example.

## Choosing a contribution

Members choose their work in conversation with the charter and their interests.
A contribution can be a research question, a design study, an experiment, an
implementation, a useful explanation or teaching material. Leads help connect
people, questions and evidence. Shared interfaces and commitments are discussed
with the teams that depend on them.

The scaffold supplies places for that work. It does not specify a backlog,
required first project, milestone sequence or personal assignment.

## Repository structure

| Location | Purpose |
|---|---|
| [docs/](docs/README.md) | Design explanations, proposals, reviews, decisions and learning material. Let the content evolve with the team’s questions; link research and experiment evidence where useful. |
| [research/](research/README.md) | Literature notes, surveys, analytical studies and comparisons relevant to the charter. Explain the question, sources, interpretation and remaining uncertainty in a form that suits the work. |
| [experiments/](experiments/README.md) | Exploratory studies, prototypes and experiment narratives. Make the question and interpretation understandable; preserve the context needed to revisit a result. These artifacts need not be production implementations. |
| [rtl/](rtl/README.md) | Arithmetic and datapath implementations developed through the team’s chosen work. |
| [tb/](tb/README.md) | Local compute testbenches and behavioral checks associated with implemented designs. |

The team may extend this structure as useful. Existing example entry points stay
in their current locations, described in [SETUP.md](SETUP.md).

## Current material

A signed INT8 MAC with an INT32 accumulator is present, with model-based and directed checking through the verification component. Its original MIT notice is retained in [LICENSE](LICENSE).

Existing code is optional material for learning or experimentation. Its behavior
and tests describe that example and do not select the team’s future design.
Reading or contributing to the charter, research and design documentation needs
no tool installation.

This is the [SiliconBadgers/rtl-compute](https://github.com/SiliconBadgers/rtl-compute) team repository.
The [organization guide](https://github.com/SiliconBadgers/accelerator/blob/main/docs/TEAM_GUIDE.md)
and [repository map](https://github.com/SiliconBadgers/accelerator/blob/main/docs/REPOSITORIES.md)
explain how the teams connect.
