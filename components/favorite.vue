<template lang="pug">
	button favorite
</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";

@Component({
  name: "favorite"
})

export class VFavorite extends Vue {}
export default VFavorite;

</script>


<style lang="stylus">

.player__favorite {
  padding: 3px 8px;
	font-size: 13px;
}

</style>

