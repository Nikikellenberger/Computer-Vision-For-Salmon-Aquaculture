# Salmon Instance Segmentation Results

This folder documents the YOLO26s-seg experiment using a custom
dataset annotated in Ultralytics Platform.

Source images were selected from the BoostCompTrack CS and TBW
training folders, including GH010031 and cage 15 footage.

## Dataset

- Class: `salmon`
- Total images: 43
- Training images: 35
- Validation images: 8
- Total instance polygons: 897
- Validation instances: 184
- Independent test split: not yet available

Annotations were converted to YOLO segmentation format and checked
using polygon overlays.

## Training configuration

- Initialization: pretrained `yolo26s-seg.pt`
- Input size: 640
- Batch size: 4
- Epochs completed: 100
- Hardware: Google Colab NVIDIA Tesla T4

## Validation performance

| Metric | Bounding boxes | Instance masks |
|---|---:|---:|
| Precision | 0.866 | 0.866 |
| Recall | 0.886 | 0.886 |
| mAP50 | 0.944 | 0.946 |
| mAP50–95 | 0.744 | 0.705 |

These results are from the best checkpoint evaluated on the
validation split.

## Files

- `results_seg.png` — Training curves and validation metrics.
- `results_seg.csv` — Per-epoch training and validation history.
- `args_seg.yaml` — Training configuration.

## Limitations

Training and validation include frames from the same source
recordings. The reported scores therefore do not establish
generalization to independent recordings.

Video inspection revealed incomplete masks on some fish and
frame-to-frame mask variation. ByteTrack added temporary IDs,
but overlaps could still cause ID switches.

The detection and segmentation experiments use different datasets
and evaluation splits, so their scores are not directly comparable.
