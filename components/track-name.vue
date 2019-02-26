<template lang="pug">
.player__track {{ track_name }}
</template>

<script lang="ts">
import { Prop, Vue, Component } from "nuxt-property-decorator";

@Component({
  name: "trackName"
})

export class VTrackName extends Vue {
  // @Prop()
  public track_name: string = 'Give It Away - Red Hot Chili Peppers';
}
export default VTrackName;

</script>


<style lang="stylus">

.player__track {
  transform: translateY(50px);
  font-size: 13px;
  line-height: 16px;
}

</style>

