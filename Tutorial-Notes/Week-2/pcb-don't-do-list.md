# PCB Design Review: Deductions and Bonus Criteria

## Items That Will Result in Mark Deductions

| No. | Item |
|---:|:-----|
| 1 | Board size exceeds 10 cm × 10 cm |
| 2 | Power traces are not adequately thick (see [recommended width](#recommended-width-for-traces)) |
| 3 | Design Rule Check (DRC) errors are present |
| 4 | Crystal is not routed correctly (asymmetric layout, excessive distance, or traces routed underneath) |
| 5 | Signal traces use improper bend angles |
| 6 | Visual indicators or buttons are placed on the back side |
| 7 | XT/XH headers are placed on different sides of the board |
| 8 | Each DRC silkscreen warning |
| 9 | Components are placed partially outside the board outline |
| 10 | Via stitching is missing |
| 11 | Mounting holes are missing |
| 12 | Traces are routed underneath an inductor |
| 13 | More than two vias are placed on a single trace |
| 14 | Power is routed across layers without sufficient vias |
| 15 | Components protrude beneath the TFT or on the back of the PCB |
| 16 | TFT extends outside the board outline |
| 17 | Decoupling capacitor is not assigned to each MCU pin |
| 18 | Unnecessary power trace loops are present |
| 19 | Connections are made in a spider-web layout instead of using copper zones where appropriate (per functional group) |
| 20 | Labels are disorganized or the silkscreen is unclear |
| 21 | A trace passes between two through-hole pads (e.g., XH connector) |
| 22 | Feedback (FB) resistor is placed too far from its target |
| 23 | Ground (GND) plane is missing |
| 24 | Differential pair signal routing is not implemented or indicated |
| 25 | Power trace width is not uniform |
| 26 | Board name is missing or unclear |
| 27 | Traces are too close to the board edge |
| 28 | Board outline is missing or drawn on the wrong layer (not Edge.Cuts) |

## Bonus Points

| No. | Item | Bonus |
|---:|:-----|------:|
| 1 | Reduced board size | 10 |
| 2 | Clear and legible silkscreen | 10 |
| 3 | Organized XH header layout | 10 |

## Reminder

- This board is intended for hand soldering. Do not place components too close together.
- Run DRC before you submit your homework!!!

## Recommended Width for Traces
| Signal / Voltage | Trace Width (mil) |
| :--- | :--- |
| 24V | 80 mil |
| 5V | 30 mil |
| 3V3 | 20 mil |
| Signal (sig) | 10 mil |

> **Note:** Trace widths are scaled according to current carrying requirements. Higher voltage/current rails (e.g., 24V) require significantly thicker traces compared to low-power signal lines.

## Submission Details
