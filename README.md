# vue2-leaflet-polyline-measure

This is a [Vue2Leaflet](https://github.com/KoRiGaN/Vue2Leaflet) plugin to provide the
[Leaflet.PolylineMeasure](https://github.com/ppete2/Leaflet.PolylineMeasure) control.


## Install
```bash
npm install --save vue2-leaflet-polyline-measure
```


## Usage

### Load the Vue component

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


### Add the component to a map

Add the `l-control-poyline-measure` component inside an `LMap`, optionally providing it with
an `options` object to specify any of the
[Leaflet.PolylineMeasure options](https://github.com/ppete2/Leaflet.PolylineMeasure#default-options)
to be set when the control is created, or the [Leaflet Control position] in which to display
the control.
For example,
```html
<l-map>
  <l-polyline-measure :options="{ showUnitControl: true }" position="bottomright"/>
  <!-- other map components -->
</l-map>
```


## Credit

The majority of the credit for this plugin goes to the author of and contributors to the underlying
[Leaflet.PolylineMeasure control](https://github.com/ppete2/Leaflet.PolylineMeasure).


### Plugin author

Michael Underwood


## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details