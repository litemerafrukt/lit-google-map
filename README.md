# lit-google-map

2023-08-10:

- Forked from [arkadiuszwojcik/lit-google-map](https://github.com/arkadiuszwojcik/lit-google-map)
- Add prettier and eslint
- Audit fix
- Update default version
- Add possibility to disable default ui

## Table of contents

[How to use](#How-to-use)

[Map element attributes](#Map-element-attributes)

[Marker element attributes](#Marker-element-attributes)

[Circle shape element attributes](#Circle-shape-element-attributes)

[Polygon shape element attributes](#Polygon-shape-element-attributes)

[How to build](#How-to-build)

[License](#License)

## How to use

Include lit-google-map bundle in HTML file:

```html
<script src="lit-google-map.bundle.js"></script>
```

or its minified version:

```html
<script src="lit-google-map.bundle.min.js"></script>
```

Use component in any place you want (remember to fill in Google Maps API key):

```html
<lit-google-map api-key="YOUR_GOOGLE_MAPS_API_KEY"> </lit-google-map>
```

You can also include any number of map markers:

```html
<lit-google-map api-key="YOUR_GOOGLE_MAPS_API_KEY">
  <lit-google-map-marker
    slot="markers"
    latitude="49.4404582"
    longitude="20.2700361"
  >
  </lit-google-map-marker>
  <lit-google-map-marker
    slot="markers"
    latitude="50.797444"
    longitude="20.4600623"
  >
  </lit-google-map-marker>
</lit-google-map>
```

or/and shapes:

```html
<lit-google-map api-key="YOUR_GOOGLE_MAPS_API_KEY">
  <lit-google-map-circle
    slot="shapes"
    center-latitude="49.4404582"
    center-longitude="20.2700361"
  >
  </lit-google-map-circle>
</lit-google-map>
```

## Map element attributes

- '_api-key_' - Google map API key
- '_language_' - Google map language (optional)
- '_map-id_' - Google map mapId (optional)
- '_version_' - Google map js script version to load (default: '3.48')
- '_styles_' - Map styles in json format (optional)
- '_zoom_' - Zoom level (default: '8')
- '_fit-to-markers_' - Fit map area to display all markers
- '_map-type_' - Map type to display: 'roadmap', 'satellite', 'hybrid', 'terrain'
- '_center-latitude_'- Latitude of map initial center point
- '_center-longitude_' - Longitude of map initial center point

Example:

```html
<lit-google-map
  api-key="SOME_API_KEY"
  zoom="6"
  map-type="satellite"
  center-latitude="51.8436554"
  center-longitude="19.5070867"
>
</lit-google-map>
```

## Marker element attributes

- '_latitude_' - Marker latitude position
- '_longitude_' - Marker longitude position
- '_label_' - Marker label
- '_z-index_' - Marker z index
- '_icon_' - Marker icon image url

Example:

```html
<lit-google-map-marker
  slot="markers"
  latitude="49.4404582"
  longitude="20.2700361"
>
</lit-google-map-marker>
```

Markers can also have associated InfoWindow with html content:

```html
<lit-google-map-marker
  slot="markers"
  latitude="50.797444"
  longitude="20.4600623"
>
  <p>Some description</p>
  <img src="some_image.jpg" alt="some image" />
</lit-google-map-marker>
```

## Circle shape element attributes

- '_center-latitude_' - Circle center latitude position
- '_center-longitude_' - Circle center longitude position
- '_radius_' - Circle radius (default: 100000)
- '_fill-color_' - Circle fill color
- '_fill-opacity_' - Circle fill opacity
- '_stroke-color_' - Circle stroke color
- '_stroke-opacity_' - Circle stroke opacity
- '_stroke-weight_' - Circle stroke weight

Example:

```html
<lit-google-map-circle
  slot="shapes"
  center-latitude="53.176389"
  center-longitude="22.073056"
  radius="50000"
  fill-color="#7FB3D5"
  fill-opacity="0.35"
  stroke-color="#2874A6"
  stroke-opacity="0.8"
  stroke-weight="5"
>
</lit-google-map-circle>
```

## Polygon shape element attributes

- '_paths_' - Polygon paths points in form of json array
- '_fill-color_' - Polygon fill color
- '_fill-opacity_' - Polygon fill opacity
- '_stroke-color_' - Polygon stroke color
- '_stroke-opacity_' - Polygon stroke opacity
- '_stroke-weight_' - Polygon stroke weight

Example:

```html
<lit-google-map-polygon
  slot="shapes"
  paths='[{"lat": 53.7332, "lng": 15.5180}, {"lat": 54.0444, "lng": 18.1379}, {"lat": 53.2028, "lng": 16.9292}, {"lat": 53.7332, "lng": 15.5180}]'
  fill-color="#7FB3D5"
  fill-opacity="0.35"
  stroke-color="#2874A6"
  stroke-opacity="0.8"
  stroke-weight="5"
>
</lit-google-map-polygon>
```

## How to build

Before build install all required packages:

```
npm install
```

Bare build:

```
npm run build
```

Build with bundle step:

```
npm run bundle
```

## License

MIT
