# Quality Control Report

## Files reviewed

- `annotations/instances_default_raw_cvat_export.json` — unchanged CVAT export.
- `annotations/instances_default.json` — portfolio-reviewed copy.
- Both represent the same 30-image task; the reviewed copy contains one documented correction.

## Visual spot-check correction

A spot-check of sample 03 found that the original export contained a `person` bounding box on a dark object beside the road median that appears to be a bag or roadside item, not a person. Annotation ID `3` was therefore removed from the **portfolio-reviewed copy**. The raw CVAT export remains unchanged. The CVAT task itself has not been edited, so the task and the reviewed JSON are not yet fully synchronized.

A fourth candidate sample is kept in `previews/review_needed/` but excluded from the featured samples. The white light commercial vehicle is labeled `truck` in the export, but its class is ambiguous at this image resolution and should be adjudicated against the class taxonomy before final publication.

## Counts

| Metric | Raw export | Reviewed copy |
|---|---:|---:|
| Images | 30 | 30 |
| Annotations | 159 | 158 |
| `car` | 28 | 28 |
| `motorcycle` | 34 | 34 |
| `bus` | 0 | 0 |
| `truck` | 41 | 41 |
| `person` | 56 | 55 |

## Structural validation of reviewed copy

| Check | Result |
|---|---:|
| Images with at least one annotation | 30 / 30 |
| Boxes with non-positive width or height | 0 |
| Boxes outside image boundaries | 0 |
| Exact duplicate boxes (same image, class and rounded coordinates) | 0 |

## Interpretation and limitations

Structural checks validate data shape and box geometry only. They do not guarantee semantic accuracy or completeness. Only the four user-selected sample images were available for visual spot-checking here; an exhaustive independent audit of all 30 images is not claimed. Before presenting this as a fully final dataset, synchronize the identified correction in CVAT and review the ambiguous sample 04 label.

