# Salmon Detection Results

This folder documents the YOLO26s detection experiment using the
Healthy and Loser Salmon dataset.

The original classes were merged into one `salmon` class.
The model detects fish; it does not classify their health status.

## Training configuration

- Initialization: pretrained `yolo26s.pt`
- Training images: 145
- Validation images: 41
- Input size: 640
- Batch size: 8
- Maximum epochs: 100
- Early stopping patience: 20
- Training completed: 84 epochs
- Best checkpoint: epoch 64
- Hardware: Google Colab NVIDIA Tesla T4

## Held-out test performance

Evaluation used 21 images containing 210 annotated salmon.

| Metric | Score |
|---|---:|
| Precision | 0.857 |
| Recall | 0.858 |
| mAP50 | 0.917 |
| mAP50–95 | 0.638 |

## Files

- `results.png` — Training curves and validation metrics.
- `results.csv` — Per-epoch training and validation history.
- `args.yaml` — Training configuration.

The training curves and CSV describe validation performance during
training, not the separate test evaluation reported above.

## Limitations

The test set is small, and some source annotations are incomplete.
These results do not establish performance across different farms,
camera systems, or environmental conditions.

Tracking results are qualitative. ID switches and fragmented tracks
were observed during overlaps and occlusions.
