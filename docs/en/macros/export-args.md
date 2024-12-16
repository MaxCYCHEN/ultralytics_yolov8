| Argument    | Type             | Default         | Description                                                                                                                                                      |
| ----------- | ---------------- | --------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `format`    | `str`            | `'torchscript'` | Target format for the exported model, such as `'onnx'`, `'torchscript'`, `'tensorflow'`, or others, defining compatibility with various deployment environments. |
| `imgsz`     | `int` or `tuple` | `640`           | Desired image size for the model input. Can be an integer for square images or a tuple `(height, width)` for specific dimensions.                                |
| `keras`     | `bool`           | `False`         | Enables export to Keras format for TensorFlow SavedModel, providing compatibility with TensorFlow serving and APIs.                                              |
| `optimize`  | `bool`           | `False`         | Applies optimization for mobile devices when exporting to TorchScript, potentially reducing model size and improving performance.                                |
| `half`      | `bool`           | `False`         | Enables FP16 (half-precision) quantization, reducing model size and potentially speeding up inference on supported hardware.                                     |
| `int8`      | `bool`           | `False`         | Activates INT8 quantization, further compressing the model and speeding up inference with minimal accuracy loss, primarily for edge devices.                     |
| `dynamic`   | `bool`           | `False`         | Allows dynamic input sizes for ONNX and TensorRT exports, enhancing flexibility in handling varying image dimensions.                                            |
| `simplify`  | `bool`           | `True`          | Simplifies the model graph for ONNX exports with `onnxslim`, potentially improving performance and compatibility.                                                |
| `opset`     | `int`            | `None`          | Specifies the ONNX opset version for compatibility with different ONNX parsers and runtimes. If not set, uses the latest supported version.                      |
| `workspace` | `float`          | `4.0`           | Sets the maximum workspace size in GiB for TensorRT optimizations, balancing memory usage and performance.                                                       |
| `nms`       | `bool`           | `False`         | Adds Non-Maximum Suppression (NMS) to the CoreML export, essential for accurate and efficient detection post-processing.                                         |
| `separate_outputs`    | `bool` | `False`         | Separate outputs for better quantization performance.                                                                                                            |
| `export_hw_optimized` | `bool` | `False`         | Optimize c2f block for faster inference on some hardware.                                                                                                        |
| `batch`     | `int`            | `1`             | Specifies export model batch inference size or the max number of images the exported model will process concurrently in `predict` mode.                          |