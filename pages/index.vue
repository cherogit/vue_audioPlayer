<template lang="pug">
.audioplayer
  h2.audioplayer__title AudioPlayer Development:
  v-audio-player
</template>

<script lang="ts">
import { Vue, Component } from "~/modules/nuxt";
import VAudioPlayer from "~/components/audio-player.vue";
import { AppContext } from "~/typings/context";

@Component({
  components: {
    VAudioPlayer
  }
})
export class VIndexPage extends Vue {}
export default VIndexPage;
</script>

<style lang="stylus">
* {
  margin 0
  padding 0
  box-sizing: border-box;
}

.audioplayer {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  height 100vh
  padding: 50px 0;
  background: #1e1e1e;

  &__title {
    margin-bottom 50px
    color: white;
  }
}


</style>
