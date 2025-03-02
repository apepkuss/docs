---
sidebar_position: 1
---

# WasmEdge Plug-in System Introduction

While the WasmEdge language SDKs allow registering host functions from a host (wrapping) application, developers should implement the host functions before compilation.

For the other solutions, WasmEdge provides the plug-in architecture to load the plug-in shared library for easier extending of the host functions.

With developing the plug-ins, WasmEdge SDKs in the supported languages can load and register the host functions from the plug-in shared libraries.

In current, developers can follow the guides to implement the plug-ins in [C API (recommended)](develop_plugin_c.md) or [C++](develop_plugin_cpp.md).

## Loadable Plug-in

Loadable plugin is a standalone `.so`/`.dylib`/`.dll` file that WasmEdge can load during runtime environment, and provide modules to be imported.

Please [refer to the plugin example code](https://github.com/WasmEdge/WasmEdge/tree/master/examples/plugin/get-string).

## WasmEdge Currently Released Plug-ins

There are several plug-in releases with the WasmEdge official releases. Please check the following table to check the release status and how to build from source with the plug-ins.

| Plug-in | Rust Crate | Released Platforms | Build Steps |
| --- | --- | --- | --- |
| WasmEdge-Process | [wasmedge_process_interface][] | `manylinux2014 x86_64`, `manylinux2014 aarch64`, and `ubuntu 20.04 x86_64` (since `0.10.0`) | [Build Wtih WasmEdge-Process](../source/plugin/process.md) |
| [WASI-Crypto][] | [wasi-crypto][] | `manylinux2014 x86_64`, `manylinux2014 aarch64`, and `ubuntu 20.04 x86_64` (since `0.10.1`) | [Build With WASI-Crypto](../source/plugin/wasi_crypto.md) |
| [WASI-NN with OpenVINO backend](../../develop/rust/wasinn/openvino.md) | [wasi-nn][] | `ubuntu 20.04 x86_64` (since `0.10.1`) | [Build With WASI-NN](../source/plugin/wasi_nn.md#build-wasmedge-with-wasi-nn-openvino-backend) |
| [WASI-NN with PyTorch backend](../../develop/rust/wasinn/pytorch.md) | [wasi-nn][] | `ubuntu 20.04 x86_64` (since `0.11.1`) | [Build With WASI-NN](../source/plugin/wasi_nn#build-wasmedge-with-wasi-nn-pytorch-backend) |
| [WASI-NN with TensorFlow-Lite backend](../../develop/rust/wasinn/tensorflow_lite.md) | [wasi-nn][] | `manylinux2014 x86_64`, `manylinux2014 aarch64`, and `ubuntu 20.04 x86_64` (since `0.11.2`) | [Build With WASI-NN](../source/plugin/wasi_nn#build-wasmedge-with-wasi-nn-tensorflow-lite-backend) |
| WasmEdge-Image | [wasmedge_tensorflow_interface][] | `manylinux2014 x86_64`, `manylinux2014 aarch64`, `ubuntu 20.04 x86_64`, `darwin x86_64`, and `darwin arm64` (since `0.13.0`) | [Build With WasmEdge-Image](../source/plugin/image.md) |
| WasmEdge-Tensorflow | [wasmedge_tensorflow_interface][] | `manylinux2014 x86_64`, `manylinux2014 aarch64`, `ubuntu 20.04 x86_64`, `darwin x86_64`, and `darwin arm64` (since `0.13.0`) | [Build With WasmEdge-Tensorflow](../source/plugin/tensorflow.md) |
| WasmEdge-TensorflowLite | [wasmedge_tensorflow_interface][] | `manylinux2014 x86_64`, `manylinux2014 aarch64`, `ubuntu 20.04 x86_64`, `darwin x86_64`, and `darwin arm64` (since `0.13.0`) | [Build With WasmEdge-TensorflowLite](../source/plugin/tensorflowlite.md) |

<!-- prettier-ignore -->
:::note
Due to the `OpenVINO` dependency, we only release the WASI-NN plug-in for the `OpenVINO` backend on `Ubuntu 20.04 x86_64` now. We'll work with `manylinux2014` versions in the future.
:::

[wasmedge_process_interface]: https://crates.io/crates/wasmedge_process_interface
[wasmedge_tensorflow_interface]: https://crates.io/crates/wasmedge_tensorflow_interface
[wasi-crypto]: https://crates.io/crates/wasi-crypto
[wasi-nn]: https://crates.io/crates/wasi-nn
