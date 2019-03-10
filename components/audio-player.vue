<template lang="pug">
.player
	v-favorite.player__favorite

	.player__wrapper
		.player__progress
			.player__bg
				img(src="https://upload.wikimedia.org/wikipedia/en/thumb/5/5e/RHCP-BSSM.jpg/220px-RHCP-BSSM.jpg", alt="")/

			svg.progress(viewBox='0 0 200 200')
				path(fill='none', stroke-linecap='round', stroke-width='12', stroke='rgba(0,0,0, .90)', stroke-dasharray='560,560', d='M 100 100 m -80 0 a 80 80 0 1 0 160 0 a 80 80 0 1 0 -160 0')
				path.moving-line(fill='none', stroke-linecap='round', stroke-width='12', stroke='#039BE5', stroke-dasharray='0,560', d='M 100 100 m -80 0 a 80 80 0 1 1 160 0 a 80 80 0 1 1 -160 0', style='stroke-dasharray: 0, 560;')
			
			
			v-player-controls-bar(:audio="audio")
		v-track-name
	v-volume.player__volume

</template>

<script lang="ts">
import { Vue, Component } from "nuxt-property-decorator";
import VPlayerControlsBar from "./player-controls-bar.vue";
import VFavorite from "./favorite.vue";
import VVolume from "./volume.vue";
import VTrackName from "./track-name.vue";

@Component({
  name: "audio-player",
  components: {
    VPlayerControlsBar,
    VFavorite,
    VVolume,
    VTrackName
  }
})
export class VAudioPlayer extends Vue {

	public audio: HTMLAudioElement[] = [
		new Audio('https://cs9-11v4.vkuseraudio.net/p15/a0e49d1cb6a454.mp3?extra=jIbHGC0qSr-NluFtjn6vzr09PJcxxic1U1nJf9BfrAM5nqIKLcDg8u-_aFO264dHLqDNADGiwhlMM-5P5u9kixqtAfXnt4lXfiTXulMMl2kJS8QJZo0mb48rT0fgHlHC0y4ks5aOw9wGamzpAra2'),
		new Audio('https://cs9-20v4.vkuseraudio.net/p12/a2154a7b019096.mp3?extra=W5rzyvxyDXE1DtVNCf0iIHSru-uduQIJB3eLVHN1JnsprBQ0PEYqsq6UIOhF40UH1VbZamJQm6mYPAEA5YHCOLqW_oWGnznI2UVMiAyoQRb1SH98XEbHtfNjmRVFQMKMSG4MNqVqVafIs77_Qegm'),
		new Audio('https://cs9-7v4.vkuseraudio.net/p1/556c103d5733bf.mp3?extra=73R5DHQdAeE4DOFRF-YE70QVeICU4Xg0c0PPgq3SXaTTefwkB14VxwiLAA2RhEbnA9IXfdgfC8kkWAemtkPXVECt2S1Gy6-VSFvpdn9JmrB8HvnLRi40rBvJuhe-H3_Iph0-oDRDaEC0CJ_HrbNH'),
		new Audio('https://cdn.jsdelivr.net/gh/lexytail/first-phaser/assets/music.mp3')
	]
}

export default VAudioPlayer;

</script>


<style lang="stylus">
.player {
  display: flex;
  justify-content: center;
  align-items: center;

  &__wrapper {
    margin: 0 80px;
    text-align: center;
    color: white;
  }

  &__progress {
    position: relative;
    width: 200px;
    height: 200px;
    margin: 0 auto;
  }

  &__bg {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: calc(100% - 30px);
    height: calc(100% - 30px);
    border-radius: 50%;
    overflow: hidden;

    img {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      display: block;
      min-width: 100%;
      min-height: 100%;
    }
  }
	&__controls {
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%, -50%);
		width: calc(100% - 30px);
		padding: 8px 10px;
		background: rgba(0,0,0, .8);
		font-size: 0;
		z-index: 999;
	}

	&__control {
		margin: 0 5px;
		padding: 3px 8px;
		font-size: 16px;
	}
}
.progress {
	transform rotate(90deg)
}
</style>

