<script lang="ts">
	import { browser } from '$app/environment';
	import { onMount } from 'svelte';
	import { bubble } from 'svelte/internal';
	import * as THREE from "three";

	const isOBSBrowserSource = typeof window !== 'undefined' && /OBS\/\d+\.\d+\.\d+/.test(window.navigator.userAgent);

	let canvas: HTMLCanvasElement;

	if(browser){
		onMount(() => {
			canvas = document.getElementById('3D') as HTMLCanvasElement;
			canvas.setAttribute('alpha', 'true');

			const renderer = new THREE.WebGLRenderer({canvas: canvas, alpha: true });
			renderer.setSize(canvas.clientWidth, canvas.clientHeight);
			renderer.setClearColor(0x000000, 0);

			const camera = new THREE.PerspectiveCamera(
				75,
				canvas.clientWidth / canvas.clientHeight,
				0.1,
				1000
			);
			camera.position.z = 5;

			const scene = new THREE.Scene();

			const geometry = new THREE.BoxGeometry();
			const material = new THREE.MeshBasicMaterial({color: 0xff00ff});
			const cube = new THREE.Mesh(geometry, material);
			scene.add(cube);

			function animate() {
				requestAnimationFrame(animate);

				cube.rotation.x += 0.01;
				cube.rotation.y += 0.01;

				renderer.render(scene, camera);
			}

			animate();
		});
	}
</script>

<canvas id="3D"></canvas>

<style>
	canvas {
		position: fixed;
		top: 0px;
		left: 0px;

		width: 100%;
		height: 100%;
	}
</style>