# Data Annotation Portfolio

**Vinsentius Davis Anggara** · Aspiring AI Data Annotator

This repository documents self-directed practice in data annotation, labeling consistency, export handling, and quality checks. These are personal practice projects, not paid client work.

## Featured project

### [Project 01 — Vehicle Detection Annotation](projects/01-vehicle-detection/README.md)

- **30** CCTV traffic images annotated in CVAT.
- **159** annotations in the untouched CVAT export; **158** in the portfolio-reviewed copy after one likely false-positive box was removed.
- **5** label categories defined: `car`, `motorcycle`, `bus`, `truck`, and `person`.
- Structural QC checks box dimensions, image boundaries, image coverage, and exact duplicates.
- Source dataset and CC BY 4.0 attribution are documented.

## Tools

- CVAT — bounding-box annotation
- COCO JSON — annotation export
- Python — structural validation and preview rendering
- GitHub — project documentation and versioning

## Transparency

Project 01 is a personal practice project, not professional client experience. The QC report distinguishes structural validation from semantic review and records one likely false-positive correction plus one class-label candidate needing further review.

The downloadable project package contains the full COCO exports and visual preview assets. In this repository revision, the annotation and quality-control documentation is committed, while the larger JSON export and image preview files remain in the package rather than checked into GitHub.
