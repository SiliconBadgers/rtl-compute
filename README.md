# Compute research: two independent proposals

Compute1 and Compute2 each investigate the full compute-unit design question and produce their own proposal. They are not splitting arithmetic versus stateful work, and neither team depends on or coordinates its proposal with the other.

## Start here

1. Read [the current assignment and artifact locations](docs/START-HERE.md).
2. Work on a branch and open a PR for `@abhinavnandwani` using
   [CONTRIBUTING.md](CONTRIBUTING.md). Main requires a code-owner approval;
   admins can bypass.

## Current issues

- [Research the complete compute-unit design](https://github.com/SiliconBadgers/rtl-compute/issues/2)

## Repository structure

| Location | Purpose |
|---|---|
| [research/compute1/](research/compute1/README.md) | Compute1's complete independent investigation and proposal for rtl-compute#2. Cover the full operation set; divide tasks within Compute1. |
| [research/compute2/](research/compute2/README.md) | Compute2's complete independent investigation and proposal for rtl-compute#2. Cover the full operation set; divide tasks within Compute2. |

## Current material and scope

The signed MAC is a runnable example. The four functional boxes in Architecture do not commit the project to four engines. No final unit allocation is established here.

[Shared diagram](https://github.com/SiliconBadgers/architecture/blob/main/docs/accelerator-diagram.md) · [Software evidence](https://github.com/SiliconBadgers/software/tree/main/experiments/llama-cpp/2026-09-22)

[CHARTER.md](CHARTER.md) and [OBJECTIVES.md](OBJECTIVES.md) describe the
longer-term purpose. Current issues and the starting guide specify the work
assigned now. [SETUP.md](SETUP.md) describes existing example commands and scope.
