<template>
  <div style="height: 100%; width: 100%">
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
    <p
      v-for="event in events"
      :key="event.order"
    >
      {{ event.order }}. {{ event.desc }}
    </p>
  </div>
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
      eventDescriptions: [],
    };
  },
  computed: {
    events () {
      return this.eventDescriptions.map((desc, idx) => ({ order: idx + 1, desc })).reverse();
    },
  },
  methods: {
    addEvent (desc) {
      this.eventDescriptions.push(desc);
    },
    handleToggle (e) {
      this.addEvent(`Toggled: ${e.sttus}`);
    },
    handleStart (currentLine) {
      this.addEvent(`Started: Initial distance ${currentLine.distance}`);
    },
    handleResume (currentLine) {
      this.addEvent(`Resumed: Current distance ${currentLine.distance}`);
    },
    handleFinish (currentLine) {
      this.addEvent(`Finished: Total distance ${currentLine.distance}`);
    },
    handleClear () {
      this.addEvent('Cleared');
    },
    handleAdd (e) {
      this.addEvent(`Added point: ${e.latlng}`);
    },
    handleInsert (e) {
      this.addEvent(`Inserted point: ${e.latlng}`);
    },
    handleMove (e) {
      this.addEvent(`Moved point: ${e.latlng} to ${e.sourceTarget._latlng}`);
    },
    handleRemove (e) {
      this.addEvent(`Removed point: ${e.latlng}`);
    },
  },
};
</script>

<style>
@import '~leaflet/dist/leaflet.css';
</style>