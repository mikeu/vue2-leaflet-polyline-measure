<template>
  <l-map
    style="height: 400px"
    :center="mapCentre"
    :zoom="mapZoom"
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
    <l-tile-layer
      :url="tileUrl"
      :attribution="tileAttribution"
    />
    <l-control-polyline-measure />
  </l-map>
</template>

<script>
import L from 'leaflet';
import { LMap, LTileLayer } from 'vue2-leaflet';
import LControlPolylineMeasure from './LControlPolylineMeasure.vue';

export default {
  components: {
    LMap,
    LTileLayer,
    LControlPolylineMeasure,
  },
  data () {
    return {
      mapCentre: [51, -114],
      mapZoom: 10,
      tileUrl: 'https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png',
      tileAttribution: '&copy; <a href="//osm.org/copyright">OpenStreetMap</a> contributors',
    };
  },
  methods: {
    handleToggle (e) {
      console.log('Toggled', e.status);
    },

    handleStart (currentLine) {

    },

    handleResume (currentLine) {

    },

    handleFinish (e) {

    },

    handleClear (e) {

    },

    handleAdd (e) {

    },

    handleInsert (e) {

    },

    handleMove (e) {

    },

    handleRemove (e) {

    },
  },
};
</script>

<style>
@import '~leaflet/dist/leaflet.css';
</style>