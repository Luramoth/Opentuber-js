<script lang='ts'>
	import { onMount } from "svelte";
	
	let videoref:HTMLVideoElement;


	onMount(() => {
		videoref = document.getElementById('webcam') as HTMLVideoElement;

		navigator.mediaDevices.getUserMedia({ video: true })
		.then((stream) => {
				console.log(videoref.srcObject);
				videoref.srcObject = stream;
				videoref.play();
			})
			.catch((error) => {
				console.error('Error getting webcam: ', error);
			});
	});
</script>

<!-- svelte-ignore a11y-media-has-caption -->
<video autoplay id='webcam'></video>

<style>
	video {
		width: 100%;
	}
</style>