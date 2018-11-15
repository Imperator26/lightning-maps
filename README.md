# Lightning Maps `[WIP]`

A lightweight, dependency-free slippy map renderer.

Heavily inspired by [Pigeon Maps](https://github.com/mariusandra/pigeon-maps) and [Leaflet](https://leafletjs.com), but with slightly different goals in mind:

## Goals

* Modern, built using ES6+ syntax
* Lightweight, [absolutely zero dependencies](https://github.com/Geocodio/lightning-maps/blob/master/package.json#L28) with a minified bundle of less than 20kb
* Ability to render thousands of markers, by using `<canvas>` rendering instead of depending on the DOM
* Wrappers for React and VueJS (Coming soon)

## Using

### 1. Include `LightningMaps.min.js`

> Optional: You can also use your favorite module loader

```html
<script src="LightningMaps.min.js"></script>
```

### 2. Create a `<canvas>` element

```html
<canvas id="map" width="800" height="600"></canvas>
```

### 3. Instantiate the map and add a marker

```javascript
var map = new LightningMaps.Map(canvas, {
  source: function (x, y, z) {
    return `https://maps.geocod.io/tiles/base/${z}/${x}/${y}.png`;
  },
  zoom: 12,
  center: [38.86530697026126, -77.20057854052735]
});

map.addMarker(new LightningMaps.Marker([38.882666, -77.170150]))
```

### 4. Success! You now have a map

![Example](docs/screenshots/marker-single.png)

## Development

### Run local development build and tests

```bash
npm run dev
npm run test:watch
```

> You can now head to [http://localhost:8081/docs/simple.html](http://localhost:8081/docs/simple.html) or [http://localhost:8081/docs/markers.html](http://localhost:8081/docs/markers.html) to test the app

### Build library for distribution

```bash
npm run build
```
