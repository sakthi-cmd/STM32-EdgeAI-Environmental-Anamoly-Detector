# Edge AI Environmental Anomaly Detector on STM32 (TinyML)

A bare-metal TinyML pipeline that deploys a multivariate neural network onto an STM32L4S5 microcontroller to detect environmental anomalies in real-time.

## 🚀 The Pipeline Overview
Instead of relying on rigid, hardcoded threshold limits, this project utilizes an embedded neural network to evaluate the *interacted signature* of multiple sensor inputs simultaneously.

1. **Data Pipeline:** Preprocessed multivariate datasets to train an MLP classifier in PyTorch, exported via ONNX.
2. **Edge Deployment:** Used STMicroelectronics' **X-CUBE-AI** to optimize and compile the model into bare-metal C-code.
3. **On-Chip Softmax Activation:** Implemented a numerically stable Softmax math block in the C runtime to map raw logits cleanly to a 0% to 100% confidence scale.
4. **Hardware Actuation:** Tied the inference engine directly to hardware GPIO, instantly driving an onboard LED when anomaly confidence crosses 80%.

## 🛠️ Tech Stack & Hardware
- **Microcontroller:** STM32L4S5VI (ARM Cortex-M4)
- **Software/Tools:** STM32CubeIDE, X-CUBE-AI, PyTorch, ONNX, PuTTY
- **Language:** C / Python
