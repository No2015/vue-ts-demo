<template>
  <div
    :style="{
      width: '8.6rem',
      height: '6rem',
    }"
  >
    <BaiduMap
      ref="map"
      :id="id"
    />
  </div>
</template>

<script lang="ts">
import { Component,Vue } from 'vue-property-decorator';
import { getRandomId } from '@/utils/global';
import BaiduMap from '@/components/Map/BaiduMap.vue';
import {loadMapFiles} from '@/components/Map/utils';


const DEFAULT_MAP_SCALE = 17;
const DEFAULT_MAP_MAX_SCALE = 18;
const DEFAULT_MAP_MIN_SCALE = 5;
const DEFAULT_MAP_LOCATION = {
      x: 114,
      y: 23
    };

@Component<Map>({
  components: {
    BaiduMap,
  }
})

export default class Map extends Vue{
  $refs: any;
  id = getRandomId()


  mounted() {
    console.log('1111======>')
    loadMapFiles().then(() => {
      this.initMap();
    })
  }

  initMap(cb?:any) {
    this.$refs.map.initialize(
      {
        center: DEFAULT_MAP_LOCATION,
        scale: DEFAULT_MAP_SCALE,
        maxScale: DEFAULT_MAP_MAX_SCALE,
        minScale: DEFAULT_MAP_MIN_SCALE,
      },
      (event: any) => {
        // if (this.$refs.map && event.type == "load") {
        if (this.$refs.map) {
          

        } else {
          console.error("地图没有正确安装", this.$refs);
        }
      },
    );
    cb && cb();
  }
}
</script>
