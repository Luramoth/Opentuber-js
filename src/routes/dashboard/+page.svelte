<script lang='ts'>
	import Dashslide from "$lib/dashslide.svelte";
	import ThreeCanvas from "$lib/threeCanvas.svelte";
	import Webcam from "$lib/webcam.svelte";

</script>

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
	.dashboard {
		display: grid;
		position: fixed;

		top: 0px;
		left: 0px;
		
		height: 10cm;
		width: 20cm;

		grid-template-rows: auto 1fr;
		grid-gap: 0px;
	}
	
	.dashslide {

		grid-column-start: 1;
		grid-row: span 2;
	}

	.webcam {
		max-height: 50vh;

		grid-column-start: 2;
	}

	.viewport {
		background-color: black;

		grid-column-start: 2;
	}
</style>