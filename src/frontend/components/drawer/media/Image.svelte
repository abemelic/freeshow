<script lang="ts">
  import { onMount } from "svelte"

  export let src: string
  export let alt: string

  let loaded: boolean = false
  let image: any

  onMount(() => {
    image.onload = () => {
      loaded = true
    }
  })
</script>

<img style={$$props.style} {src} {alt} class:loaded bind:this={image} />

<style>
  img {
    opacity: 0;
    transition: opacity 0.5s ease-out;
  }

  img.loaded {
    opacity: 1;
  }
</style>
