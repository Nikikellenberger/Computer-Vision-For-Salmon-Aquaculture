# Video Previews

Short annotated videos demonstrating salmon detection, instance
segmentation, and multi-object tracking.

## Preview types

| Type | What the video shows |
|---|---|
| Detection | Bounding boxes and confidence scores from YOLO26s |
| Detection with tracking | Bounding boxes and temporary IDs assigned by ByteTrack |
| Instance segmentation | Predicted fish masks from YOLO26s-seg |
| Segmentation with tracking | Fish masks and IDs, with colors assigned by track ID |

Tracking colors remain consistent while an ID is maintained.
Different IDs may share a color because the color palette is finite.

## Models and data

The detection model was trained on the Healthy and Loser Salmon
dataset, with both original classes merged into one `salmon` class.

The segmentation model was trained on 35 custom-annotated images
from BoostCompTrack CS and TBW training data, with eight additional
images used for validation.

Preview footage comes from the
[BoostCompTrack dataset](https://zenodo.org/records/16880877).

## Evaluation context

- **GH010031:** a separate data source from detection training, but
  represented in the segmentation training data.
- **Korsneset cage 07:** used for a qualitative external-video check
  of the detection model.

These previews illustrate model behavior. They are not quantitative
video benchmarks and do not establish performance across farms.

## How to interpret the results

- Bounding boxes indicate predicted fish locations.
- Masks indicate predicted visible fish regions.
- Confidence scores are model scores, not guaranteed probabilities
  of correctness.
- Track IDs associate observations across frames; they are not
  permanent identities for individual salmon.
- ID changes can occur during overlap, occlusion, or missed detections.
- Tracking does not automatically repair or smooth segmentation masks.
- The number of visible tracks is not the total cage population.

## Observed limitations

Tracking was more stable when fish were visually separated.
Overlaps sometimes caused ID switches or fragmented tracks.
Some segmentation masks omitted visible body regions or varied
between frames.

## Preview details

Each uploaded preview should identify:

- Source recording.
- Detection or segmentation model.
- Whether ByteTrack was enabled.
- Clip duration and inference image size.
- Any settings changed from the notebook defaults.

Annotated outputs may be resized for viewing and are saved without
audio. Playback speed does not indicate inference processing speed.

## Attribution

Source footage belongs to its respective creators. Annotations shown
in these previews are model predictions generated for this project.

Only previews permitted by the source footage's redistribution terms
are included. Publication here does not grant additional rights to
the underlying footage.

