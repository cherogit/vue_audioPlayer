<template lang="pug">
.player
	//- v-play(:audio="audio")
	v-favorite.player__favorite

	.player__wrapper
		.player__progress
			.player__bg
				img(src="https://upload.wikimedia.org/wikipedia/en/thumb/5/5e/RHCP-BSSM.jpg/220px-RHCP-BSSM.jpg", alt="")/

			svg(class="progress" width="200" height="200" viewBox="0 0 120 120")
				circle(cx="60" cy="60" r="54" fill="none" stroke="rgba(0,0,0, .7)" stroke-width="10")
				circle(class="progress__value" cx="60" cy="60" r="54" fill="none" stroke="#0077c7" stroke-width="10")
		v-track-name

	v-volume.player__volume
</template>

<script lang="ts">
import { Vue, Component } from 'nuxt-property-decorator'
import VPlay from './play.vue'
import VFavorite from './favorite.vue'
import VVolume from './volume.vue'
import VTrackName from './track-name.vue'

@Component({
	name: 'audio-player',
	components: {
		VPlay,
		VFavorite,
		VVolume,
		VTrackName
	}
})

export class VAudioPlayer extends Vue {
	public audio: HTMLAudioElement = new Audio('https://cdn.jsdelivr.net/gh/lexytail/first-phaser/assets/music.mp3')

	public qwe() {
			this.audio.play()
	}
}
export default VAudioPlayer

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
}
</style>

