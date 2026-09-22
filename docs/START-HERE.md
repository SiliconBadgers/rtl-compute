# Compute starting material

September 22, 2026. Initial investigations for team discussion; no personal assignments or deadlines.

## Shared starting points

- [Editable architecture diagram](https://github.com/SiliconBadgers/architecture/blob/main/docs/accelerator-diagram.md) and [candidate boundaries](https://github.com/SiliconBadgers/architecture/blob/main/contracts/accelerator-boundaries.md).
- [Workload cases and source shapes](https://github.com/SiliconBadgers/architecture/blob/main/docs/workload-cases.md).
- [Measured llama.cpp report](https://github.com/SiliconBadgers/software/blob/main/experiments/llama-cpp/2026-09-22/REPORT.md) and [reproduction procedure](https://github.com/SiliconBadgers/software/blob/main/experiments/llama-cpp/2026-09-22/README.md).
- [Parallel team investigations](https://github.com/SiliconBadgers/planning/blob/main/docs/team-start.md).

The diagram and engine split are proposals. Start from available shapes and
reference cases now; use explicit parameters or stubs where decisions remain
open. Software's broader profiling study is not a prerequisite. Preserve the
source revision, assumptions, commands and limits of each result. Members and
leads can choose a different investigation that resolves a relevant uncertainty.


## Compute 1: reusable arithmetic and dataflow

Start with the [matrix cases CSV](https://github.com/SiliconBadgers/architecture/blob/main/docs/matrix-cases.csv).
Compare a small number of tile/lane organizations for decode and prefill. Include
MLP up/down, attention projections, tiny gate projections and the large tied
embedding/output matrix. Report lane utilization, tail handling, cycles under
stated assumptions, operand/partial-sum storage and bytes demanded per cycle.
Prototype or synthesize a representative kernel when that resolves a major
uncertainty; do not choose arithmetic widths from the old INT8 MAC example.

First useful artifact: `experiments/<study>/` containing the candidate datapath
sketch, parameterized estimates, commands and a comparison table. Distinguish
logical GGUF bytes from the proposed hardware format and actual bus traffic.

## Compute 2: stateful and non-matrix execution

Map attention, DeltaNet, convolution, norm, RoPE, activation and gather/copy work
to arithmetic primitives and state lifetimes. Compare reuse of Compute 1's
arithmetic with a specialized path. Show QK/softmax/AV sequencing, recurrent-state
updates, convolution history and where intermediate results move.

First useful artifact: an operation/resource map and local control/datapath
Mermaid sketch, plus representative numerical/state cases shared with
Verification. Low measured CPU convolution time does not remove the need for
correct convolution or establish its accelerator cost.

## Compare together

These investigations share this repository; they do not imply fixed permanent
engine ownership. Provide a candidate partition showing what is shared, what is
local and the scheduling/storage cost. Model backpressure, dimension tails,
partial-sum preservation across K tiles and prefill-to-decode state continuity.
A useful comparison includes at least one unfavorable shape, not only a square
matrix with perfect lane utilization.

## Existing executable example

The signed INT8 MAC is available for learning and reference checks. With sibling
checkouts named `software`, `architecture` and `verification`, run:

```sh
make doctor
make test MODELS_ROOT=../software
```

This requires Python 3.11+ and Icarus Verilog (`iverilog`, `vvp`). It validates the
small MAC example only; it is not an INT4/BF16 engine or full-model test. The
explicit `MODELS_ROOT` argument accommodates the Software repository rename.
