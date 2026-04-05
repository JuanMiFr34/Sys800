# Sys800


[Entraînement PyTorch - 5 epochs]
         ↓
MobileNetV2 α=0.25 + CIFAR-100
         ↓
  Précision: 55%
         ↓
   [Export ONNX]
         ↓
    ┌────┴────┐
    ↓         ↓
[Approche A] [Approche B]
ST Toolchain  ONNX Runtime
    │         (Google Colab)
    ↓              ↓
Calibration   Calibration
sur 10 images  sur >100 images
    ↓              ↓
 PTQ INT8       PTQ INT8
    ↓              ↓
 16% acc.       36% acc.
    ↓              ↓
    └──────┬───────┘
           ↓
   [Déploiement sur STM32F767ZI]
