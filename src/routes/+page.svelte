<script lang="ts">
	const isOBSBrowserSource = typeof window !== 'undefined' && /OBS\/\d+\.\d+\.\d+/.test(window.navigator.userAgent);

</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<h1>is this being rendered in OBS?: {isOBSBrowserSource}</h1>
