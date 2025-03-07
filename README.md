# JournalPlots

A Python package for creating publication-ready matplotlib figures with consistent styling. Designed to make your scientific visualizations look professional and meet journal requirements.

## Features

- 🎨 Colorblind-friendly color palettes
- 📏 Journal-appropriate font sizes and styles
- 🖼️ High-resolution output settings (300 DPI)
- 🎯 Easy-to-use styling functions
- 📐 Consistent figure dimensions

## Installation

You can install the package directly from source:

```bash
git clone https://github.com/joemans3/journalplots.git
cd journalplots
pip install .
```

or use PyPI package:
```bash
pip install JournalPlots
```

## Usage

### Basic Usage

```python
import matplotlib.pyplot as plt
from journalplots import set_style, apply_style, cb_colors

# Set the global style
set_style(font_scale=1.0)

# Create your plot
fig, ax = plt.subplots()
ax.plot([1, 2, 3], [1, 2, 3], color=cb_colors()['red'], label='Data')
apply_style(ax, title='My Plot', xlabel='X', ylabel='Y')
plt.show()
```

### Available Colors

The package includes a colorblind-friendly palette:
```python
from journalplots import cb_colors

red = cb_colors()['red']

# Available colors:
# - COLORBLIND_COLORS = {
# -    "blue": "#377eb8",
# -    "orange": "#ff7f00",
# -    "green": "#4daf4a",
# -    "pink": "#f781bf",
# -    "brown": "#a65628",
# -    "purple": "#984ea3",
# -    "gray": "#999999",
# -    "red": "#e41a1c",
# -    "yellow": "#dede00",
# }

# Using set_style, subsequent plots cycle through these colorblind colors rather than the Pyplot defaults.
```

### Customizing Sizes

You can adjust various size parameters:
```python
from journalplots import SIZES

# Available size presets:
# - SIZES['figure']       # Default figure size in inches
# - SIZES['font']         # Font sizes (tiny, small, medium, large, xlarge)
# - SIZES['linewidth']    # Default line width
# - SIZES['markersize']   # Default marker size
# - SIZES['tick_length']  # Length of axis ticks
```

### Style Functions

#### set_style()
Sets global matplotlib parameters for consistent styling:
```python
set_style(font_scale=1.0)  # Adjust font_scale to make all text larger or smaller
```

#### apply_style()
Apply styling to a specific axes object:
```python
apply_style(ax,
           title='My Plot',     # Optional plot title
           xlabel='X',          # Optional x-axis label
           ylabel='Y',          # Optional y-axis label
           legend=True)         # Whether to show legend
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
