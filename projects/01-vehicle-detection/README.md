# Project 01 — Vehicle Detection Annotation

**Type:** Personal practice project · **Tool:** CVAT · **Format:** COCO 1.0 · **Annotation:** rectangle / bounding box

## Project overview

This project practises object-detection annotation on CCTV-style traffic imagery, applying a fixed label taxonomy, exporting in COCO format, and reviewing annotation quality.

This is a **self-directed portfolio project**, not paid client work or a claim of production experience.

## Results

The initial CVAT export contained **30 images and 159 annotations**. During visual spot-checking, one `person` box on a bag-like object beside the road median was identified as a likely false positive. I preserved the untouched export for traceability and removed that one box in a separate portfolio-reviewed copy.

| Metric | Raw CVAT export | Portfolio-reviewed copy |
|---|---:|---:|
| Images | 30 | 30 |
| Bounding-box annotations | 159 | 158 |
| `car` | 28 | 28 |
| `motorcycle` | 34 | 34 |
| `bus` | 0 | 0 |
| `truck` | 41 | 41 |
| `person` | 56 | 55 |

`bus` was defined in the task taxonomy but does not appear in this 30-image subset. Counts are reported from the actual JSON files, not estimates.

## Before / after examples

The annotated previews are rendered from the **portfolio-reviewed COCO JSON**. The raw CVAT export is also retained so the review correction is auditable.

### Sample 01 — Multiple vehicles and distant objects

| Before | After |
|---|---|
| ![Before sample 01](previews/before_01.jpg) | ![After sample 01](previews/after_01.jpg) |

### Sample 02 — Prominent car and distant vehicle

| Before | After |
|---|---|
| ![Before sample 02](previews/before_02.jpg) | ![After sample 02](previews/after_02.jpg) |

### Sample 03 — Vehicle and people at different scales

| Before | After (after review correction) |
|---|---|
| ![Before sample 03](previews/before_03.jpg) | ![After sample 03](previews/after_03.jpg) |

[Open the combined contact sheet](previews/before_after_contact_sheet.jpg).

A fourth candidate is retained under [`previews/review_needed/`](previews/review_needed/) but is not featured because the class assigned to a distant light commercial vehicle needs a taxonomy-based second review.

## Workflow

1. Selected a 30-image subset from the source dataset.
2. Created a CVAT task with `car`, `motorcycle`, `bus`, `truck`, and `person` labels.
3. Annotated objects with rectangles in CVAT.
4. Exported the task to COCO format.
5. Validated the exported JSON structure and rendered preview images from the box coordinates.
6. Performed a visual spot-check and documented a likely false positive rather than silently presenting the untouched export as error-free.

## Quality control

Structural validation on the reviewed copy found:

- 0 boxes with non-positive width or height;
- 0 boxes outside image boundaries;
- 0 images without annotations;
- 0 exact duplicate boxes (same image/class/rounded coordinates).

These structural checks do **not** prove all labels are semantically correct or that every visible object was captured. The source CVAT task has **not** been edited to match the portfolio-reviewed copy; the one correction currently exists only in the reviewed JSON. The fourth candidate also needs a second class review before it is used as a showcase example.

See [`quality_control.md`](quality_control.md) and [`quality_check_results.json`](quality_check_results.json) for the audit trail.

## Files

- [`annotations/instances_default.json`](annotations/instances_default.json) — portfolio-reviewed COCO JSON (158 annotations).
- [`annotations/instances_default_raw_cvat_export.json`](annotations/instances_default_raw_cvat_export.json) — untouched CVAT export (159 annotations).
- [`annotation_summary.csv`](annotation_summary.csv) — raw and reviewed class counts.
- [`annotation_guideline.md`](annotation_guideline.md) — project-specific labeling rules.
- [`quality_control.md`](quality_control.md) — structural checks and visual review notes.
- [`previews/`](previews/) — curated before/after samples and a contact sheet.

**Dataset note:** the COCO files reference the 30 original image filenames. This repository package includes four sample images for display, not all 30 originals. Download the source dataset separately if you need all image files to reload the full annotation export.

## Dataset attribution

Source dataset: [CCTV_OK_MERGE Original by Tadulako on Roboflow Universe](https://universe.roboflow.com/tadulako/cctv_ok_merge-original). The source page identifies the dataset as **CC BY 4.0**. See [`DATASET_ATTRIBUTION.md`](DATASET_ATTRIBUTION.md).
