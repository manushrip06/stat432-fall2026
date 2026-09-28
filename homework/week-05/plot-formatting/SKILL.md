---
name: stat432-plot-formatting
description: Improves formatting of STAT 432 homework plots produced in R or Python. Use only when the user explicitly asks to use this skill on a homework figure.
disable-model-invocation: true
---

# STAT 432 Homework Plot Formatting

## Intent

Polish homework figures for readability and submission quality without changing the underlying data, statistics, or analysis.

## When to use

Apply this skill only when the student explicitly names `stat432-plot-formatting` or asks you to use this plot-formatting skill on a homework figure.

## Formatting rules

### Margins and layout

- Call `tight_layout()` (Python) or use adequate theme margins (R) so titles and labels are not clipped.
- Default figure size about `(8, 5)` for one panel; `(10, 6)` for multi-series line plots.
- Keep legends inside the plot area only when they do not cover important data.

### Titles

- Use one clear, descriptive title in sentence case.
- State what is being plotted and the main comparison (for example, error components versus a tuning parameter).

### Axes

- Use tick marks that match the data (every value, every other value, or a regular grid).
- Start the y-axis at 0 when all plotted values are non-negative and the scale is absolute.
- Rotate x-axis labels slightly if tick labels overlap.

### Labels

- Write full axis labels, not single-letter shortcuts alone.
- Name the x-variable with its role (for example, “Number of neighbors (k)”).
- Name the y-variable with what is estimated or measured (for example, “Estimated squared bias, variance, and MSE”).
- Include units when the quantity has them.

### Colors

- Prefer a colorblind-friendly palette (for example, matplotlib `tab10` or a ColorBrewer set).
- Assign a distinct color to each series and keep legend order matched to the plot order.
- Combine color with line style or markers so series remain distinguishable in grayscale.

### Sizes

- Base text around 11–12 pt; title around 13–14 pt.
- Line width about 1.5–2; marker size about 5–7.
- Keep legend text the same size as axis labels.

## Rules

- Do not change data, simulation settings, model fits, or numerical results.
- Do not refer to specific homework question numbers inside the skill file.
- Apply the same standards in matplotlib/seaborn (Python) or ggplot2 (R).
