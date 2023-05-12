<script lang='ts'>
	import Dashslide from "$lib/dashslide.svelte";
import ThreeCanvas from "$lib/threeCanvas.svelte";
	import Webcam from "$lib/webcam.svelte";

</script>

<h1>hi</h1>

<div class="dashboard">
	<div class="dashslide">
		<Dashslide/>
	</div>

	<div class="webcam">
		<Webcam/>
	</div>

	<div class="viewport">
		<ThreeCanvas bg={false} />
	</div>
</div>

<style>
	.viewport {
		background-color: black;
	}
</style>