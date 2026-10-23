# Validation record

Checked 23 October 2026.

- Original source snapshot exported from the recovered repository. See PUBLICATION.md for publication-only changes.
- Dependencies were not installed and the recovered application/simulation was not executed. Numerical correctness, deployment behavior and benchmarks are not verified.

Compilation checks syntax, board APIs and linking. It does not verify wiring, voltages, sensor conditioning, actuator behavior or timings on hardware. Python checks exercise a separate logic model; they do not execute the compiled sketch. No physical hardware, clinical test, road trial or historical experiment was performed.

Exact library versions are recorded in the local `toolchain-versions.txt`.

## New bench evidence to collect

Record controller and module part numbers, firmware commit, power rails, calibration method and timestamp. Capture a normal case, an invalid/disconnected input, restart behavior, and timing boundaries where relevant. Save raw data and a real build photograph alongside the new test report. For analytical projects, retain input data, units and independent reference calculations.
