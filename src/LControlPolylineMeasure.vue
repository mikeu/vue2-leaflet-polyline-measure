<script>
import { OptionsMixin, ControlMixin, propsBinder, optionsMerger } from 'vue2-leaflet';
import LPolylineMeasure from 'leaflet.polylinemeasure';
import 'leaflet.polylinemeasure/Leaflet.PolylineMeasure.css';

export default {

  name: 'LControlPolylineMeasure',

  mixins: [
    ControlMixin,
    OptionsMixin,
  ],

  mounted () {
    const options = optionsMerger({
      ...this.controlOptions,
      options: this.options,
    }, this);
    this.mapObject = new LPolylineMeasure(options);
    propsBinder(this, this.mapObject, this.$options.props);
    this.mapObject.addTo(this.$parent.mapObject);
  },

  render () {
    return null;
  },

};
</script>