
# Matplotlib & Seaborn


Matplotlib is a foundational plotting library in Python. It offers granular control over every aspect of a plot — from axes and ticks to colors and annotations.

```python
import matplotlib.pyplot as plt
```

-  Low-level, highly customizable
-  Ideal for precise control and layered plots

---


Seaborn is built on top of Matplotlib and Pandas. It simplifies statistical plotting and comes with aesthetically pleasing defaults.

```python
import seaborn as sns
```

-  High-level API for statistical plots
-  Great for quick insights and grouped visualizations

---

#  Matplotlib Plot Types (with Full Argument Cheatsheets)

---

## 1. `plt.plot()` – Line Plot

###  Syntax
```python
plt.plot(
    x, y,
    color=None, linestyle=None, linewidth=None,
    marker=None, markersize=None, markerfacecolor=None, markeredgecolor=None,
    label=None, alpha=None, zorder=None, antialiased=None
)
```

###  Cheatsheet

| Argument            | Description                              | Example         |
|---------------------|------------------------------------------|------------------|
| `x`, `y`            | Coordinates                              | `[1,2,3]`        |
| `color`             | Line color                               | `'blue'`         |
| `linestyle`         | Line style (`'-'`, `'--'`, `':'`, `'-.'`) | `'--'`           |
| `linewidth`         | Line thickness                           | `2.5`            |
| `marker`            | Marker style (`'o'`, `'s'`, `'^'`)        | `'o'`            |
| `markersize`        | Size of markers                          | `8`              |
| `markerfacecolor`   | Fill color of marker                     | `'red'`          |
| `markeredgecolor`   | Border color of marker                   | `'black'`        |
| `label`             | Legend label                             | `'Trend'`        |
| `alpha`             | Transparency (0 to 1)                    | `0.7`            |
| `zorder`            | Layering order                           | `2`              |
| `antialiased`       | Smooth edges                             | `True`           |

---

## 2. `plt.scatter()` – Scatter Plot

###  Syntax
```python
plt.scatter(
    x, y,
    s=None, c=None, marker=None,
    alpha=None, linewidths=None, edgecolors=None,
    label=None
)
```

###  Cheatsheet

| Argument       | Description                        | Example     |
|----------------|------------------------------------|-------------|
| `x`, `y`       | Coordinates                        | `[1,2,3]`   |
| `s`            | Marker size                        | `100`       |
| `c`            | Color                              | `'green'`   |
| `marker`       | Marker shape                       | `'x'`       |
| `alpha`        | Transparency                       | `0.6`       |
| `linewidths`   | Border thickness                   | `1.5`       |
| `edgecolors`   | Border color                       | `'black'`   |
| `label`        | Legend label                       | `'Points'`  |

---

## 3. `plt.bar()` – Bar Chart

###  Syntax
```python
plt.bar(
    x, height,
    width=0.8, bottom=None,
    align='center', color=None,
    edgecolor=None, linewidth=None,
    tick_label=None, label=None
)
```

###  Cheatsheet

| Argument       | Description                        | Example     |
|----------------|------------------------------------|-------------|
| `x`            | Categories                         | `['A','B']` |
| `height`       | Bar heights                        | `[10, 20]`  |
| `width`        | Bar width                          | `0.5`       |
| `bottom`       | Starting point                     | `[0, 0]`    |
| `align`        | `'center'` or `'edge'`             | `'center'`  |
| `color`        | Fill color                         | `'orange'`  |
| `edgecolor`    | Border color                       | `'black'`   |
| `linewidth`    | Border thickness                   | `1.5`       |
| `tick_label`   | Custom tick labels                 | `['X','Y']` |
| `label`        | Legend label                       | `'Bars'`    |

---

## 4. `plt.hist()` – Histogram

###  Syntax
```python
plt.hist(
    x, bins=10, range=None,
    density=False, weights=None,
    cumulative=False, histtype='bar',
    align='mid', orientation='vertical',
    rwidth=None, color=None, label=None,
    alpha=None, edgecolor=None, linewidth=None
)
```

###  Cheatsheet

| Argument       | Description                        | Example     |
|----------------|------------------------------------|-------------|
| `x`            | Input data                         | `[1,2,3]`   |
| `bins`         | Number of bins                     | `10`        |
| `range`        | Range of values                    | `(0,100)`   |
| `density`      | Normalize histogram                | `True`      |
| `weights`      | Weight for each value              | `[1,1,1]`   |
| `cumulative`   | Cumulative histogram               | `False`     |
| `histtype`     | `'bar'`, `'step'`, `'stepfilled'`  | `'bar'`     |
| `align`        | `'left'`, `'mid'`, `'right'`       | `'mid'`     |
| `orientation`  | `'vertical'` or `'horizontal'`     | `'vertical'`|
| `rwidth`       | Relative width                     | `0.9`       |
| `color`        | Fill color                         | `'gray'`    |
| `edgecolor`    | Border color                       | `'black'`   |
| `linewidth`    | Border thickness                   | `1.2`       |

---

#  Seaborn Plot Types (with Full Argument Cheatsheets)

---

## 1. `sns.lineplot()`

###  Syntax
```python
sns.lineplot(
    x=None, y=None, data=None,
    hue=None, style=None, size=None,
    palette=None, markers=False, dashes=True,
    legend='auto', ci=95, estimator='mean',
    errorbar=None
)
```

###  Cheatsheet

| Argument     | Description                          | Example         |
|--------------|--------------------------------------|------------------|
| `x`, `y`     | Column names                         | `'x'`, `'y'`     |
| `data`       | DataFrame                            | `df`             |
| `hue`        | Color grouping                       | `'group'`        |
| `style`      | Line style grouping                  | `'type'`         |
| `size`       | Line thickness grouping              | `'value'`        |
| `palette`    | Color palette                        | `'Set2'`         |
| `markers`    | Show markers                         | `True`           |
| `dashes`     | Show dashed lines                    | `False`          |
| `legend`     | Legend behavior                      | `'brief'`        |
| `ci`         | Confidence interval                  | `None`           |
| `estimator`  | Aggregation function                 | `'mean'`         |
| `errorbar`   | Error bar type                       | `'sd'`           |

---

## 2. `sns.scatterplot()`

###  Syntax
```python
sns.scatterplot(
    x=None, y=None, data=None,
    hue=None, style=None, size=None,
    palette=None, sizes=None, markers=True,
    edgecolor='w', linewidth=0.5, alpha=None
)
```

###  Cheatsheet

| Argument     | Description                          | Example         |
|--------------|--------------------------------------|------------------|
| `sizes`      | Size mapping                         | `(20, 200)`      |
| `edgecolor`  | Border color                         | `'black'`        |
| `linewidth`  | Border thickness                     | `1.0`            |
| `alpha`      | Transparency                         | `0.7`            |

---

##  `sns.histplot()` – Seaborn Histogram

### Syntax
```python
sns.histplot(
    data=None, x=None, y=None, hue=None,
    weights=None, stat='count', bins='auto',
    binwidth=None, binrange=None, discrete=None,
    cumulative=False, common_bins=True, common_norm=True,
    multiple='layer', element='bars', fill=True,
    shrink=1, kde=False, kde_kws=None, line_kws=None,
    thresh=0, pthresh=None, pmax=None,
    cbar=False, cbar_ax=None, cbar_kws=None,
    palette=None, hue_order=None, hue_norm=None,
    color=None, log_scale=None, legend=True,
    ax=None, **kwargs
)
```

###  Cheatsheet of All Parameters

| Argument        | Description                                                                 | Example               |
|-----------------|-----------------------------------------------------------------------------|------------------------|
| `data`          | DataFrame or array-like input                                               | `df`                  |
| `x`, `y`        | Column names for axes                                                       | `'value'`, `'score'`  |
| `hue`           | Semantic variable for color grouping                                        | `'category'`          |
| `weights`       | Weight each observation                                                     | `'weights'`           |
| `stat`          | `'count'`, `'frequency'`, `'probability'`, `'percent'`, `'density'`         | `'density'`           |
| `bins`          | Number of bins or bin edges                                                 | `20`, `'auto'`        |
| `binwidth`      | Width of each bin                                                           | `5`                   |
| `binrange`      | Tuple of min/max values                                                     | `(0, 100)`            |
| `discrete`      | Treat data as discrete (centered bars)                                      | `True`                |
| `cumulative`    | Show cumulative counts                                                      | `True`                |
| `common_bins`   | Use same bins across hue groups                                             | `False`               |
| `common_norm`   | Normalize across hue groups                                                 | `False`               |
| `multiple`      | `'layer'`, `'stack'`, `'dodge'`, `'fill'`                                   | `'stack'`             |
| `element`       | `'bars'`, `'step'`, `'poly'`                                                | `'bars'`              |
| `fill`          | Fill bars                                                                   | `True`                |
| `shrink`        | Shrink bar width (0–1)                                                      | `0.8`                 |
| `kde`           | Overlay KDE curve                                                           | `True`                |
| `kde_kws`       | Dict of KDE options                                                         | `{'bw_adjust': 0.5}`  |
| `line_kws`      | Dict of line options for KDE                                                | `{'color': 'red'}`    |
| `thresh`        | Minimum height to show bar                                                  | `0.01`                |
| `pthresh`       | Threshold for KDE polygon fill                                              | `0.1`                 |
| `pmax`          | Max value for KDE polygon fill                                              | `0.9`                 |
| `cbar`          | Show color bar                                                              | `True`                |
| `cbar_ax`       | Axes object for color bar                                                   | `ax2`                 |
| `cbar_kws`      | Dict of color bar options                                                   | `{'orientation': 'horizontal'}` |
| `palette`       | Color palette                                                               | `'Set2'`              |
| `hue_order`     | Custom order of hue categories                                              | `['A', 'B', 'C']`     |
| `hue_norm`      | Normalize hue values                                                        | `(0, 1)`              |
| `color`         | Single color override                                                       | `'blue'`              |
| `log_scale`     | Log scale axes (`True`, `False`, or tuple)                                  | `(True, False)`       |
| `legend`        | Show legend                                                                 | `True`                |
| `ax`            | Matplotlib Axes object                                                      | `ax`                  |
| `**kwargs`      | Additional keyword arguments passed to `matplotlib.pyplot.hist`             | `label='My Histogram'`|

---


## 4. `sns.histplot()` – Histogram

###  Syntax
```python
sns.histplot(
    data=None, x=None, y=None,
    hue=None, multiple='layer',
    bins=None, binwidth=None, binrange=None,
    stat='count', kde=False, element='bars',
    fill=True, palette=None, alpha=None,
    linewidth=None, edgecolor=None, legend=True
)
```

###  Cheatsheet

| Argument      | Description                                 | Example         |
|---------------|---------------------------------------------|------------------|
| `data`        | DataFrame                                   | `df`             |
| `x`, `y`      | Column names                                | `'value'`        |
| `hue`         | Color grouping                              | `'group'`        |
| `multiple`    | `'layer'`, `'stack'`, `'dodge'`             | `'stack'`        |
| `bins`        | Number of bins                              | `20`             |
| `binwidth`    | Width of each bin                           | `5`              |
| `binrange`    | Tuple of min/max values                     | `(0, 100)`       |
| `stat`        | `'count'`, `'frequency'`, `'density'`, `'probability'` | `'density'` |
| `kde`         | Show KDE curve                              | `True`           |
| `element`     | `'bars'`, `'step'`, `'poly'`                | `'bars'`         |
| `fill`        | Fill bars                                   | `True`           |
| `palette`     | Color palette                               | `'Set2'`         |
| `alpha`       | Transparency                                | `0.6`            |
| `linewidth`   | Border thickness                            | `1.0`            |
| `edgecolor`   | Border color                                | `'black'`        |
| `legend`      | Show legend                                 | `True`           |

---

## 5. `sns.kdeplot()` – Kernel Density Estimate

###  Syntax
```python
sns.kdeplot(
    data=None, x=None, y=None,
    hue=None, multiple='layer',
    bw_adjust=1, cut=3, clip=None,
    fill=False, common_norm=True,
    palette=None, alpha=None, linewidth=None,
    legend=True
)
```

###  Cheatsheet

| Argument      | Description                                 | Example         |
|---------------|---------------------------------------------|------------------|
| `bw_adjust`   | Bandwidth adjustment                        | `0.5`            |
| `cut`         | Extend beyond data range                    | `3`              |
| `clip`        | Limit range                                 | `(0, 100)`       |
| `fill`        | Fill under curve                            | `True`           |
| `common_norm` | Normalize across groups                     | `False`          |
| `palette`     | Color palette                               | `'coolwarm'`     |
| `alpha`       | Transparency                                | `0.5`            |
| `linewidth`   | Line thickness                              | `2.0`            |
| `legend`      | Show legend                                 | `True`           |

---

## 6. `sns.boxplot()` – Box Plot

###  Syntax
```python
sns.boxplot(
    x=None, y=None, data=None,
    hue=None, order=None, orient=None,
    color=None, palette=None, saturation=0.75,
    width=0.8, dodge=True, fliersize=5,
    linewidth=None, boxprops=None, whiskerprops=None,
    capprops=None, medianprops=None, meanprops=None,
    showmeans=False, showcaps=True, showbox=True,
    showfliers=True, notch=False
)
```

###  Cheatsheet

| Argument       | Description                              | Example         |
|----------------|------------------------------------------|------------------|
| `order`        | Custom category order                    | `['A','B','C']`  |
| `orient`       | `'v'` or `'h'`                           | `'h'`            |
| `saturation`   | Color intensity                          | `0.6`            |
| `width`        | Box width                                | `0.5`            |
| `dodge`        | Separate boxes by hue                    | `True`           |
| `fliersize`    | Outlier marker size                      | `6`              |
| `linewidth`    | Border thickness                         | `1.5`            |
| `showmeans`    | Show mean marker                         | `True`           |
| `notch`        | Show notch                               | `True`           |

---

## 7. `sns.violinplot()` – Violin Plot

###  Syntax
```python
sns.violinplot(
    x=None, y=None, data=None,
    hue=None, order=None, orient=None,
    bw='scott', cut=2, scale='area',
    scale_hue=True, gridsize=100,
    width=0.8, inner='box', split=False,
    palette=None, saturation=0.75,
    linewidth=None
)
```

###  Cheatsheet

| Argument       | Description                              | Example         |
|----------------|------------------------------------------|------------------|
| `bw`           | Bandwidth method                         | `'silverman'`    |
| `cut`          | Extend beyond data range                 | `2`              |
| `scale`        | `'area'`, `'count'`, `'width'`           | `'count'`        |
| `scale_hue`    | Normalize across hue groups              | `False`          |
| `gridsize`     | KDE resolution                           | `200`            |
| `inner`        | `'box'`, `'quartile'`, `'stick'`, `None` | `'quartile'`     |
| `split`        | Split violins by hue                     | `True`           |
| `width`        | Violin width                             | `0.6`            |
| `linewidth`    | Border thickness                         | `1.2`            |

---

## 8. `sns.barplot()` – Aggregated Bar Plot

###  Syntax
```python
sns.barplot(
    x=None, y=None, data=None,
    hue=None, order=None, estimator='mean',
    ci=95, n_boot=1000, units=None,
    seed=None, orient=None, color=None,
    palette=None, saturation=0.75,
    width=0.8, dodge=True, errwidth=None,
    capsize=None
)
```

###  Cheatsheet

| Argument       | Description                              | Example         |
|----------------|------------------------------------------|------------------|
| `estimator`    | Aggregation function                     | `'median'`       |
| `ci`           | Confidence interval                      | `None`           |
| `n_boot`       | Bootstrap samples                        | `500`            |
| `units`        | Column for repeated measures             | `'subject_id'`   |
| `seed`         | Random seed                              | `42`             |
| `errwidth`     | Error bar thickness                      | `1.5`            |
| `capsize`      | Error bar cap size                       | `0.2`            |

---

## 9. `sns.heatmap()` – Correlation Matrix / Grid Plot

###  Syntax
```python
sns.heatmap(
    data, vmin=None, vmax=None, cmap=None,
    center=None, robust=False, annot=False,
    fmt='.2g', annot_kws=None, linewidths=0,
    linecolor='white', cbar=True, cbar_kws=None,
    square=False, xticklabels=True, yticklabels=True,
    mask=None
)
```

### Cheatsheet

| Argument       | Description                              | Example         |
|----------------|------------------------------------------|------------------|
| `vmin`, `vmax` | Value range                              | `0`, `1`         |
| `cmap`         | Color map                                | `'coolwarm'`     |
| `center`       | Center value for colormap                | `0`              |
| `robust`       | Ignore outliers                          | `True`           |
| `annot`        | Show values                              | `True`           |
| `fmt`          | Format string                            | `'.1f'`          |
| `linewidths`   | Grid line thickness                      | `0.5`            |
| `linecolor`    | Grid line color                          | `'black'`        |
| `cbar`         | Show color bar                           | `True`           |
| `square`       | Force square cells                       | `True`           |
| `mask`         | Mask values                              | `df.isnull()`    |

---
