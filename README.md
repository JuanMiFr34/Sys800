# Sys800


Entraînement PyTorch (5 époques)
              │
              ▼
MobileNetV2 α=0.25 + CIFAR-100
              │
              ▼
      Précision: 55%
              │
              ▼
        [Export ONNX]
              │
              ▼
       ┌──────┴──────┐
       │             │
       ▼             ▼
  Approche A     Approche B
  ST Toolchain   ONNX Runtime
       │             │
       ▼             ▼
  Calibration    Calibration
  sur 10 images   sur >100 images
       │             │
       ▼             ▼
    PTQ INT8       PTQ INT8
       │             │
       ▼             ▼
    16% acc.       36% acc.
    Flash: 294Ko   Flash: 285.5Ko
    RAM: 309Ko     RAM: 307.4Ko
       │             │
       └──────┬──────┘
              │
              ▼
  Déploiement sur STM32F767ZI
  (Image d'entrée: 520Ko > RAM disponible → limitation)
