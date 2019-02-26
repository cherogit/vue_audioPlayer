<template lang="pug">
div
	button(@click="audio.play()") Проиграть

</template>

<script lang="ts">
import { Prop, Vue, Component } from "nuxt-property-decorator";

@Component({
  name: "play"
})

export class VPlay extends Vue {
  @Prop()
  public audio: HTMLAudioElement;
}
export default VPlay;

</script>


<style lang="stylus">

</style>

