<script>
	import { onMount } from "svelte";

	const {
		src,
		caption,
		loop = false,
		autoplay = false,
		controls = true,
		customControls = false,
		hasBorder = false,
		poster = "",
	} = $props();

	let videoRef;


</script>

<figure>
	<!-- svelte-ignore a11y_media_has_caption -->
	<!-- svelte-ignore event_directive_deprecated -->
	<video class:border={hasBorder} bind:this={videoRef} {src} {loop} {autoplay} 
	{controls} muted={autoplay} preload="auto" playsinline poster={poster}></video>

	{#if caption}
		<figcaption>{@html caption}</figcaption>
	{/if}

</figure>

<style>
	figure {
		width: 100%;
		height: 100%;
	}

	video {
		position: flex;
		width: 100%;
		height: 100%;
		object-fit: cover;
	}

	.border {
		border: 4px solid #ffffff;
		border-radius: 12px;
		box-shadow: 0 0 10px rgba(0, 0, 0, 0.2);
	}

	figcaption {
		text-align: center;
		font-size: 14px;
		margin-top: 8px;
	}

</style>
  
