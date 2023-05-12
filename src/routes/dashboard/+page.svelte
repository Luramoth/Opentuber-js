<script lang='ts'>
	import Dashslide from "$lib/dashslide.svelte";
	import ThreeCanvas from "$lib/threeCanvas.svelte";
	import Webcam from "$lib/webcam.svelte";

</script>

<body>
	<div class="center">
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
	</div>
</body>

<style>

	body {
		background-color: rgb(61, 0, 61);
	}

	.center {
		position: relative;
		height: 100vh;
		box-shadow: 20px black;
	}

	.dashboard {
		display: grid;
		position: absolute;
		top: 50%;
		left: 50%;
		transform: translate(-50%,-50%);

		border-radius: 20px;
		overflow: hidden;
		background-color: black;
		
		width: 20cm;

		grid-template-rows: auto 1fr;
		grid-gap: 0px;
	}
	
	.dashslide {
		grid-column-start: 1;
		grid-row: span 2;
	}

	.webcam {
		max-height: 10cm;
		width: 10cm;

		margin-bottom: 0px;

		grid-column-start: 2;
	}

	.viewport {
		background-color: black;

		height: 10cm;
		width: 10cm;

		grid-column-start: 2;
	}
</style>