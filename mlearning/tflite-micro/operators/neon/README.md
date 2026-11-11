# TensorFlow Lite Micro ARM NEON Kernels (`mlearning/tflite-micro/operators/neon`)

## Overview
Implements ARM NEON SIMD-accelerated integer (`int8`/`q7`/`q15`) neural network operator kernels for TensorFlow Lite Micro and CMSIS-NN on NuttX.

## Interface
- `[arm_convolve_s8.c:arm_convolve_s8]`: Basic `s8` 2D convolution kernel with `im2col` workspace expansion and per-channel requantization.
- `[arm_nn_mat_mult_kernel_s8_s16.c:arm_nn_mat_mult_kernel_s8_s16]`: Matrix-multiplication kernel for `s8` weights and `s16` input activations using NEON dot-product/multiply-accumulate intrinsics.
- `[arm_q7_to_q15_with_offset.c:arm_q7_to_q15_with_offset]`: Converts 8-bit signed `q7` vectors to 16-bit signed `q15` vectors with an additive input offset.
- `[arm_elementwise_add_s8.c:arm_elementwise_add_s8]`: Elementwise addition of two `s8` tensors with input rescaling and output activation clamping.

## Invariants
- `[arm_convolve_s8.c:arm_convolve_s8]`: Returns `ARM_CMSIS_NN_ARG_ERROR` if `ctx->buf == NULL`; clamps output values to `[conv_params->activation.min, conv_params->activation.max]`.
- `[arm_nn_mat_mult_kernel_s8_s16.c:arm_nn_mat_mult_kernel_s8_s16]`: Clamps requantized output values to `[activation_min, activation_max]`.
- `[arm_elementwise_add_s8.c:arm_requantize_neon]`: Requires `shift <= 0` and clamps requantized elementwise sums to `[out_activation_min, out_activation_max]`.

## Side Effects
- `[arm_convolve_s8.c:arm_convolve_s8]`: Mutates caller-supplied scratch buffer `ctx->buf` (`im2col` workspace) and writes convolved `int8_t` results to `output_data`.
- `[arm_nn_mat_mult_kernel_s8_s16.c:arm_nn_mat_mult_kernel_s8_s16]`, `[arm_q7_to_q15_with_offset.c:arm_q7_to_q15_with_offset]`, and `[arm_elementwise_add_s8.c:arm_elementwise_add_s8]`: Write transformed tensor outputs directly into caller-provided destination buffers.

## Verification
- Run: `make test`
