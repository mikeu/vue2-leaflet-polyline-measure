# vue2-leaflet-polyline-measure

This is a [Vue2Leaflet](https://github.com/KoRiGaN/Vue2Leaflet) plugin to provide the
[Leaflet.PolylineMeasure](https://github.com/ppete2/Leaflet.PolylineMeasure) control
on [Leaflet](https://leafletjs.com/) maps in [Vue](https://vuejs.org/) applications.


## Installation
```bash
npm install --save vue2-leaflet-polyline-measure
```

## Local demo
```bash
git clone git@github.com:mikeu/vue2-leaflet-polyline-measure.git
cd vue2-leaflet-polyline-measure

npm install
npm run example
```
You should then be able to visit http://localhost:4000 to see a leaflet map with the polyline
measurement tool. Events fired by the tool will be logged beneath the map as you interact with it.


## Usage

### Adding the component to a map

With the `LControlPolylineMeasure` component loaded into Vue (see below), simply add the
`l-control-poyline-measure` element inside an `l-map`, optionally providing it with an
`options` object to specify any of the
[Leaflet.PolylineMeasure options](https://github.com/ppete2/Leaflet.PolylineMeasure#default-options)
to be set when the control is created, or the
[Leaflet Control position](https://leafletjs.com/reference-1.4.0.html#control-position)
in which to display the control.
For example,
```html
<l-map>
  <l-control-polyline-measure :options="{ showUnitControl: true }" position="bottomright"/>
  <!-- other map components -->
</l-map>
```

#### Polyline measurement events

The polyline measurement control fires events from the map to which it has been added. In Vue, these
can be listened for in the standard fashion, by adding event handlers the the `LMap` control within
which the `LControlPolylineMeasure` is being used:
```html
<l-map
    @polylinemeasure:toggle="handleToggle"
    @polylinemeasure:start="handleStart"
    @polylinemeasure:resume="handleResume"
    @polylinemeasure:finish="handleFinish"
    @polylinemeasure:clear="handleClear"
    @polylinemeasure:add="handleAdd"
    @polylinemeasure:insert="handleInsert"
    @polylinemeasure:move="handleMove"
    @polylinemeasure:remove="handleRemove"
>
  <l-control-polyline-measure :options="{ showUnitControl: true }" position="bottomright"/>
  <!-- other map components -->
</l-map>
```
Of course, the `handleToggle`, `handleStart`, etc., methods must be defined within the Vue component
that is calling them.

See the [Events](https://github.com/ppete2/Leaflet.PolylineMeasure#events) section of the
Leaflet.PolylineMeasure documentation for more details about the arguments passed to each event
handler.


### Loading the Vue component

You can either install the control globally within your application at the point where you initially
configure Vue, or import the control only within the components that require it.


#### Option 1: Global install

Where you load and configure your Vue environment,
```js
import Vue from 'vue';
import LControlPolylineMeasure from 'vue2-leaflet-polyline-measure';
// ...
Vue.component('l-control-polyline-measure', LControlPolylineMeasure);
// ...
```


#### Option 2: Local import

In the `<script>` of a Vue component,
```js
import LControlPolylineMeasure from 'vue2-leaflet-polyline-measure';
// ...
export default {
  // ...
  components: {
    LControlPolylineMeasure,
    // ...
  },
  // ...
};
```


## Credit

The majority of the credit for this plugin goes to the author of and contributors to the underlying
[Leaflet.PolylineMeasure control](https://github.com/ppete2/Leaflet.PolylineMeasure), and of course
the plugin wouldn't be possible without Vue, Leaflet, and Vue2Leaflet.


### Plugin author

Michael Underwood


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
