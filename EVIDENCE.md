# Evidence and gaps

## Preserved original description

See original-project.json for the complete unchanged local portfolio entry. Source: ../.. / portfolio/src/default-content.json (local inventory).

## Available evidence

Repository README and selected source files inspected; execution and deployment not verified.

Repository inspected: [DeepFlow-HPC](https://github.com/ashupsingh/DeepFlow-HPC)

Pinned tree/commit: `268be20dd0d0f36d66b7fac17de5a8b21bfd078d`. Full file inventory: [saved index](resources/DeepFlow-HPC-file-index.json). README: [saved copy](resources/DeepFlow-HPC-repository-readme.txt).

Selected source files saved for review:
- [reference.py](https://github.com/ashupsingh/DeepFlow-HPC/blob/268be20dd0d0f36d66b7fac17de5a8b21bfd078d/reference.py) — [local copy](recovered_original/reference.py)
- [test_cuda.py](https://github.com/ashupsingh/DeepFlow-HPC/blob/268be20dd0d0f36d66b7fac17de5a8b21bfd078d/test_cuda.py) — [local copy](recovered_original/test_cuda.py)
- [validate.py](https://github.com/ashupsingh/DeepFlow-HPC/blob/268be20dd0d0f36d66b7fac17de5a8b21bfd078d/validate.py) — [local copy](recovered_original/validate.py)

## Evidence still needed

- Your precise contribution and approximate date.
- Original photo, dated presentation, circuit diagram or institutional submission if recoverable.
- Raw measurements and test conditions for any quantitative claim.
- Permission and attribution for collaborators or borrowed designs.

Do not use stock images as prototype photographs. Newly drawn diagrams should say reconstructed architecture. No result, award or deployment is independently proven by a general technical reference.

## Findings from inspected source

- `reference.py` contains diffusion iterations, a pressure projection routine and semi-Lagrangian-style backtracing with bilinear interpolation. Its visible configuration uses an 800 x 800 grid and 100 steps. These are code settings, not measured performance results.
- The tree includes `exp_njit.py`, `exp_njit_parallel.py`, `ray_code.py`, `test_cuda.py`, `validate.py` and a presentation file. The existence of those files is established; not every file was reviewed or executed.
- `validate.py` contains CUDA kernels and shared-memory usage. In the inspected pressure kernel, pressure initialization and neighbor reads appear in one launch, with block-level synchronization. Cross-block ordering and the intended pressure iteration scheme need review before correctness claims.
- `test_cuda.py` should not be assumed self-contained simply from its filename: verify all referenced kernels and compare its initial conditions against the reference.
- No speedup is calculated here. CUDA execution, GPU availability, dependency compatibility and presentation results were not validated.

## Useful next step without rebuilding

Explain one CPU stencil, one GPU indexing scheme, and the difference between kernel timing and end-to-end timing. Recover the existing presentation and original benchmark logs before quoting any result or competition award as externally verified.

## Local recovery and reconstruction update

See README.md and VALIDATION.md for the current local files and checks. Newly generated code, demo outputs and wiring are dated reconstructions; they support a new reproducible version, not a claim that old source files or measurements were recovered.
