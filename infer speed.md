# device

- cpu: 10700
- ram: 32G
- gpu: 1080 Ti

# 注意点

1. > 注意:
   >
   > `onnxruntime` 和 `onnxruntime-gpu` 不要同时安装，否则使用 `gpu` 推理时速度会很慢，如果同时安装了2个包，要全部卸载，再安装 'onnxruntime-gpu' 才能使用gpu推理，否则gpu速度会很慢

1. 注意：openvino没法使用cuda，但是使用 --device 0 会提高推理速度

   # table

|              | n    | s     | m     | l     | x     |
| ------------ | ---- | ----- | ----- | ----- | ----- |
| pytorch-gpu  | 8.3  | 9.2   | 13.8  | 20.1  | 33.2  |
| trt-fp32     | 2.7  | 4.8   | 8.1   | 13.8  | 24.0  |
| trt-fp16     |      |       |       |       |       |
| ort-gpu      | 10.9 | 13.4  | 19.0  | 26.2  | 42.1  |
|              |      |       |       |       |       |
| pytorch-cpu  | 62.8 | 126.0 | 265.8 | 477.5 | 807.3 |
| ort-cpu      | 27.3 | 69.7  | 170.5 | 331.9 | 567.9 |
| openvino-gpu | 18.9 | 38.7  | 98.0  | 214.8 | 384.6 |
| openvino-cpu | 19.7 | 51.3  | 138.7 | 275.2 | 448.6 |
|              |      |       |       |       |       |

# n

```
pytorch-gpu: 	Speed: 0.3ms pre-process, 8.3ms inference, 1.0ms NMS per image at shape (1, 3, 640, 640)
pytorch-cpu: 	Speed: 0.6ms pre-process, 62.8ms inference, 1.6ms NMS per image at shape (1, 3, 640, 640)

trt-fp32:     	Speed: 7.4ms pre-process, 2.7ms inference, 1.0ms NMS per image at shape (1, 3, 640, 640)

ort-gpu: 	 	Speed: 7.4ms pre-process, 10.9ms inference, 1.0ms NMS per image at shape (1, 3, 640, 640)
ort-cpu: 	 	Speed: 0.8ms pre-process, 27.3ms inference, 1.5ms NMS per image at shape (1, 3, 640, 640)

# 注意：openvino没法使用cuda，但是使用 --device 0 会提高推理速度
openvino-gpu:	Speed: 7.2ms pre-process, 18.9ms inference, 1.2ms NMS per image at shape (1, 3, 640, 640)
openvino-cpu:	Speed: 0.7ms pre-process, 19.7ms inference, 1.4ms NMS per image at shape (1, 3, 640, 640)
```

# s

```
pytorch-gpu: 	Speed: 0.4ms pre-process, 9.2ms inference, 1.0ms NMS per image at shape (1, 3, 640, 640)
pytorch-cpu: 	Speed: 0.7ms pre-process, 126.0ms inference, 1.7ms NMS per image at shape (1, 3, 640, 640)

trt-fp32:     	Speed: 7.3ms pre-process, 4.8ms inference, 1.0ms NMS per image at shape (1, 3, 640, 640)

ort-gpu: 	 	Speed: 7.3ms pre-process, 13.4ms inference, 1.1ms NMS per image at shape (1, 3, 640, 640)
ort-cpu: 	 	Speed: 0.7ms pre-process, 69.7ms inference, 1.6ms NMS per image at shape (1, 3, 640, 640)

# 注意：openvino没法使用cuda，但是使用 --device 0 会提高推理速度
openvino-gpu:	Speed: 7.2ms pre-process, 38.7ms inference, 1.2ms NMS per image at shape (1, 3, 640, 640)
openvino-cpu:	Speed: 0.8ms pre-process, 51.3ms inference, 1.5ms NMS per image at shape (1, 3, 640, 640)
```

# m

```
pytorch-gpu: 	Speed: 0.3ms pre-process, 13.8ms inference, 1.0ms NMS per image at shape (1, 3, 640, 640)
pytorch-cpu: 	Speed: 0.7ms pre-process, 265.8ms inference, 1.8ms NMS per image at shape (1, 3, 640, 640)

trt-fp32:     	Speed: 7.3ms pre-process, 8.1ms inference, 1.0ms NMS per image at shape (1, 3, 640, 640)

ort-gpu: 	 	Speed: 7.3ms pre-process, 19.0ms inference, 1.1ms NMS per image at shape (1, 3, 640, 640)
ort-cpu: 	 	Speed: 0.8ms pre-process, 170.5ms inference, 1.6ms NMS per image at shape (1, 3, 640, 640)

# 注意：openvino没法使用cuda，但是使用 --device 0 会提高推理速度
openvino-gpu:	Speed: 7.6ms pre-process, 98.0ms inference, 1.6ms NMS per image at shape (1, 3, 640, 640)
openvino-cpu:	Speed: 1.0ms pre-process, 138.7ms inference, 1.5ms NMS per image at shape (1, 3, 640, 640)
```

# l

```
pytorch-gpu: 	Speed: 0.4ms pre-process, 20.1ms inference, 1.1ms NMS per image at shape (1, 3, 640, 640)
pytorch-cpu: 	Speed: 0.6ms pre-process, 477.5ms inference, 1.8ms NMS per image at shape (1, 3, 640, 640)

trt-fp32:     	Speed: 7.2ms pre-process, 13.8ms inference, 1.1ms NMS per image at shape (1, 3, 640, 640)

ort-gpu: 	 	Speed: 7.5ms pre-process, 26.2ms inference, 1.1ms NMS per image at shape (1, 3, 640, 640)
ort-cpu: 	 	Speed: 1.0ms pre-process, 331.9ms inference, 1.6ms NMS per image at shape (1, 3, 640, 640)

# 注意：openvino没法使用cuda，但是使用 --device 0 会提高推理速度
openvino-gpu:	Speed: 8.2ms pre-process, 214.8ms inference, 2.6ms NMS per image at shape (1, 3, 640, 640)
openvino-cpu:	Speed: 0.8ms pre-process, 275.2ms inference, 1.4ms NMS per image at shape (1, 3, 640, 640)
```

# x

```
pytorch-gpu: 	Speed: 0.4ms pre-process, 33.2ms inference, 1.1ms NMS per image at shape (1, 3, 640, 640)
pytorch-cpu: 	Speed: 0.7ms pre-process, 807.3ms inference, 1.9ms NMS per image at shape (1, 3, 640, 640)

trt-fp32:     	Speed: 7.6ms pre-process, 24.0ms inference, 1.1ms NMS per image at shape (1, 3, 640, 640)

ort-gpu: 	 	Speed: 7.6ms pre-process, 42.1ms inference, 1.2ms NMS per image at shape (1, 3, 640, 640)
ort-cpu: 	 	Speed: 0.8ms pre-process, 567.9ms inference, 1.6ms NMS per image at shape (1, 3, 640, 640)

# 注意：openvino没法使用cuda，但是使用 --device 0 会提高推理速度
openvino-gpu:	Speed: 8.2ms pre-process, 384.6ms inference, 2.8ms NMS per image at shape (1, 3, 640, 640)
openvino-cpu:	Speed: 0.6ms pre-process, 448.6ms inference, 1.5ms NMS per image at shape (1, 3, 640, 640)
```

