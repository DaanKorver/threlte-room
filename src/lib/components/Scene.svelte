<script lang="ts">
	import { GLTF } from '@threlte/extras';
	import { OrbitControls, PerspectiveCamera } from '@threlte/core';
	import { AmbientLight, DirectionalLight } from '@threlte/core';
	import type { DirectionalLight as DirectionalLightT } from 'three';

	let light: DirectionalLightT | undefined;

	$: {
		if (light) {
			light.shadow.bias = -0.0001;
		}
	}
</script>

<AmbientLight intensity={1} />
<DirectionalLight bind:light shadow position={{ y: 5, x: 0 }} />
<GLTF position={{ y: -2 }} url="/room.glb" castShadow receiveShadow />
<PerspectiveCamera fov={60} position={{ x: 10, y: 5, z: 10 }}>
	<OrbitControls
		enableZoom={false}
		target={{ y: 0 }}
		maxPolarAngle={Math.PI / 2 - 0.4}
		minPolarAngle={Math.PI / 2 - 0.4}
		enableDamping
	/>
</PerspectiveCamera>
