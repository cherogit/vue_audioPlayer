<template lang="pug">
.player__controls
  template
    button.player__control._play(v-if="isPlaying" @click="playPauseTrack") &#10073; &#10073; 
    button.player__control._play(v-else @click="playPauseTrack") &#9658;
  button.player__control._prev(@click="playPrevTrack") <
  button.player__control._next(@click="playNextTrack") >

</template>

<script lang="ts">
import { Prop, Vue, Component } from "nuxt-property-decorator";
import { setTimeout } from "timers";

@Component({
  name: "playerControlsBar"
})

export class VPlayerControlsBar extends Vue {
  public isPlaying = false

  @Prop()

  public audio: HTMLAudioElement[];

  public currentIndex: number = 0

  public playPauseTrack() {
    const track = this.currentTrack
    this.trakDuration()
    this.isPlaying = !this.isPlaying

    if (!track.paused) {
      track.pause()
    } else {
      track.play()
    }
  }
  
  public stopTrack() {
    const track = this.currentTrack

    track.pause()
    track.currentTime = 0
  }
	
	public get currentTrack(): HTMLAudioElement {
		return this.audio[this.currentIndex]
  }

  public playPrevTrack() {
    this.stopTrack()

    if (this.currentIndex <= 0) {
      this.currentIndex = this.audio.length - 1
    } else {
      this.currentIndex--
    }
    
    this.currentTrack.play()
  }

  public playNextTrack() {
    this.stopTrack()

    if (this.currentIndex < this.audio.length - 1) {
      this.currentIndex++
    } else {
      this.currentIndex = 0
    }

    this.currentTrack.play()
  }

  public trakDuration() {
    const track = this.currentTrack

    const duration: number = track.duration
    const minutes = Math.round(duration / 60)
    const seconds = Math.round(duration % 60)
    console.log(('this track duration: ' + minutes + ":" + seconds))

    const perc = duration / 100
  }
}
export default VPlayerControlsBar;

</script>


<style lang="stylus">

</style>

