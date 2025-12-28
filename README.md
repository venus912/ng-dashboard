<p align="center"><img src="src/assets/img/about9.jpg" style="width: 580px; height: 325px"></p>

<h1><p align="center">NG Dashboard</p></h1>
<b><p align="center">Dashboard for Angular (versions 4 +)</p></b>

<p align="center">
<b>If you find this project useful and are going to use it, please give a star in the repo and credits to the author.</b>
</p>

## Features

- Use of asynchrony for responsiveness and fast rendering. Data loading is executed 
  in **asynchronous** and **sequential** code blocks. This frees the main thread for rendering the user interface 
  without blocking it, and allows fast TTI (Time To Interactive)

## Requirements

- Latest versions of node, npm/yarn
- Latest versions of Angular-CLI

## Installation and Use

- To install in a existing project generated with Angular-CLI, run: `npm install YagoLopez/ng-dashboard --save`
- To copy and run this project: Clone or fork the repository
- Install dependencies running `npm install`
- Run: `ng serve` from project directory
- Metrics Graphics Chart Component is located in `mgChart` folder.
  - If you want to use this component, you can copy this folder to your `app` folder and import `mgChartMod` 
  in your own module or 
  - Import it directily from `/node_modules/ng-dashboard/src/app/mgChart/mgChartMod.ts`. 
  <b>IMPORTANT</b>: `d3.js` must be in your root `/src` directory. This requirement is harcoded in `metricsgraphics.js`. 
  It doesn't depend on this project.
- Leaflet Map Directive is located in `leafletMap` folder. If you want to use this directive:
  - Copy this folder to your `app` folder and import `NgLMapDir` in your own component or 
  
## MetricsGraphics Chart Component API

```html
<mg-chart [urlData]="urlDataString" [data]="dataArray" [request-options]="requestOptionsObject" 
  [config]="configObject" [preprocess-fn]="preprocessFn" [delay]="delayNumber"></mg-chart>
```

- There are two ways to pass data into a chart and both are mutually exclusive
  1. <b>[urlData]:</b> Url pointing to a local/remote json file with data (Remote data might have CORS restrictions)
  2. <b>[data]:</b> Array of javascript objects with X and Y coordinates, typically coming from a service.
- <b>[preprocess-Fn]:</b> Applies Javascript transformations to input data (for example format dates, etc.)
- <b>[delay]:</b> Delay the loading of data (ms). It could be useful when having serveral charts in same page
- To use MetricsGraphics global object in your component class: `declare var MG: any`

## Leaflet Map Directive API

```html
<div l-map [l-token]="tokenString" [l-center]="centerTuple" [l-zoom]="zoomNumber" [l-options]="optionsObject"></div>
```

- <b>[l-token]:</b> String with access token (Get a token in Leaflet website).
- <b>[l-center]:</b> Tuple of type `[number, number]` with the coordinates of the map center (latitude and longitude)
- <b>[l-zoom]:</b> Number with initial zoom
for more information on map options

