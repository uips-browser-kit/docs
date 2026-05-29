# Solarized Palette

Precision color scheme by Ethan Schoonover.  
Spec and rationale: <https://ethanschoonover.com/solarized/>

---

## Base tones

Eight values forming a monotone ramp. In dark mode the lower four serve as backgrounds and the upper four as content. In light mode the roles swap — the scheme is designed to be symmetric.

| Name    | Hex       | L*   | Dark mode role        | Light mode role       |
|---------|-----------|------|-----------------------|-----------------------|
| base03  | `#002b36` |  15  | Background (darkest)  | —                     |
| base02  | `#073642` |  20  | Background (dark)     | —                     |
| base01  | `#586e75` |  45  | Optional emphasis     | Body text             |
| base00  | `#657b83` |  50  | Body text             | Optional emphasis     |
| base0   | `#839496` |  60  | Body text             | Optional emphasis     |
| base1   | `#93a1a1` |  65  | Optional emphasis     | Body text             |
| base2   | `#eee8d5` |  92  | —                     | Background (light)    |
| base3   | `#fdf6e3` |  97  | —                     | Background (lightest) |

---

## Accent colors

Eight accent values with consistent lightness (~50 L*). Interchangeable across dark and light backgrounds.

| Name     | Hex       | Swatch                                                                 |
|----------|-----------|------------------------------------------------------------------------|
| yellow   | `#b58900` | ![#b58900](https://placehold.co/12x12/b58900/b58900.png)              |
| orange   | `#cb4b16` | ![#cb4b16](https://placehold.co/12x12/cb4b16/cb4b16.png)              |
| red      | `#dc322f` | ![#dc322f](https://placehold.co/12x12/dc322f/dc322f.png)              |
| magenta  | `#d33682` | ![#d33682](https://placehold.co/12x12/d33682/d33682.png)              |
| violet   | `#6c71c4` | ![#6c71c4](https://placehold.co/12x12/6c71c4/6c71c4.png)              |
| blue     | `#268bd2` | ![#268bd2](https://placehold.co/12x12/268bd2/268bd2.png)              |
| cyan     | `#2aa198` | ![#2aa198](https://placehold.co/12x12/2aa198/2aa198.png)              |
| green    | `#859900` | ![#859900](https://placehold.co/12x12/859900/859900.png)              |

---

## CSS custom properties

```css
:root {
  /* Base tones */
  --sol-base03:  #002b36;
  --sol-base02:  #073642;
  --sol-base01:  #586e75;
  --sol-base00:  #657b83;
  --sol-base0:   #839496;
  --sol-base1:   #93a1a1;
  --sol-base2:   #eee8d5;
  --sol-base3:   #fdf6e3;

  /* Accent colors */
  --sol-yellow:  #b58900;
  --sol-orange:  #cb4b16;
  --sol-red:     #dc322f;
  --sol-magenta: #d33682;
  --sol-violet:  #6c71c4;
  --sol-blue:    #268bd2;
  --sol-cyan:    #2aa198;
  --sol-green:   #859900;
}

/* Dark mode semantic aliases */
[data-theme="dark"] {
  --color-bg:       var(--sol-base03);
  --color-bg-alt:   var(--sol-base02);
  --color-emphasis: var(--sol-base01);
  --color-text:     var(--sol-base0);
  --color-text-alt: var(--sol-base1);
}

/* Light mode semantic aliases */
[data-theme="light"] {
  --color-bg:       var(--sol-base3);
  --color-bg-alt:   var(--sol-base2);
  --color-emphasis: var(--sol-base1);
  --color-text:     var(--sol-base00);
  --color-text-alt: var(--sol-base01);
}
```

---

## Python dict

```python
SOLARIZED = {
    # Base tones
    "base03":  "#002b36",
    "base02":  "#073642",
    "base01":  "#586e75",
    "base00":  "#657b83",
    "base0":   "#839496",
    "base1":   "#93a1a1",
    "base2":   "#eee8d5",
    "base3":   "#fdf6e3",
    # Accents
    "yellow":  "#b58900",
    "orange":  "#cb4b16",
    "red":     "#dc322f",
    "magenta": "#d33682",
    "violet":  "#6c71c4",
    "blue":    "#268bd2",
    "cyan":    "#2aa198",
    "green":   "#859900",
}
```

---

## Design notes

- All 16 values were derived using the CIELAB colorspace to achieve **equal perceived contrast** across both themes.
- The four darkest and four lightest base tones are mirror images — `base03`/`base3`, `base02`/`base2`, `base01`/`base1`, `base00`/`base0` swap roles between modes.
- Accent values maintain readability on both dark (`base03`) and light (`base3`) backgrounds without modification.
- Avoid mixing accents with non-Solarized greys; the contrast model breaks outside the palette.
