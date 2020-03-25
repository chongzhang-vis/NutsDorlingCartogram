# NutsDorlingCartogram
Dorling cartogram from NUTS regions with Eurostat statistics

<div>
<img src="assets/images/preview.png" alt="preview"/>
<div>
  
## [Live Demo](https://eurostat.github.io/NutsDorlingCartogram/examples/basic/)

## Installation

'npm install nutsdorlingcartogram'

then 
```javascript
NutsDorlingCartogram = require("nutsdorlingcartogram")
```

or

```javascript
<script src="https://unpkg.com/nutsdorlingcartogram/build/dorling.min.js"></script>
```

## Usage

```javascript
NutsDorlingCartogram.dorling({
  svgId: "dorlingSvg",
  width: 800,
  height: 500,
  nutsLvl: 2,
  sizeDatasetId: "demo_r_pjangrp3",
  sizeDatasetFilters: "sex=T&age=TOTAL&unit=NR&time=2018",
  colorDatasetId: "demo_r_gind3",
  colorDatasetFilters: "indic_de=GROWRT&time=2018",
  colorScheme: "interpolateRdYlBu",
  zoom: true,
  legend: {
    //see https://d3-legend.susielu.com/#color
    titleWidth: 200,
    title: "Population change (‰)",
    orient: "horizontal",
    cells: 5,
    shape: "rect",
    shapeRadius: 20,
    shapePadding: 20,
    labelAlign: "middle",
    labelOffset: 10
  }

});
```

# Parameters

Name | Description | Type | Required | Default
:--------- | :--------- | :--------- | :--------- | :---------
svgId | Identifier of the target SVG element | string | true | null
width | Width of the visualization | number | false | 900
height | Height of the visualization | number | false | 500
nutsLvl | NUTS level | number | false | 2
sizeDatasetId | [Eurostat database](https://ec.europa.eu/eurostat/data/database) dataset identifier used to determine circle sizes  | string | false | "demo_r_pjangrp3"
sizeDatasetFilters | URL parameter string to apply to the sizeDataset request  | string | false | "sex=T&age=TOTAL&unit=NR&time=2018"
colorDatasetId | Eurostat dataset identifier used to determine circle colors | number | false | 200
colorDatasetFilters | URL parameter string to apply to the colorDataset request  | string | false | "indic_de=GROWRT&time=2018"
colorScheme | [d3 scale chromatic](https://github.com/d3/d3-scale-chromatic) function name | string | false | "interpolateRdYlBu"
zoom | Enable d3 zoom | boolean | false | true
legend | Object which stores the configuration parameters for the legend. See [here](https://d3-legend.susielu.com/#color) for more details on the following legend options. | object | false | See [here](https://d3-legend.susielu.com/#color) 
&nbsp;&nbsp;&nbsp;&nbsp; legend.orient | Accepted values: "vertical" or "horizontal" | string | false | "vertical"
&nbsp;&nbsp;&nbsp;&nbsp; legend.title | Legend title text | string | false | "Legend"
&nbsp;&nbsp;&nbsp;&nbsp; legend.titleWidth | Width of the legend title | number | false | 200
&nbsp;&nbsp;&nbsp;&nbsp; legend.cells | Number of cells to be shown in the legend | number | false | 5
&nbsp;&nbsp;&nbsp;&nbsp; legend.shape | Shape of the legend cells ("circle" or "rect") | string | false | "rect"
&nbsp;&nbsp;&nbsp;&nbsp; legend.shapeRadius | Radius of the circle when legend.shape is set to "circle" | string | false | null
&nbsp;&nbsp;&nbsp;&nbsp; legend.shapePadding | Padding to be applied to the legend cells for spacing | number | false | 5
&nbsp;&nbsp;&nbsp;&nbsp; legend.labelAlign | Alignment of the legend cell labels. | false | "middle"
&nbsp;&nbsp;&nbsp;&nbsp; legend.labelOffset | Distance in pixels from legend label to its corresponding cell | false | 5


