<template>
  <div class="cssDemo">
    <Heart/>
    <Terminal/>
    <FontInput/>
    <Loading1/>
    <Macaron/>
    <FantasyNav/>
  </div> 
</template>
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Macaron from '@/views/CSSDemo/Macaron.vue';
import FantasyNav from '@/views/CSSDemo/FantasyNav.vue';
import Heart from '@/views/CSSDemo/Heart.vue';
import Loading1 from '@/views/CSSDemo/Loading1.vue';
import FontInput from '@/views/CSSDemo/FontInput.vue';
import Terminal from '@/views/CSSDemo/Terminal.vue';
@Component({
  components: {
    Macaron,
    FantasyNav,
    Heart,
    Loading1,
    FontInput,
    Terminal,
  },
  
})
export default class CSSDemo extends Vue {
  
}
</script>

<style lang="css" scoped>
  .cssDemo {
    height: calc(100% -  0.8rem);
  }
</style>




