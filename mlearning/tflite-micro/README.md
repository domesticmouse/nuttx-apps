# TensorFlow Lite Micro (`mlearning/tflite-micro`)

## Overview
Integrates TensorFlow Lite for Microcontrollers (`CONFIG_TFLITEMICRO`) into NuttX, providing `syslog`-backed logging hooks (`tflm_syslog.cc`), a command-line model evaluation and AOT code generation utility (`tflm_tool.cc`), int8 operator patches, and architecture-accelerated operator kernels.

## Interface
- `[tflm_syslog.cc:VMicroPrintf]` / `[tflm_syslog.cc:MicroPrintf]` / `[tflm_syslog.cc:MicroSnprintf]` / `[tflm_syslog.cc:MicroVsnprintf]`: NuttX logging and formatting hooks for TensorFlow Lite Micro diagnostics.
- `[tflm_tool.cc:main]`: CLI tool (`tflm`) to load `.tflite` models, inject test inputs, benchmark inference latency, and optionally emit compiled C++ model sources.
- `[Kconfig:CONFIG_TFLITEMICRO]`, `[Kconfig:CONFIG_TFLITEMICRO_TOOL]`, `[Kconfig:CONFIG_TFLITEMICRO_SYSLOG]`: Build and tool configuration flags.
- Subdirectories:
  - `operators`: [./operators/README.md](./operators/README.md) - Hardware-accelerated operator kernels (ARM NEON).

## Invariants
- `[Kconfig:CONFIG_TFLITEMICRO]`: Depends on `SYSTEM_FLATBUFFERS && MATH_GEMMLOWP && MATH_KISSFFT && MATH_RUY`.
- `[tflm_tool.cc:TFLM_MAX_OPS]`: Models executed by `tflm_tool` may register at most 32 distinct operators in `MicroMutableOpResolver`.
- `[tflm_tool.cc:TFLM_MAX_INPUTS]`: At most 4 input arguments (`-d`/`-x`) can be specified per run.
- `[tflm_tool.cc:main]`: Requires `model_path != nullptr`, `code_path != nullptr` when `-C` is set, `arena_size > 0`, `runs > 0`, valid FlatBuffer schema version `TFLITE_SCHEMA_VERSION`, and at least one subgraph.
- `[tflm_tool.cc:load_input_file]`: Input binary file byte size must match `tensor->bytes` (`load_input_values` requires either 1 broadcast value or exact tensor element count).

## Side Effects
- `[tflm_syslog.cc:VMicroPrintf]` and `[tflm_syslog.cc:MicroPrintf]`: Emit formatted diagnostic messages via `vsyslog` at `CONFIG_TFLITEMICRO_SYSLOG_LEVEL`.
- `[tflm_tool.cc:main]`: Allocates heap buffers for the model, tensor arena, resolver, profiler, and interpreter; reads model and input files via `std::ifstream`; measures monotonic time via `clock_gettime(CLOCK_MONOTONIC)`; and writes compiled C++ code via `std::ofstream` when `-C` is used.
- `[Makefile:tflite-micro.zip]`: Downloads the `tflite-micro` source archive via `curl`, unpacks it, and applies local quantization/operator patches during build context setup.

## Verification
- Run: `make test`
