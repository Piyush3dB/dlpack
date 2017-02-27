# DLPack

RFC for common tensor and operator guidelines in deep learning systems.
Started by [this issue](https://github.com/dmlc/mxnet/issues/4735)

Currently each DL framework have their own internal tensor data structure, and operator interface, which are similar but not compatible. The major goal of thie RFC is to come up with a minimum tensor data structure and a set of operator interfaces(or guidelines) that can be shared across frameworks.

This enables:
- Easier sharing of operators between deep learning frameworks.
- Easier wrapping of vendor level operator implementations, allowing collaboration when introducing new devices/ops.
- Quick swapping of backend implementations, like different version of BLAS
- For final users, this could bring more operators, and possiblity of mixing usage between frameworks (e.g. pass a Torch Tensor into Caffe, use MXNet scheduler to schedule Torch Tensors)

We do not intend to implement of Tensor and Ops, but instead use this as common interface to reuse tensor and ops across frameworks.
