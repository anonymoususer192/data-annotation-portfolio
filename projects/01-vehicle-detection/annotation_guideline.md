# Annotation Guidelines — Vehicle Detection

These rules summarize the conventions used for this personal practice task. They are project-specific and are not represented as the original dataset creator’s official guideline.

## Label taxonomy

| Label | Use for |
|---|---|
| `car` | Passenger cars clearly identifiable as cars. |
| `motorcycle` | Motorcycles and motor scooters clearly identifiable as such. |
| `bus` | Buses clearly identifiable in the image. |
| `truck` | Goods-carrying trucks. Do not label every van or pickup as a truck solely because it is a vehicle; ambiguous examples should be reviewed against a consistent taxonomy. |
| `person` | Visible individual people whose presence can be identified. |

## Bounding-box rules

1. Use one rectangle per identifiable object.
2. Keep the rectangle as tight as practical to the visible extent of the object; avoid large areas of unrelated background.
3. For partially occluded objects, annotate the visible extent when the object can still be identified with reasonable confidence.
4. Small distant objects may have small boxes. Do not enlarge a box just to make it easier to see.
5. Do not create separate boxes for the same visible instance in the same frame.
6. If an object cannot be reliably distinguished between categories, do not guess. Review the taxonomy or mark it for later review.
7. Keep class usage consistent across all images.

## Scope and limitations

Five classes were defined, but a label being defined does not mean it occurs in the subset. The `bus` count is zero in both exports.
