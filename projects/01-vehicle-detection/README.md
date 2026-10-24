# Project 01 — Vehicle Detection Annotation

**Type:** Personal practice project · **Tool:** CVAT · **Format:** COCO 1.0 · **Annotation:** rectangle / bounding box

## Project overview

This project practises object-detection annotation on CCTV-style traffic imagery, applying a fixed label taxonomy, exporting in COCO format, and reviewing annotation quality.

This is a **self-directed portfolio project**, not paid client work or a claim of production experience.

## Results

The initial CVAT export contained **30 images and 159 annotations**. During visual spot-checking, one `person` box on a bag-like object beside the road median was identified as a likely false positive. The untouched export is retained in the downloadable project package for traceability, and a separate portfolio-reviewed copy removes that one box.

| Metric | Raw CVAT export | Portfolio-reviewed copy |
|---|---:|---:|
| Images | 30 | 30 |
| Bounding-box annotations | 159 | 158 |
| `car` | 28 | 28 |
| `motorcycle` | 34 | 34 |
| `bus` | 0 | 0 |
| `truck` | 41 | 41 |
| `person` | 56 | 55 |

`bus` was defined in the task taxonomy but does not appear in this 30-image subset. Counts are reported from the exported JSON, not estimates.

## Annotation workflow

1. Selected a 30-image subset from [CCTV_OK_MERGE Original by Tadulako on Roboflow Universe](https://universe.roboflow.com/tadulako/cctv_ok_merge-original).
2. Created a CVAT task with `car`, `motorcycle`, `bus`, `truck`, and `person` labels.
3. Annotated objects with rectangles in CVAT.
4. Exported the task to COCO format.
5. Validated the exported JSON structure and generated before/after previews from the box coordinates.
6. Performed a visual spot-check and documented a likely false positive rather than presenting the untouched export as error-free.

## Quality control

Structural validation on the reviewed copy found:

- 0 boxes with non-positive width or height;
- 0 boxes outside image boundaries;
- 0 images without annotations;
- 0 exact duplicate boxes (same image/class/rounded coordinates).

These structural checks do **not** prove all labels are semantically correct or that every visible object was captured. The source CVAT task has **not** been edited to match the portfolio-reviewed copy; the one correction currently exists only in the reviewed JSON. The fourth candidate also needs a second class review before it is used as a showcase example.

See [`quality_control.md`](quality_control.md), [`quality_check_results.json`](quality_check_results.json), and [`annotation_summary.csv`](annotation_summary.csv) for the QC record and class counts.

## Annotation guidelines

The project-specific labeling rules are in [`annotation_guideline.md`](annotation_guideline.md). They define how to draw tight boxes, handle partially occluded objects, treat small distant instances, and avoid guessing uncertain classes.

## Artifacts

The downloadable project package contains:
- the portfolio-reviewed COCO export (158 annotations);
- the untouched CVAT COCO export (159 annotations);
- four before/after examples and a combined contact sheet.

The larger COCO JSON exports and preview images are not yet checked into this repository revision. The JSON files refer to the source image filenames; the complete 30-image dataset itself is not redistributed here.

## Dataset attribution

Source dataset: [CCTV_OK_MERGE Original by Tadulako on Roboflow Universe](https://universe.roboflow.com/tadulako/cctv_ok_merge-original). The source page identifies the dataset as **CC BY 4.0**. See [`DATASET_ATTRIBUTION.md`](DATASET_ATTRIBUTION.md).
