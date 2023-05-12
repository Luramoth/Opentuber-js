<script lang='ts'>
	import ThreeCanvas from "$lib/threeCanvas.svelte";
	import Webcam from "$lib/webcam.svelte";

</script>

<h1>hi</h1>

<div class="webcam">
	<Webcam/>
</div>

<div class="viewport">
	<ThreeCanvas bg={false} />
</div>

<style>
	.viewport {
		background-color: black;
	}
</style>