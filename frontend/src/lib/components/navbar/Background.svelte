<script lang="ts">
	import { fade } from 'svelte/transition';
	export let backgroundImage: string;
</script>

{#key backgroundImage}
	<div class="absolute inset-0 z-[-1] opacity-10" transition:fade={{ duration: 500 }}>
		<img src={backgroundImage} alt="Background" class="h-full w-full object-cover" />
	</div>
{/key}
