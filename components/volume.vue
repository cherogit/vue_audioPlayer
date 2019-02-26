<template lang="pug">
	button volume
</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";

@Component({
  name: "volume"
})

export class VVolume extends Vue {}
export default VVolume;

</script>


<style lang="stylus">

.player__volume {
  padding: 3px 8px;
	font-size: 13px;
}

</style>

