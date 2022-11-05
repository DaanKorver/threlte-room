<script lang="ts">
	import '$lib/styles/global.css';

	import { Canvas } from '@threlte/core';
	import Scene from '$lib/components/Scene.svelte';
</script>

<div>
	<Canvas>
		<Scene />
	</Canvas>
</div>

<style>
	div {
		position: fixed;
		width: 100%;
		height: 100%;
	}
</style>
