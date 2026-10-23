# DeepFlow-HPC: methodology

Status: researched reconstruction / proposed evaluation, prepared 23 October 2026. Not a recovered lab notebook.

## Existing account

Built using Python, Ray, Numba JIT, and CUDA for parallel processing. Won the Deep-flow HPC competition at IIT Guwahati in February 2025.

The account above comes from the existing portfolio and is not independent verification. Listed stack: Python, CUDA, Numba, Ray. Exact components and versions still need confirmation.

## System architecture

Initial velocity/dye fields -> diffusion -> pressure projection -> advection -> numerical comparison

## Proposed engineering workflow

1. Pin a commit and define one grid, timestep, viscosity and initial condition shared by every implementation.
2. Compare CPU and GPU arrays with stated tolerances and divergence checks before timing.
3. Audit synchronization, boundary updates and stencil dependencies; block synchronization is not global synchronization.
4. Warm up compilation, synchronize GPU timing, and report transfers separately from kernel time.

## Evaluation plan, not results

Record: L2/max error; velocity divergence; wall time; transfer time; grid and hardware. Use explicit units, test conditions, a baseline where relevant, repeated observations and a timestamped log. Report failure cases alongside successes. No numerical result is available from this reconstruction.

## Limitations and claim boundaries

Saved source exists but was not executed here. Code presence is not numerical validation or a measured speedup.

## Design questions for an interview

- Explain the input, decision and output paths in the architecture above.
- What concrete fault would invalidate the output, and how would you detect it?
- Which design decision did you personally make, and what evidence do you retain?
- Which part of this proposed workflow differs from what you actually built?

## Research basis

[NVIDIA CUDA best practices](https://docs.nvidia.com/cuda/cuda-c-best-practices-guide/) — consulted 23 October 2026. This source supports the underlying engineering topic, not the historical implementation. Workflow and evaluation proposals above are original analysis for this project.
